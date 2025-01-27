# Creating Stacked Chart Visualizations

In this tutorial, you will learn how to create stacked chart
visualizations using a sample spreadsheet.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/charts-stacked-area.png" alt="charts stacked area" /><br />
</p>
<p><a href="#create-stacked-chart">Stacked Area Chart</a><br />
</p></td>
<td><p><img src="images/charts-stacked-bar.png" alt="charts stacked bar" /><br />
</p>
<p><a href="#create-stacked-chart">Stacked Bar Chart</a><br />
</p></td>
<td><p><img src="images/charts-stacked-columns.png" alt="charts stacked columns" /><br />
</p>
<p><a href="#create-stacked-chart">Stacked Columns Chart</a><br />
</p></td>
</tr>
<tr class="even">
<td><p><img src="images/stacked-columns-bounds.png" alt="stacked columns bounds" /><br />
</p>
<p><a href="#change-axis-configuration">Stacked Column with Bounds</a><br />
</p></td>
<td><p><img src="images/stacked-columns-logarithmic.png" alt="stacked columns logarithmic" /><br />
</p>
<p><a href="#set-logarithmic-axis">Stacked Column with Logarithmic Configuration</a><br />
</p></td>
<td><p><img src="images/stacked-chart-percentage-distribution.png" alt="stacked chart percentage distribution" /><br />
</p>
<p><a href="#enable-percentage-distribution">Stacked Column with Percentage Distribution</a><br />
</p></td>
</tr>
</tbody>
</table>

Access the links below for the Stacked Chart view walkthroughs:

  - [How to create a Stacked Column chart](#create-stacked-chart)

  - [How to change your Stacked chart type](#change-chart-type)

  - [How to change your axis configuration](#change-axis-configuration)

  - [How to set your axis configuration to logarithmic](#set-logarithmic-axis)

  - [How to enable percentage distribution](#enable-percentage-distribution)

## Key Concepts

There are three different layouts to choose from when using stacked
charts: [area](#create-stacked-chart),
[column](#create-stacked-chart), and [bar](#create-stacked-chart).

You can also configure the following settings:

  - **Axis Configuration**: the axis configuration lets you configure
    the minimum and maximum values for your charts. The minimum value is
    set to 0 by default and the maximum calculated automatically
    depending on your values.

      - **Logarithmic Axis Configuration**: if you check the
        "Logarithmic" checkbox, the scale for your values will be
        calculated with a non-linear scale which takes magnitude into
        account instead of the usual linear scale.

## Sample Data Source

For this tutorial, you will use the "Stacked Charts" sheet in the
[Reveal Tutorials Spreadsheet](https://download.infragistics.com/reportplus/help/samples/Reveal_Visualization_Tutorials.xlsx).

>[!NOTE]
Excel files as local files are not supported in this release. In order
to follow these tutorials, make sure you upload the file to one of the
supported _cloud services_ or add it as a [Web Resource](datasources/supported-data-sources/web-resource.md).

</div>

<a name='create-stacked-chart'></a>
## Creating a Stacked Chart

|                                          |                                                                                                        |                                                                                                                                                                                                                                                 |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Create a Dashboard**               | <img src="images/Tutorials-Create-New-Dashboard.png" alt="Tutorials-Create-New-Dashboard" class="responsive-img"/>                           | In the dashboard viewer, select the + button in the top right-hand corner of the "My Dashboards" screen. Then, select "Dashboard" from the dropdown.                                                                                            |
| 2\. **Configure your Data Source**       | <img src="images/Tutorials-Select-Data-Source.png" alt="Tutorials-Select-Data-Source" class="responsive-img"/>                               | In the *New Visualization* window, select the + button in the bottom right corner and select your data source.                                                                                                                                  |
| 3\. **Select the Tutorials Spreadsheet** | <img src="images/Tutorials-Select-Stacked-Charts-Spreadsheet.png" alt="Tutorials-Select-Stacked-Charts-Spreadsheet" class="responsive-img"/> | Once the data source is configured, select the **Reveal Tutorials Spreadsheet**. Then, choose the "Stacked Charts" sheet.                                                                                                                       |
| 4\. **Open the Visualizations Menu**     | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" class="responsive-img"/>             | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                                                                                                                           |
| 5\. **Select your Visualization**        | <img src="images/Tutorials-Stacked-Select-Visualization.png" alt="Tutorials-Stacked-Select-Visualization" class="responsive-img"/>           | By default, the visualization type will be set to "Grid". Select any of the **stack** visualizations.                                                                                                                                           |
| 6\. **Organize your Data**               | <img src="images/Tutorials-Stacked-Charts-Organizing-Data.png" alt="Tutorials-Stacked-Charts-Organizing-Data" class="responsive-img"/>       | Stacked charts require two or more fields to be dragged and dropped into the "Values" placeholder of the data editor. In this case, the "1960", "2003", "2008" and "2010" fields have been dropped into "Values" and "Country Name" in "Label". |

<a name='change-chart-type'></a>
## Changing your Stacked Chart Type

If needed, you can choose a different type of stacked chart better
fitted to your needs. In order to do this:

|                                      |                                                                                              |                                                                                                                                      |
| ------------------------------------ | -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 1\. **Open the Visualizations Menu** | <img src="images/Tutorials-Select-Change-Visualization.png" alt="Tutorials-Select-Change-Visualization" class="responsive-img"/>   | Select the **grid icon** in the top bar of the Visualizations Editor.                                                                |
| 2\. **Select your Visualization**    | <img src="images/Tutorials-Stacked-Select-Visualization.png" alt="Tutorials-Stacked-Select-Visualization" class="responsive-img"/> | Select the type of stack chart you need. This section has a [preview of every stack chart type](#create-stacked-chart) at the top. |

<a name='change-axis-configuration'></a>
## Changing your Axis Configuration

Similarly to the [Gauge bands](~/en/data-visualizations/gauge-charts#bands-configuration), the
chart axis configuration allows you to set the lowest and highest values
in your chart. You can use this feature to include or exclude specific
data.

|                                        |                                                                                      |                                                                                                                                       |
| -------------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1\. **Change Settings**                | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" class="responsive-img"/>               | Go to the **Settings** section of the Visualization Editor.                                                                           |
| 2\. **Access the Axis Bounds section** | <img src="images/Tutorials-Axis-Bounds.png" alt="Tutorials-Axis-Bounds" class="responsive-img"/>                           | Navigate to Axis Bounds.                                                                                                              |
| 3\. **Change the Default selection**   | <img src="images/Tutorials-Change-Default-Selection.png" alt="Tutorials-Change-Default-Selection" class="responsive-img"/> | Depending on whether you want to set the minimum or maximum value (or both), enter the value you want the chart to start or end with. |

<a name='set-logarithmic-axis'></a>
## Setting your Axis Configuration as Logarithmic

|                                           |                                                                          |                                                             |
| ----------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------- |
| 1\. **Change Settings**                   | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" class="responsive-img"/>   | Go to the **Settings** section of the Visualization Editor. |
| 2\. **Access the Axis option**            | <img src="images/Tutorials-Axis-Bounds.png" alt="Tutorials-Axis-Bounds" class="responsive-img"/>               | Expand the Axis dropdown by selecting the down arrow.       |
| 3\. **Select an Axis Configuration type** | <img src="images/Tutorials-Charts-Logarithmic.png" alt="Tutorials-Charts-Logarithmic" class="responsive-img"/> | Select "Logarithmic".                                       |

<a name='enable-percentage-distribution'></a>
## Enabling Percentage Distribution

For stacked charts, you can configure the Percentage Distribution. It
allows you to switch between values and percentage distribution scales
for those types of charts. In order to do this:

|                                        |                                                                                    |                                                                                           |
| -------------------------------------- | ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| 1\. **Change Settings**                | <img src="images/Tutorials-Navigate-Settings.png" alt="Tutorials-Navigate-Settings" class="responsive-img"/>             | Go to the **Settings** section of the Visualization Editor.                               |
| 2\. **Enable Percentage Distribution** | <img src="images/Tutorials-Percentage-Distribution.png" alt="Tutorials-Percentage-Distribution" class="responsive-img"/> | Enable the percentage distribution setting by checking the "Percentage Distribution" box. |
