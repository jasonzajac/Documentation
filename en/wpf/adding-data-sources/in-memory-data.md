# Adding an In-Memory Data Source

The Reveal SDK allows you to create dashboards using data that has been generated at application run-time. This data is usually backed by a business object (POCO class) that is used within the application. This type of data is referred to as **in-memory data**.

There are three primary steps to add an application's in-memory data as a data source item in the Reveal SDK.

**Step 1** - Create a class that implements `IRVDataProvider`. This class will provide the actual in-memory data to be returned to the Reveal SDK. You'll want to check the `RVInMemoryDataSourceItem.DatasetId` property to know what data to return.

```cs
class MyInMemoryDataProvider : IRVDataProvider
{
    public Task<IRVInMemoryData> GetData(RVInMemoryDataSourceItem dataSourceItem)
    {
        if (dataSourceItem.DatasetId == "MyDataSetId")
        {
            return Task.FromResult<IRVInMemoryData>(new RVInMemoryData(data));
        }
        else
        {
            throw new Exception("Invalid datasetId");
        }
    }
}
```

The `GetData` method returns a `Task<IRVInMemoryData>`. This means that any in-memory data you want to use must be wrapped by the `RVInMemoryData` object.  Simply create a new instance of the `RVInMemoryData` object and pass your in-memory data as a parameter to the object constructor.

**Step 2** - Set the `RevealSdkSettings.DataProvider` to an instance of the class that implements `IRVDataProvider`

```cs
RevealSdkSettings.DataProvider = new MyInMemoryDataProvider();
```

**Step 3** - Create an `RVInMemoryDataSourceItem` in the `RevealView.DataSourcesRequested` event.

Add an event handler to the `RevealView.DataSourcesRequested`

```html
<rv:RevealView x:Name="_revealView" DataSourcesRequested="RevealView_DataSourcesRequested" />
```

In the event handler, create a new instance of the `RVInMemoryDataSourceItem` object and provide a unique name/ID as a parameter. This ID is used in the `IRVDataProvider` to indicate which data source is requesting the data.

```cs
private void RevealView_DataSourcesRequested(object sender, DataSourcesRequestedEventArgs e)
{
    List<RVDashboardDataSource> datasources = new List<RVDashboardDataSource>();
    List<RVDataSourceItem> datasourceItems = new List<RVDataSourceItem>();

    var inMemoryDataSourceItem = new RVInMemoryDataSourceItem("MyDataSetId")
    {
        Title = "My Data"                
    };

    datasourceItems.Add(inMemoryDataSourceItem);

    e.Callback(new RevealDataSources(datasources, datasourceItems, true));
}

```

## Example: Implement In-Memory Data Source

### Create the Business Objects

For this example, we need to create 3 business objects; A `Product`, `Seller`, and a `Sale` object.  These objects will be used to hold the data that will be represented in our dashboards.

```cs
public class Product
{
    public string Name { get; set; }
    public double UnitPrice { get; set; }
}

public class Seller
{
    public string Name { get; set; }
    public string City { get; set; }
}

public class Sale
{
    internal Product Product { get; set; } = new Product();

    internal Seller Seller { get; set; } = new Seller();

    public string SalesPerson
    {
        get { return Seller.Name; }
        set { Seller.Name = value; }
    }

    public DateTime Date { get; set; }

    public string City
    {
        get { return Seller.City; }
        set { Seller.City = value; }
    }

    public string ProductName
    {
        get { return Product.Name; }
        set { Product.Name = value; }
    }

    internal double Value { get; set; }

    internal string Quarter { get; set; }

    public int NumberOfUnits { get; set; }

    public double UnitPrice
    {
        get { return Product.UnitPrice; }
        set { Product.UnitPrice = value; }
    }

    public int AmountOfSale
    {
        get { return (int)UnitPrice * NumberOfUnits; }
        set { Product.UnitPrice = value / NumberOfUnits; }
    }
}
```

### Generate the In-Memory Data

Next, we need to generate some data that will be used to build our Reveal Dashboards. For this, we will create a helper class called `SalesDataGenerator` that will generate some random data for use in our dashboards.

```cs
public class SalesDataGenerator
{
    private static string[] _products = new string[4] { "Apple", "Grape", "Orage", "Banana" };
    private static string[] _sellerNames = new string[8] { "Ellen Adams", "Lisa Andrews", "William Fox", "Walter Harp", "Jessica Oxley", "Misty Shock", "Chris Meyer", "Jay Calvin" };
    private static string[] _cities = new string[6] { "Tokyo", "Shanghai", "Beijing", "Singapore", "New York", "Seoul" };
    private static readonly Random Random = new Random();
    public static List<Sale> GenerateSales(int numberOfSales)
    {
        List<Sale> sales = new List<Sale>();

        for (double i = 0; i < numberOfSales; i++)
        {
            Sale sale = new Sale
            {
                Quarter = "Q " + i,
                Value = GetRandomPrice(),
                Date = GetRandomDate(),
                Product = GerRandomProduct(),
                NumberOfUnits = GetRandomNumUnits(),
                Seller = GetRandomSeller()
            };
            sales.Add(sale);
        }
        return sales;
    }

    private static Seller GetRandomSeller()
    {
        return new Seller
        {
            City = GetRandomCity(),
            Name = GetRandomSellerName()
        };
    }

    private static string GetRandomSellerName()
    {
        Random a = new Random(Random.Next());
        int length = _sellerNames.Length;
        int RandomMaxLength = a.Next(length) % 2 == 0 ? a.Next(length) : length;
        return _sellerNames[a.Next(RandomMaxLength)];
    }

    private static string GetRandomCity()
    {
        Random a = new Random(Random.Next());
        int length = _cities.Length;
        int RandomMaxLength = a.Next(length) % 2 == 0 ? a.Next(length) : length;
        return _cities[a.Next(RandomMaxLength)];
    }

    private static int GetRandomNumUnits()
    {
        Random a = new Random(Random.Next());
        return a.Next(1, 100);
    }

    private static Product GerRandomProduct()
    {
        return new Product
        {
            Name = GetRandomProductName(),
            UnitPrice = GetRandomPrice()
        };
    }

    private static double GetRandomPrice()
    {
        Random a = new Random(Random.Next());
        return a.NextDouble() * 1000;
    }

    private static string GetRandomProductName()
    {
        Random a = new Random(Random.Next());
        int length = _products.Length;
        int RandomMaxLength = a.Next(length) % 2 == 0 ? a.Next(length) : length;
        return _products[a.Next(RandomMaxLength)];
    }

    private static DateTime GetRandomDate()
    {
        Random a = new Random(Random.Next());
        int day = a.Next(1, 28);
        int month = a.Next(1, 13);
        int year = a.Next(2016, 2020);

        return new DateTime(year, month, day);
    }
}
```

In the constructor of our `MainWindow.cs` file in our application, we are going to create `10000` records of sales data.

```cs
public MainWindow()
{
    InitializeComponent();

    var salesData = SalesDataGenerator.GenerateSales(10000);
}
```

### Create the Data Provider

Now that we have created the data that will be used in our dashboards, the next step is to make that data available to the Reveal SDK. To do this, we need to create a new class that implements the `IRVDataProvider`.  This interface is used specifically for in-memory data implementations within the Reveal SDK.

Let's create a new class called `InMemoryDataProvider` and implement the `IRVDataProvider` interface. Notice that we also defined a constructor that accepts an `IEnumerable<Sale>`. This allows us to pass in our generated sales data from our previou step.

```cs
class InMemoryDataProvider : IRVDataProvider
{
    RVInMemoryData<Sale> _salesInMemoryData;

    public InMemoryDataProvider(IEnumerable<Sale> sales)
    {
        _salesInMemoryData = new RVInMemoryData<Sale>(sales);
    }

    public Task<IRVInMemoryData> GetData(RVInMemoryDataSourceItem dataSourceItem)
    {
        if (dataSourceItem.DatasetId == "SalesRecords")
        {
            return Task.FromResult<IRVInMemoryData>(_salesInMemoryData);
        }
        else
        {
            throw new Exception("Invalid datasetId");
        }
    }
}
```

As you can see, in the `GetData` method, we are checking the `DatasetId` for a specific value. If this id matches our `SalesRecords` data source item, then we will then use the in-memory bussiness object collection that we passed in class constructor as the data source for the dashboard.

Now that we have our data and our data provider, we need to set the `RevealSdkSettings.DataProvider` property to an instance of our `InMemoryDataProvider` class. 

```cs
public MainWindow()
{
    InitializeComponent();

    var salesData = SalesDataGenerator.GenerateSales(10000);
    RevealSdkSettings.DataProvider = new InMemoryDataProvider(salesData);
}
```

Now you may be asking, "Where does the `DataSetId` value come from?". This happens in the next step when we create the data source item.

### Handle the DataSourcesRequested Event

The next step is to add an event handler to the `RevealView.DataSourcesRequested` event.

```html
<rv:RevealView x:Name="_revealView" DataSourcesRequested="RevealView_DataSourcesRequested" />
```

```cs
private void RevealView_DataSourcesRequested(object sender, DataSourcesRequestedEventArgs e)
{
    List<RVDashboardDataSource> datasources = new List<RVDashboardDataSource>();
    List<RVDataSourceItem> datasourceItems = new List<RVDataSourceItem>();

    var inMemoryDataSourceItem = new RVInMemoryDataSourceItem("SalesRecords")
    {
        Title = "Sales Records"                
    };

    datasourceItems.Add(inMemoryDataSourceItem);

    e.Callback(new RevealDataSources(datasources, datasourceItems, true));
}
```

> [!NOTE]
> The source code to this sample can be found on [GitHub](https://github.com/RevealBi/sdk-samples-wpf/tree/master/AddingDataSources/InMemory).