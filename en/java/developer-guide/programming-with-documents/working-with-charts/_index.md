---
title: Working with Charts in Java
second_title: Aspose.Words for Java
articleTitle: Working with Charts
linktitle: Working with Charts
description: "Introduction to Chart feature, how to create and manipulate charts using Java."
type: docs
weight: 310
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-charts/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with charts inside Word documents.

{{% /alert %}}

New [insertChart](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertChart-int-double-double) method was added into the [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) class. So, let's see how to insert a simple column chart into the document using the [insertChart()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertChart-int-double-double) method.

## How to Insert a Chart

In this section we will learn how to insert a chart into a document.

###  Insert Column Chart

The following code example shows how to insert column chart:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "insert-simple-column-chart.java" >}}

The code produces the following result:

![create-column-chart-aspose-words-net](working-with-charts-1.png)


There are four different overloads for series Add method, which was exposed to cover all possible variants of data sources for all chart types:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "insert-column-chart.java" >}}

The code produces the following result:

![create-column-chart-from-datasource-aspose-words-net](working-with-charts-2.png)

### Insert Scatter Chart

The following code example shows how to insert a scatter chart:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "insert-scatter-chart.java" >}}

The code produces the following result:

![scatter-chart-aspose-words-net](working-with-charts-3.png)

### Insert Area Chart

The following code example shows how to insert an area chart:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "insert-area-chart.java" >}}

The code produces the following result:

![area-chart-aspose-words-net](working-with-charts-4.png)

### Insert Bubble Chart

The following code example shows how to insert a bubble chart:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "insert-bubble-chart.java" >}}

The code produces the following result:

![bubble-chart-aspose-words-net](working-with-charts-5.png)

## Working with Charts through `Shape.getChart()` Object

Once the chart has been inserted and populated with data, you can modify its appearance. Use the `shape.getChart()` method to access all chart-related options provided by the public API.

For example, let's change Chart title or legend behavior:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "create-chart-using-shape.java" >}}

The code generates the followings results:

![line-chart-aspose-words-net](working-with-charts-6.png)

## How to Work with ChartSeriesCollection of Chart

Let's look into [ChartSeries](https://reference.aspose.com/words/java/com.aspose.words/chartseries/) collection. All chart series are available through [chart.getSeries()](https://reference.aspose.com/words/java/com.aspose.words/chart/#getSeries) collection, which is **IEnumerable**:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "chart-series-collection.java" >}}

You can remove series one by one or clear all of them as well as add a new one if needed. The newly inserted chart has some default series added to this collection. To remove them you need to call the **chart.getSeries().clear()** method.

## Working with Single ChartSeries Class

Here is how to work with a particular series:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "work-with-single-chart-series.java" >}}

Please see the result below:

![line-chart-chartseries-aspose-words-net](working-with-charts-7.png)

All single [ChartSeries](https://reference.aspose.com/words/java/com.aspose.words/chartseries/) have default [ChartDataPoint](https://reference.aspose.com/words/java/com.aspose.words/chartdatapoint/) options, please try using the following code to change them:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "chart-data-point.java" >}}

Please see the result below:

![line-chart-chartdatapoint-aspose-words-net](working-with-charts-8.png)

## How to Work with Single ChartDataPoint of a `ChartSeries` 

Using [ChartDataPoint](https://reference.aspose.com/words/java/com.aspose.words/chartdatapoint/) you are able to customize the formatting of a single data point of the chart series:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "work-with-single-chart-data-point.java" >}}

Please see the result below:

![line-chart-datapoint-aspose-words-net](working-with-charts-9.png)

## How to Work with ChartDataLabel of a Single ChartSeries

Using [ChartDataLabel](https://reference.aspose.com/words/java/com.aspose.words/chartdatalabel/) you are able to specify the formatting of a single data label of the chart series, like show/hide LegendKey, CategoryName, SeriesName, Value etc:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "work-with-chart-data-label.java" >}}

Please see the result below:

![bar-chart-aspose-words-net](working-with-charts-10.png)

## How to Define Default Options for ChartDataLabels of ChartSeries

The [ChartDataLabelCollection](https://reference.aspose.com/words/java/com.aspose.words/chartdatalabelcollection/) class defines properties which can be used to set default options for **ChartDataLabels** for Chart **Series**. These properties include ShowCategoryName, ShowBubbleSize, ShowPercentage, ShowSeriesName, ShowValue etc:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "default-options-for-data-labels.java" >}}

Please see the result below:

![pie-chart-aspose-words-net](working-with-charts-11.png)

## How to Format Number of Chart Data Label

Using [getNumberFormat()](https://reference.aspose.com/words/java/com.aspose.words/chartdatalabel/#getNumberFormat) you are able to specify number formatting of a single data label of the chart.

The following code example shows how to format a number of the data label:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "format-number-of-data-label.java" >}}

## How to Set Chart Axis Properties

If you want to work with chart axis, scaling, and display units for the value axis, please use [ChartAxis](https://reference.aspose.com/words/java/com.aspose.words/chartaxis/), [AxisDisplayUnit](https://reference.aspose.com/words/java/com.aspose.words/axisdisplayunit/), and [AxisScaling](https://reference.aspose.com/words/java/com.aspose.words/axisscaling/) classes.

The following code example shows how to define X and Y-axis properties:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "define-axis-properties.java" >}}

### How to Set Date Time Value of Axis

The following code example shows how to set date/time values to axis properties:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "date-time-values-to-axis.java" >}}

### How to Format Number Value of Axis

The following code example shows how to change the format of numbers on the value axis:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "number-format-for-axis.java" >}}

### How to Set Bounds of Axis

The `AxisBound` class represents a minimum or maximum bound of axis values. Bound can be specified as a numeric, date-time or a special "auto" value.

The following code example shows how to set bounds of an axis:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "bounds-of-axis.java" >}}

### How to Set Interval Unit Between Labels

The following code example shows how to set the interval unit between labels on an axis:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "interval-unit-between-labels-on-axis.java" >}}

### How to Hide Chart Axis

In Java you would use the setter method, e.g., `chartAxis.setHidden(true);` to hide the axis or `chartAxis.setHidden(false);` to show it.

The following code example shows how to hide the Y-axis of the chart:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "hide-chart-axis.java" >}}

### How to Align Chart Label

If you want to set a text alignment for multi-line labels, you can simply achieve this by calling [AxisTickLabels.setAlignment()](https://reference.aspose.com/words/java/com.aspose.words/axisticklabels/#setAlignment-int) on the object returned by [ChartAxis.getTickLabels()](https://reference.aspose.com/words/java/com.aspose.words/chartaxis/#getTickLabels).

The following code example shows how to tick label alignment:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "tick-multi-line-label-alignment.java" >}}

{{% alert color="primary" %}}

Microsoft Word aligns Chart Label to the centre by default.

{{% /alert %}}

## How to Set Fill and Stroke Formatting

Fill and stroke formatting can be set for chart series, data points, and markers. To do this, you need to use the properties of the **ChartFormat** type in the **ChartSeries**, **ChartDataPoint**, and **ChartMarker** classes, as well as aliases for some properties, such as ForeColor, BackColor, Visible, and Transparency in the `Stroke` class.

The following code example shows how to set series color:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "fill-formatting.java" >}}

The following code example shows how to set line color and weight:

{{< gist "aspose-words-gists" "f87662b501bdf23f24f7c2412bda746f" "stroke-formatting.java" >}}
