# Stacked Line/Spline Charts

 * [Overview](#overview)
 * [Chart](#chart)
 * [Spline Stacked Area](#spline-stacked-area)
 * [Step Stacked Area](#step-stacked-area)

<a name="overview"/>
## Overview
Data that is arranged in columns or rows on a worksheet can be plotted in an area chart. Area charts emphasize the magnitude of change over time, and can be used to draw attention to the total value across a trend.

Stacked area charts are multi series area charts that display the trend of the contribution of each value over time or categories.

<a name="chart"/>
## Chart

As stacked charts should show contribution of different components to the total, we will demonstrate them on an imaginable ACME FastFood, Corp. sales. Let's assume that it sells Ice Cream, Chocolate Bar and Coke all through the year.

So, we have three series of data - one series for each product, and we give proper names to each series:
```
    var dataSet = anychart.data.set([
        ["Winter", 12000, 12000, 10000],  
        ["Spring", 13000, 12000, 17000],  
        ["Summer", 25000, 15000, 19000],  
        ["Autumn", 16000, 16000, 16000]   
    ]);
```
Now we have to tell Y Axis to display these series in as stacked area:
```
    chart.yScale().stackMode('value');
```
And set "Area" as a default series type:

```
    chart = anychart.areaChart();
```

{sample}BCT_Stacked\_Area-SplineArea\_Charts\_01{sample}

<a name="spline-stacked-area"/>
## Spline Stacked Area

Just change default series type to "SplineArea" and get your data displayed in more appealing way:

```
    chart.splineArea(seriesData_1);
```
<!--Also, let's add area tooltips and make them more informative, to that we will change their format:

XML Syntax
XML Code
Plain code
01
<area_series>
02
  <tooltip_settings enabled="true">
03
    <format><![CDATA[{%SeriesName} - {%Value}$ - {%YPercentOfCategory}{numDecimals:2}%]]></format>
04
  </tooltip_settings>
05
</area_series>-->
Here is a sample spline stacked area chart:

{sample}BCT_Stacked\_Area-SplineArea\_Charts\_02{sample}

<a name="step-stacked-area"/>
## Step Stacked Area

Just change default series type to "stepArea" and get your data displayed in more comparable way:

```
    chart.stepArea(seriesData_1);
```

Here is a sample step stacked area chart:

{sample}BCT_Stacked\_Area-SplineArea\_Charts\_03{sample}
<!--
Current Page Online URL: Stacked Line/Spline/StepLine Chart-->