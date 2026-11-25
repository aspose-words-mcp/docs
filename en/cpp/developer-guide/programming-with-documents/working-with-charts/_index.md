---
title: Working with Charts in C++
second_title: Aspose.Words for C++
articleTitle: Working with Charts
linktitle: Working with Charts
description: "Introduction to Chart feature, how to create and manipulate charts using C++."
type: docs
weight: 310
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-charts/
aliases:
  - /cpp/creating-ooxml-charts-from-scratch-using-aspose-words/
  - /cpp/working-with-charts-through-shape-chart-object/
  - /cpp/working-with-chartseries/
  - /cpp/working-with-chart-data-label/
  - /cpp/how-to-set-chart-axis-properties/
  - /cpp/how-to-set-fill-and-stroke-formatting/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with charts inside Word documents.

{{% /alert %}}

New [InsertChart](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertchart/) method was added into the [DocumentBuilder](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/) class. So, let's see how to insert a simple column chart into the document using the [InsertChart](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertchart/) method.

## How to Insert a Chart

In this section we will learn how to insert a chart into a document.

### Insert Column Chart

The following code example shows how to insert column chart:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "insert-simple-column-chart.h" >}}

The code produces the following result:

![create-column-chart-aspose-words-cpp](working-with-charts-1.png)

There are four different overloads for the [ChartSeriesCollection::Add](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartseriescollection/add/) method, which was exposed to cover all possible variants of data sources for all chart types:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "insert-column-chart.h" >}}

The code produces the following result:

![create-column-chart-from-datasource-aspose-words-cpp](working-with-charts-2.png)

### Insert Scatter Chart

The following code example shows how to insert a scatter chart:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "insert-scatter-chart.h" >}}

The code produces the following result:

![scatter-chart-aspose-words-cpp](working-with-charts-3.png)

### Insert Area Chart

The following code example shows how to insert an area chart:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "insert-area-chart.h" >}}

The code produces the following result:

![area-chart-aspose-words-cpp](working-with-charts-4.png)

### Insert Bubble Chart

The following code example shows how to insert a bubble chart:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "insert-bubble-chart.h" >}}

The code produces the following result:

![bubble-chart-aspose-words-cpp](working-with-charts-5.png)

## Working with Charts through `Shape::get_Chart()` Object

Once the chart was inserted and filled with data, you are able to change its appearance. The [Shape::get_Chart()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/get_chart/) method returns the chart object that contains all chart related options available through the public API.

For example, let's change Chart title or legend behavior:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "create-chart-using-shape.h" >}}

The code generates the followings results:

![line-chart-aspose-words-cpp](working-with-charts-6.png)

## How to Work with ChartSeriesCollection of Chart

Let's look into [ChartSeries](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartseries/) collection. All chart series are available through [get_Series()](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chart/get_series/) collection, which is **IEnumerable**:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "chart-series-collection.h" >}}

You can remove series one by one or clear all of them as well as add a new one if needed. The newly inserted chart has some default series added to this collection. To remove them you need to call the **chart->get_Series()->Clear()** method.

## Working with Single ChartSeries Class

Here is how to work with a particular series:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "work-with-single-chart-series.h" >}}

Please see the result below:

![line-chart-chartseries-aspose-words-cpp](working-with-charts-7.png)

All single [ChartSeries](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartseries/) have default [ChartDataPoint](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartdatapoint/) options, please try using the following code to change them:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "chart-data-point.h" >}}

Please see the result below:

![line-chart-chartdatapoint-aspose-words-cpp](working-with-charts-8.png)

## How to Work with Single ChartDataPoint of a `ChartSeries`

Using [ChartDataPoint](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartdatapoint/) you are able to customize the formatting of a single data point of the chart series:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "work-with-single-chart-data-point.h" >}}

Please see the result below:

![line-chart-datapoint-aspose-words-cpp](working-with-charts-9.png)

## How to Work with ChartDataLabel of a Single ChartSeries

Using [ChartDataLabel](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartdatalabel/) you are able to specify the formatting of a single data label of the chart series, like show/hide LegendKey, CategoryName, SeriesName, Value etc:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "work-with-chart-data-label.h" >}}

Please see the result below:

![bar-chart-aspose-words-cpp](working-with-charts-10.png)

## How to Define Default Options for ChartDataLabels of ChartSeries

The [ChartDataLabelCollection](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartdatalabelcollection/) class defines properties which can be used to set default options for **ChartDataLabels** for Chart **Series**. These properties include ShowCategoryName, ShowBubbleSize, ShowPercentage, ShowSeriesName, ShowValue etc:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "default-options-for-data-labels.h" >}}

Please see the result below:

![pie-chart-aspose-words-cpp](working-with-charts-11.png)

## How to Format Number of Chart Data Label

Using [get_NumberFormat()](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartdatalabel/get_numberformat/) you are able to specify number formatting of a single data label of the chart.

The following code example shows how to format a number of the data label:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "format-number-of-data-label.h" >}}

## How to Set Chart Axis Properties

If you want to work with chart axis, scaling, and display units for the value axis, please use [ChartAxis](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartaxis/), [AxisDisplayUnit](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/axisdisplayunit/), and [AxisScaling](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/axisscaling/) classes.

The following code example shows how to define X and Y-axis properties:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "define-axis-properties.h" >}}

### How to Set Date Time Value of Axis

The following code example shows how to set date/time values to axis properties:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "date-time-values-to-axis.h" >}}

### How to Format Number Value of Axis

The following code example shows how to change the format of numbers on the value axis:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "number-format-for-axis.h" >}}

### How to Set Bounds of Axis

The `AxisBound` class represents a minimum or maximum bound of axis values. Bound can be specified as a numeric, date-time or a special "auto" value.

The following code example shows how to set bounds of an axis:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "bounds-of-axis.h" >}}

### How to Set Interval Unit Between Labels

The following code example shows how to set the interval unit between labels on an axis:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "interval-unit-between-labels-on-axis.h" >}}

### How to Hide Chart Axis

If you want to show or hide the chart axis, you can simply achieve this by calling the `ChartAxis::set_Hidden` method.

The following code example shows how to hide the Y-axis of the chart:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "hide-chart-axis.h" >}}

### How to Align Chart Label

If you want to set a text alignment for multi-line labels, you can simply achieve this by setting the value of the [get_TickLabels()](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartaxis/get_ticklabels/)**.Alignment** property.

The following code example shows how to tick label alignment:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "tick-multi-line-label-alignment.h" >}}

{{% alert color="primary" %}}

Microsoft Word aligns Chart Label to the centre by default.

{{% /alert %}}

## How to Set Fill and Stroke Formatting

Fill and stroke formatting can be set for chart series, data points, and markers. To do this, you need to use the properties of the **ChartFormat** type in the **ChartSeries**, **ChartDataPoint**, and **ChartMarker** classes, as well as aliases for some properties, such as ForeColor, BackColor, Visible, and Transparency in the `Stroke` class.

The following code example shows how to set series color:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "fill-formatting.h" >}}

The following code example shows how to set line color and weight:

{{< gist "aspose-words-gists" "d6b6544118f3e67fee9b4558d256c998" "stroke-formatting.h" >}}
