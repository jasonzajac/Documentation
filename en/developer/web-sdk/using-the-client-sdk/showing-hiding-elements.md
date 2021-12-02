# Showing/Hiding User Interface Elements

The __$.ig.RevealView__ component can be used to enable or disable different features and/or UI elements towards the end user. Many of the available properties are of the Boolean type and can be very straightforward to use, but others not so much.

The *revealView* instance and the DOM element created below are assumed by all the code snippets in this topic: 

``` js
var revealView = new $.ig.RevealView("#revealView");
...
<div id="revealView" style="height:500px;" />
```


> [!NOTE]
> Depending on your css layout approach you might need the element hosting the RevealView to be "positioned" by setting a position attribute that is not static (like relative or absolute).


## canEdit
This property can be used to disable the user's ability to edit dashboards.

<img src="../../general/images/showing_hiding_elements_edit.png" alt="Editing a dashboard through the UI" class="responsive-img"/>

``` js
revealView.canEdit = false;
```

## showEditDataSource
This property can be used to disable the editing of a dashboard datasource.

<img src="../../general/images/showing-hiding-elements-edit-datasource.png" alt="Editing the dashboard datasource" class="responsive-img"/>

``` js
revealView.showEditDataSource = false;
```

## showExportImage
This property can be used to disable exporting the dashboad to an image.

<img src="../../general/images/showing-hiding-elements-show-export-image.png" alt="Exporting a dashboard to image" class="responsive-img"/>

``` js
revealView.showExportImage = false;
```

## showExportToPowerpoint
This property can be used to disable exporting the dashboad to PowerPoint.

<img src="../../general/images/showing-hiding-elements-show-export-powerpoint.png" alt="Exporting a dashboard to PowerPoint" class="responsive-img"/>

``` js
revealView.showExportToPowerpoint = false;
```

## showExportToPDF
This property can be used to disable exporting the dashboad to PDF.

<img src="../../general/images/showing-hiding-elements-show-export-pdf.png" alt="Exporting a dashboard to PDF" class="responsive-img"/>

``` js
revealView.showExportToPDF = false;
```

## showExportToExcel
This property can be used to disable exporting the dashboad to Excel.

<img src="../../general/images/showing-hiding-elements-show-export-excel.png" alt="Exporting a dashboard to Excel" class="responsive-img"/>

``` js
revealView.showExportToExcel = false;
```

## canCopyVisualization
This property can be used to disable the ability to copy a visualization and later paste it in the current dashboard or a different one.

<img src="../../general/images/showing_hiding_elements_copy.png" alt="Copying an existing visualization through the UI" class="responsive-img"/>

``` js
revealView.canCopyVisualization = false;
```

## canDuplicateVisualization
This property can be used to disable the ability to duplicate a visualization in the current dashboard.

<img src="../../general/images/showing_hiding_elements_duplicate.png" alt="Duplicating an existing visualization through the UI" class="responsive-img"/>

``` js
revealView.canDuplicateVisualization = false;
```

## canAddPostCalculatedFields
This property can be used to disable the ability to add a new post-calculated field in the current dashboard.

<img src="../../general/images/showing_hiding_elements_post_calculated.png" alt="Accessing post-calculated fields through the UI" class="responsive-img"/>

Post-calculated fields are new fields in the data set and are created by applying a formula on already summarized values.  
For further details, please refer to the [Reveal Help](https://help.revealbi.io/en/data-visualizations/fields/calculated-fields/overview.html).

``` js
revealView.canAddPostCalculatedFields = false;
```

## canAddCalculatedFields
This property can be used to disable the ability to add a new pre-calculated field in the current dashboard.

<img src="../../general/images/showing_hiding_elements_pre_calculated.png" alt="Accessing pre-calculated fields through the UI" class="responsive-img"/>

Pre-calculated fields are new fields in the data set and are evaluated before executing data editor aggregations.  
For further details, please refer to the [Reveal Help](https://help.revealbi.io/en/data-visualizations/fields/calculated-fields/overview.html).

``` js
revealView.canAddCalculatedFields = true;
```

## showFilters
This property can be used to show or hide the Dashboard Filters UI to the user.

<img src="../../general/images/showing_hiding_elements_filters.png" alt="Showing Dashboard Filters in the UI" class="responsive-img"/>

Dashboard filters allow you to slice the contents of the visualizations in a dashboard, all at once.

``` js
revealView.showFilters = true;
```

## canAddDashboardFilter
This property can be used to show or hide the Add Dashboard Filter menu item.

<img src="../../general/images/showing-hiding-elements-can-add-dashboard-filter.png" alt="Showing Add Dashboard Filter in the UI" class="responsive-img"/>

``` js
revealView.canAddDashboardFilter = false;
```
## canAddDateFilter
This property can be used to show or hide the Add Date Filter menu item.

<img src="../../general/images/showing-hiding-elements-can-add-date-filter.png" alt="Showing Add Date Filter in the UI" class="responsive-img"/>

``` js
revealView.canAddDateFilter = false;
```

## Preselected Filters
You can specify which values are initially selected among existing Dashboard Filters when loading a dashboard.

<img src="../../general/images/showing_hiding_elements_filters_preselected.png" alt="Showing a Dashboard Filter preselected in the UI" class="responsive-img"/>

The following code snippet illustrates how to load a dashboard “AppsStats”. By setting the “Territory” dashboard filter’s selected value to be “Americas”, the dashboard will be showing data filtered by “Americas”.

``` js
var dashboardId = "AppsStats";

$.ig.RVDashboard.loadDashboard(dashboardId, function (dashboard) {
    dashboard.filters.getByTitle("Territory").selectedValues = ["Americas"];

    var revealView = new $.ig.RevealView("#revealView");
    revealView.dashboard = dashboard;
}, function (error) {
});
```

## availableChartTypes
This property can be used to filter the visualization types available to the user.

<img src="../../general/images/showing_hiding_elements_charts.png" alt="Switching visualizations through the UI" class="responsive-img"/>

You can use a brand new Array that includes only the visualizations you want to be available:

``` js
revealView.availableChartTypes = [$.ig.RVChartType.BulletGraph, $.ig.RVChartType.Choropleth];
```

In addition, you could remove some of the charts as shown below:

```js
var toRemoveChartTypes = [$.ig.RVChartType.AreaChart, $.ig.RVChartType.Indicator, $.ig.RVChartType.IndicatorTarget, $.ig.RVChartType.ScatterMap, $.ig.RVChartType.Choropleth, $.ig.RVChartType.TreeMap];
revealView.availableChartTypes = revealView.availableChartTypes.filter(t => !toRemoveChartTypes.includes(t));

```

## canChangeVisualizationBackgroundColor
A flag indicating if the end-user can change the background color for a given visualization in the visualization editor (under Settings tab), if enabled the list of colors specified as BackgroundColors in RevealTheme will be displayed as a suggested palette, but the user can also use an advanced mode to select any color.

Default value of this property is false. So to enable the end user to specify a background for a visualization you need to set it to true.

``` csharp
revealView.canChangeVisualizationBackgroundColor = true;
```

This feature depends on [Spectrum](https://github.com/bgrins/spectrum) color picker - v 1.8.0.
In order to use it you'll need to make sure to have it loaded in the browser. Like:

```html
<link href="https://fonts.googleapis.com/css?family=Righteous" rel="stylesheet">
<link href="https://fonts.googleapis.com/css?family=Domine" rel="stylesheet">
<link href="https://fonts.googleapis.com/css?family=Caveat" rel="stylesheet">
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.min.css">
```


Background color for visualization could also be controlled programmatically by calling revealView.setVisualizationBackgroundColor(RVVisualization, color). The color argument should be a hex string like "#ffffff".

