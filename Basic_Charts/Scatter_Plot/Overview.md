{:index 1}
# Overview

* [Overview](#overview)
* [Chart](#chart)
  * [Line Chart](#line_chart)
  * [Bubble Chart](#bubble_chart)
  * [Marker Chart](#marker_chart)
* [Axes](#axes)
  * [Orientation](#orientation)
  * [Inversion](#inversion)
  * [Minimum and Maximum](#minimum_and_maximum)
  * [Logarithmic](#logarithmic)
* [Labels and Tooltips](#labels_and_tooltips)

## Overview

Scatter charts show the relationships among the numeric values in several data series, or between two groups of numbers as one series of XY coordinates.

A scatter chart has two value axes, showing one set of numerical data along the horizontal axis (X-axis) and another one along the vertical axis (Y axis). It combines these values into single data points and displays them in uneven intervals, or clusters. Scatter charts are commonly used for displaying and comparing numeric values, such as scientific, statistical and engineering data.

Use a scatter chart when:

 * You want to change the scale of the horizontal axis.
 * You want to make that axis logarithmic.
 * Values for horizontal axis are not evenly spaced.
 * There are a lot of data points on the horizontal axis.
 * You want an effective representation of data that includes pairs or groups of value sets and adjust the independent scales of a scatter chart to reveal more information about the grouped values.
 * You want to show similarities between large sets of data instead of differences between data points.
 * You want to compare large numbers of data points without regard to time — the more data you have in a scatter chart, the better comparisons you can make.

## Chart

Depending on your task you can plot the following types on a Scatter plot: Line, Marker and Bubble charts. To start the creation of Scatter chart you need create chart using {api:anychart#scatter}.scatter(){api} method.

```
var chart = anychart.scatter();
```

### Line Chart

As Scatter charts are plotted using two values you always need to specify both x and y.

Let's take the following table as the source of data for the scatter chart as the first line:

<table border="1" class="dtTABLE">
 <tbody>
  <tr>
   <th width="80">x</th>
   <th width="80">y</th>
  </tr>
  <tr>
   <td>-2</td>
   <td>4</td>
  </tr>
  <tr>
   <td>-1</td>
   <td>1</td>
  </tr>
  <tr>
   <td>0</td>
   <td>0</td>
  </tr>
  <tr>
   <td>1</td>
   <td>1</td>
  </tr>
  <tr>
   <td>2</td>
   <td>4</td>
  </tr>
 </tbody>
</table>

And here is the data for the second line:

<table border="1" class="dtTABLE">
 <tbody>
  <tr>
   <th width="80">x</th>
   <th width="80">y</th>
  </tr>
  <tr>
   <td>-2</td>
   <td>-4</td>
  </tr>
  <tr>
   <td>-1</td>
   <td>-1</td>
  </tr>
  <tr>
   <td>0</td>
   <td>0</td>
  </tr>
  <tr>
   <td>1</td>
   <td>-1</td>
  </tr>
  <tr>
   <td>2</td>
   <td>-4</td>
  </tr>
 </tbody>
</table>

Converted data from the tables is represented below:

```
// set chart type
var chart = anychart.scatter();

// data for the first line series
chart.line ([
  [-2, 4],
  [-1, 1],
  [0, 0],
  [1, 1],
  [2, 4]
]);

// data for the second line series
chart.line([
  [-2, -4],
  [-1, -1],
  [0, 0],
  [1, -1],
  [2, -4],
]);
```

As you can see we've created two Line series on the scatter plot:

{sample}BCT\_ScatterChart\_01{sample}

### Bubble Chart

Scatter Bubble Charts are widely used in many analytical studies as it is one of the popular tools for identifying and illustrating industry clusters. Essentially, these charts allow four different variables to be plotted within the same graph, making it easy to assess relative economic performance. Bubble charts can be used to plot up to 4 different variables on a single plot:

```
chart.bubble([
  {name: 'Point 1', x: 10, y: 20, size: 10},
  {name: 'Point 2', x: 20, y: 30, size: 20}
]).fill('red');

chart.bubble([
  {name: 'Point 3', x: '20', y: '30', size: '18' }
]).fill('green');
```

Above there is a demonstration of two data series of Bubble type, colored with Red and Green colors and set x, y and size.

In the sample below we use these knowledge to make a real sample of cluster analysis charting.

We illustrate industry cluster relationships for the 17 "Springfield" targeted industry clusters. The following four variables are plotted in this single graphic:

 * 1. Average cluster wages: on the x-axis (horizontal)
 * 2. Growth in jobs; on the y-axis (vertical)
 * 3. Employment size of the industry; indicated by the size of the bubble
 * 4. The industry’s location quotient; indicated by the color of the bubble

  
{sample}BCT\_ScatterChart\_02{sample}

### Marker Chart

Scatter Point or Marker JavaScript chart is used to make a scatter plot (scatter diagram or scatter graph). It is a chart used to display values of two variables. The data is displayed as a collection of points, each having one coordinate on the horizontal axis and one on the vertical axis.

A scatter plot does not specify dependent or independent variables. Either type of variable can be plotted on either axis. Scatter plots represent the association (not causation) between two variables.

To plot a scatter diagram using AnyChart you should use {api:anychart.charts.Scatter#marker}Marker{api} series type along with {api:anychart.charts.Scatter}anychart.scatterChart(){api}:

```
var chart = anychart.scatter();

chart.marker([
  {2, 10},
  {2, 20},
  {3, 0},
  {13, 0}
])
```

In the sample below we plot waiting time between eruptions and the duration of the eruptions for the Old Faithful geyser in Yellowstone National Park, Wyoming, USA. This chart suggests there are generally two "types" of eruptions: short-wait-short-duration, and long-wait-long-duration.

We will also draw a "best-fit" straight line through the data, calculated using linear regression method.

{sample}BCT\_ScatterChart\_03{sample}

## Axes

In AnyChart axis is an object that allows you to configure chart grid, axis line along with tick marks and labels, axis scale and settings and else. All axis features are described in [Axes Basics](../Axes_and_Grids/Axis_Basics) tutorial. In this section we will quickly demonstrate how we can adjust axis orientation, invert axis scale and control minimum and maximum values.

### Orientation

With AnyChart you can place axes to any side of the chart, all you need to do is to adjust {api:anychart.enums.Orientation}.orientation(){api} parameter of {api:anychart.charts.Cartesian#yAxis}.yAxis(){api} or {api:anychart.charts.Cartesian#xAxis}.xAxis(){api} methods.

Orientation depends on plot type and inversion of axes, you will find list of all possible orientation and inversion settings in [Axes Orientation](../Axes_and_Grids/Axis_Orientation) tutorial.

```
chart.xAxis().orientation('right');
chart.yAxis().orientation('top');
```

{sample}BCT\_ScatterChart\_04{sample}

### Inversion

AnyChart allows to invert any axis: Y, X or any extra. Inversion is controlled by axis **scale().inverted()**:

```
chart.yScale().inverted(true);
```

And here is the demonstration of Y and X-Axis inversion in the Marker sample:

{sample}BCT\_ScatterChart\_05{sample}

### Minimum and Maximum

By default AnyChart charting library calculates axis the minimum and the maximum automatically. You can see this on the scale inversion chart sample above: the minimal value of the Y-Axis is -5, and maximum is 5. You can control these values by setting **.maximum()** and **.minimum()** parameters of the scale:


```
chart.yScale().minimum('-20').maximum('30');
```

And here is the demonstration of maximum and minimum values in the Line sample:

{sample}BCT\_ScatterChart\_06{sample}

### Logarithmic

AnyChart allows to make Y, X or any extra axis Logarithmic. This is controlled by {api:anychart.scales.Logarithmic}scale{api}:

```
var logScaleY = anychart.scales.log();  // create logarithmic scale
logScaleY.minimum(0.1).maximum(10000);  // set parameters for the scale
chart.yScale(logScaleY);                // use logarithmic scale as Y scale of the chart

var logScaleX = anychart.scales.log();  // create logarithmic scale
logScaleX.minimum(0.1).maximum(10000);  // set parameters for the scale
chart.xScale(logScaleX);                // use logarithmic scale as X scale of the chart
```

And here is the demonstration of Logarithmic Y Scale on Line chart sample - using of both X an Y logarithmic axes
allowed us to plot data within hundreds and within thousands on the same plot:

{sample}BCT\_ScatterChart\_07{sample}

## Labels and Tooltips

If you want to configure data labels and tooltips for all series - you should use{api:anychart.core.scatter.series.Base#labels}labels(){api} and {api:anychart.charts.Scatter#tooltip}tooltip(){api} methods. You can tune the visual appearance, positioning and format of labels and tooltips.

```
// set labels
chart.bubble(data).labels().textFormatter("{%Name}");
```

{sample}BCT\_ScatterChart\_08{sample}