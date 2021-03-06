{:index 2}
# 3D Column Chart

## Overview

This article explains how to create a 3D Column chart in AnyChart.

To learn more about 3D charts in general and how to customize them, see [3D Charts (Overview)](Overview). You can also read the [Bar Chart](../Bar_Chart) article.

## Quick Start

To build a 3D Column chart, use the {api:anychart#column3d}anychart.column3d(){api} chart constructor. You can either pass your data to the chart constructor or create a series by using the {api:anychart.charts.Cartesian3d#column}column(){api} method:

```
// create a 3d column chart
chart = anychart.column3d();

// create a column series and set the data
var series = chart.column(data);
```

{sample}BCT\_3D\_Column\_Chart{sample}

## Special Settings

### Z-Distribution

When you use the {api:anychart#area3d}anychart.bar3d(){api} chart constructor, the [Z-distribution](Overview#z-distribution) is disabled by default, which means that the series of multiple-series charts are distributed along the X-axis.

### Point Size

This chart type allows you to set the size of its points. Read more in the [Point Size](../../Common_Settings/Point_Size) article.