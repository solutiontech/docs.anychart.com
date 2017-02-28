{:index 1}
# Percent Stacked Step Area Chart

* [Overview](#overview)
* [Quick Start](#quick_start)

## Overview

A percent stacked step area chart (also known as a 100% stacked step area chart) is a multi-series area chart that displays the trend of the percentage each value contributes over time or categories.

The concept of stacking in AnyChart is explained in this article: [Stacked Charts (Overview)](../Overview).

## Quick Start

To build a Percent Stacked Step Area Chart, you should create a multi-series [Step Area Chart](../../Step_Area_Chart) and set {api:anychart.scales.Linear#stackMode}stackMode(){api} to <strong>percent</strong>:

```
// create a chart
var chart = chart.area();

// enable the percent stacking mode
chart.yScale().stackMode("percent");

// create step area series
var series1 = chart.stepArea(seriesData_1);
var series2 = chart.stepArea(seriesData_2);
```

{sample}BCT\_Percent\_Stacked\_Step\_Area\_Chart{sample}