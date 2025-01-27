# Creating Gauge Visualizations

In this tutorial, you will learn how to create gauge visualizations
using a sample spreadsheet.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/lineargauge-visualization.png" alt="lineargauge visualization" /><br />
</p>
<p><a href="#create-linear-gauge">Linear Gauge</a><br />
</p></td>
<td><p><img src="images/circulargauge-visualization.png" alt="circulargauge visualization" /><br />
</p>
<p><a href="#create-circular-gauge">Circular Gauge</a><br />
</p></td>
<td><p><img src="images/textgauge-visualization.png" alt="textgauge visualization" /><br />
</p>
<p><a href="#create-text-gauge">Text Gauge</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/bulletgraphgauge-visualization.png" alt="bulletgraphgauge visualization" /><br />
</p>
<p><a href="#create-bullet-graph-gauge">Bullet Graph</a><br />
</p></td>
<td><p><img src="images/lineargauge-boundsconfiguration.png" alt="lineargauge boundsconfiguration" /><br />
</p>
<p><a href="#adding-bounds-gauge">Linear Gauge with Bounds configuration</a><br />
</p></td>
<td><p><img src="images/lineargauge-visualization-bandconfiguration.png" alt="lineargauge visualization bandconfiguration" /><br />
</p>
<p><a href="#modify-bands">Linear Gauge with different Band Colors</a><br />
</p></td>
</tr>
</tbody>
</table>

Access the links below for the gauge view walkthroughs:

  - [How to create a Linear Gauge](#create-linear-gauge)

  - [How to create a Radial Gauge](#create-circular-gauge)

  - [How to create a Label Gauge](#create-text-gauge)

  - [How to create a Bullet Graph](#create-bullet-graph-gauge)

  - [How to add bounds to your gauge visualizations](#adding-bounds-gauge)

  - [How to change band colors](#modify-bands)

<a name='key-concepts'></a>
## Key Concepts

There are three different layouts to choose from when using gauge charts:

  - **Bounds Configuration**. The bounds configuration for gauges covers
    the lowest and highest possible values in your gauges. It is usually
    set to the lowest value in your data source by default, but you can
    change it to exclude specific data.

  - **Bands Configuration**. The bands configuration allows you to
    establish three different ranges for your information (Higher than,
    between, and Less than). You can override the default values with
    ranges tailored to your data source.

## Sample Data Source

For this tutorial, you will use the "Gauge Views" sheet in the [Reveal Tutorials Spreadsheet](https://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx).

>[!NOTE]
>Excel files as local files are not supported in this release. In order to follow these tutorials, make sure you upload the file to one of the supported cloud services or add it as a [Web Resource](~/en/datasources/supported-data-sources/web-resource.md).

<a name='create-linear-gauge'></a>
## Creating a Linear Gauge

|                                          |                                                                                            |                                                                                                                                                                       |
| ---------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" class="responsive-img"/>               | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                  |
| 2\. **Configure your Data Source**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" class="responsive-img"/>                   | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                        |
| 3\. **Select the Tutorials Spreadsheet** | <img src="images/Tutorials-Select-Gauge-Views.png" alt="Tutorials-Select-Gauge-Views" class="responsive-img"/>                   | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet and select *Load Data*.                         |
| 4\. **Open the Visualizations Menu**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" class="responsive-img"/> | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                 |
| 5\. **Select your Visualization**        | <img src="images/Tutorials-Select-Linear-Gauge.png" alt="Tutorials-Select-Linear-Gauge" class="responsive-img"/>                 | By default, the visualization type will be set to "Grid". Select the "Linear" gauge.                                                                                  |
| 6\. **Organize your Data**               | <img src="images/Tutorials-LinearGauge-Data.png" alt="Tutorials-LinearGauge-Data" class="responsive-img"/>                       | This linear gauge, for example, will display life expectancy per Country. Drag and drop the "Country Name" field to "Label" and one of the year fields into "Values". |

<a name='create-circular-gauge'></a>
## Creating a Circular Gauge

|                                          |                                                                                            |                                                                                                                                                                       |
| ---------------------------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" class="responsive-img"/>               | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                  |
| 2\. **Configure your Data Source**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" class="responsive-img"/>                   | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                        |
| 3\. **Select the Tutorials Spreadsheet** | <img src="images/Tutorials-Select-Gauge-Views.png" alt="Tutorials-Select-Gauge-Views" class="responsive-img"/>                   | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet and select *Load Data*.                         |
| 4\. **Open the Visualizations Menu**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" class="responsive-img"/> | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                 |
| 5\. **Select your Visualization**        | <img src="images/Tutorials-Select-Linear-Gauge.png" alt="Tutorials-Select-Linear-Gauge" class="responsive-img"/>                 | By default, the visualization type will be set to "Grid". Select the "Circular" gauge.                                                                                |
| 6\. **Organize your Data**               | <img src="images/Tutorials-CircularGauge-Data.png" alt="Tutorials-CircularGauge-Data" class="responsive-img"/>                   | This radial gauge, for example, will display life expectancy per Country. Drag and drop the "Country Name" field to "Label" and one of the year fields into "Values". |


Circular Gauges are particularly useful to show average values as well
as sum of values. In order to change the aggregation for the field
displayed in Values:

<a name='aggregation-instructions'></a>

|                                              |                                                                            |                                                                                           |
| -------------------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| 1\. **Access Field Settings for your Value** | <img src="images/Add-Data-Filter-CircularGauge.png" alt="Add-Data-Filter-CircularGauge" class="responsive-img"/> | Select the field in **Values** to access                                                  |
| 2\. **Choose a different Aggregation**       | <img src="images/CircularGauge-Aggregation.png" alt="CircularGauge-Aggregation" class="responsive-img"/>         | Expand the **Aggregation** dropdown and select a different option (for example, Average). |


<a name='create-text-gauge'></a>
## Creating a Text Gauge

|                                          |                                                                                                                   |                                                                                                                                                                                                                                                       |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" class="responsive-img"/>                                      | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                                                                                                  |
| 2\. **Configure your Data Source**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" class="responsive-img"/>                                          | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                                                                                                        |
| 3\. **Select the Tutorials Spreadsheet** | <img src="images/Tutorials-Select-Simple-Series-Charts-Spreadsheet.png" alt="Tutorials-Select-Simple-Series-Charts-Spreadshee" class="responsive-img"/> | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet.                                                                                                                                |
| 4\. **Open the Visualizations Menu**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" class="responsive-img"/>                        | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                                                                                                 |
| 5\. **Select your Visualization**        | <img src="images/Tutorials-Select-Linear-Gauge.png" alt="Tutorials-Select-Linear-Gauge" class="responsive-img"/>                                        | By default, the visualization type will be set to "Grid". Select the "Text" gauge.                                                                                                                                                                    |
| 6\. **Organize your Data**               | <img src="images/Tutorials-TextGauge-Organizing-Data.png" alt="Tutorials-TextGauge-Organizing-Data" class="responsive-img"/>                            | This text gauge, for example, will display life expectancy per Country. Drag and drop one of the year fields into "Values", and then the "Country Name" field into "Data Filters". Then, select the specific country you want by selecting the field. |

The text gauge sample above utilizes
the average aggregation. In order to learn how to change your field's
aggregation, [review these instructions](#aggregation-instructions).

<a name='create-bullet-graph-gauge'></a>
## Creating a Bullet Graph

|                                          |                                                                                                                   |                                                                                                                                                                                              |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" class="responsive-img"/>                                      | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                                         |
| 2\. **Configure your Data Source**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" class="responsive-img"/>                                          | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                                               |
| 3\. **Select the Tutorials Spreadsheet** | <img src="images/Tutorials-Select-Simple-Series-Charts-Spreadsheet.png" alt="Tutorials-Select-Simple-Series-Charts-Spreadshee" class="responsive-img"/> | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Gauge Views" sheet.                                                                       |
| 4\. **Open the Visualizations Menu**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" class="responsive-img"/>                        | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                                        |
| 5\. **Select your Visualization**        | <img src="images/Tutorials-Charts-Select-Visualization.png" alt="Tutorials-Charts-Select-Visualization" class="responsive-img"/>                        | By default, the visualization type will be set to "Grid". Select the "Bullet Graph" visualization.                                                                                           |
| 6\. **Organize your Data**               | <img src="images/Tutorials-Charts-Organizing-Data.png" alt="Tutorials-Charts-Organizing-Data" class="responsive-img"/>                                  | This bullet graph, for example, will display life expectancy per Country. Drag and drop the "Country Name" field to "Label", one of the years into "Values", and another year into "Target". |

<a name='adding-bounds-gauge'></a>
## Adding Bounds to your Gauge

Bounds allow you to set the lowest and highest values in your gauges; as
mentioned in [Key Concepts](###ey-concepts), you can change it to exclude
specific data. In order to do this:

|                                                |                                                                        |                                                                                                                                       |
| ---------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Change Settings**                        | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" class="responsive-img"/> | Go to the **Settings** section of the Visualization Editor.                                                                           |
| 2\. **Change the Default selection in Limits** | <img src="images/Tutorials-Limits-Bounds.png" alt="Tutorials-Limits-Bounds" class="responsive-img"/>         | Depending on whether you want to set the minimum or maximum value (or both), enter the value you want the chart to start or end with. |

<a name='modify-bands'></a>
## Changing Band Colors

The colors for the three different ranges (Higher than, Lower than and
Between) can be changed between the predefined colors. In order to do
so:

|                                    |                                                                        |                                                                          |
| ---------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| 1\. **Change Settings**            | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" class="responsive-img"/> | Go to the **Settings** section of the Visualization Editor.              |
| 2\. **Access the Colors dropdown** | <img src="images/Tutorials-Colors-Dropdown.png" alt="Tutorials-Colors-Dropdown" class="responsive-img"/>     | Expand the dropdown of the range for which you want to change the color. |
| 3\. **Select your Color**          | <img src="images/Tutorials-Changing-Color.png" alt="Tutorials-Changing-Color" class="responsive-img"/>       | Select one of Reveal's three predefined colors for your band color.      |
