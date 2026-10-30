---
title: Working with Charts in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Charts
linktitle: Working with Charts
description: "Create and modify charts of various types in a document using Python."
type: docs
weight: 310
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-charts/
aliases: [/python/working-with-charts/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to create, insert, and customize various chart types in a Word document using Aspose.Words for Python via .NET, covering insertion, data series manipulation, formatting, and axis settings.
{{% /alert %}}

New [insert_chart](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_chart/) method was added into the [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) class. So, let's see how to insert a simple column chart into the document using the [DocumentBuilder.insert_chart](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_chart/) method.

## How to Insert a Chart

In this section we will learn how to insert a chart into a document.

### Insert Column Chart

The following code example shows how to insert column chart:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "insert-simple-column-chart.py" >}}

The code produces the following result:

![create-column-chart-aspose-words-python](working-with-charts-1.png)

There are four different overloads for series Add method, which was exposed to cover all possible variants of data sources for all chart types:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "insert-column-chart.py" >}}

The code produces the following result:

![create-column-chart-from-datasource-aspose-words-python](working-with-charts-2.png)

### Insert Scatter Chart

The following code example shows how to insert a scatter chart:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "insert-scatter-chart.py" >}}

The code produces the following result:

![scatter-chart-aspose-words-python](working-with-charts-3.png)

### Insert Area Chart

The following code example shows how to insert an area chart:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "insert-area-chart.py" >}}

The code produces the following result:

![area-chart-aspose-words-python](working-with-charts-4.png)

### Insert Bubble Chart

The following code example shows how to insert a bubble chart:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "insert-bubble-chart.py" >}}

The code produces the following result:

![bubble-chart-aspose-words-python](working-with-charts-5.png)

## Working with Charts through Shape.chart Object

Once the chart was inserted and filled with data, you are able to change its appearance. [Shape.chart](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/chart/) property contains all chart related options available through the public API.

For example, let's change Chart title or legend behavior:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "create-chart-using-shape.py" >}}

The code generates the followings results:

![line-chart-aspose-words-python](working-with-charts-6.png)

## How to Work with ChartSeriesCollection of Chart

Let’s look into [ChartSeries](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartseries/) collection. All chart series are available through [Chart.series](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chart/series/) collection, which is **IEnumerable**:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "chart-series-collection.py" >}}

You can remove series one by one or clear all of them as well as add a new one if needed. The newly inserted chart has some default series added to this collection. To remove them you need to call [chart.series.clear()](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartseriescollection/clear/) method.

## Working with Single ChartSeries Class

Here is how to work with a particular series:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "work-with-single-chart-series.py" >}}

Please see the result below:

![line-chart-chartseries-aspose-words-python](working-with-charts-7.png)

All single [ChartSeries](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartseries/) have default [ChartDataPoint](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartdatapoint/) options, please try using the following code to change them:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "chart-data-point.py" >}}

Please see the result below:

![line-chart-chartdatapoint-aspose-words-python](working-with-charts-8.png)

## How to Work with Single ChartDataPoint of a `ChartSeries`

Using [ChartDataPoint](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartdatapoint/) you are able to customize the formatting of a single data point of the chart series:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "work-with-single-chart-data-point.py" >}}

Please see the result below:

![line-chart-datapoint-aspose-words-python](working-with-charts-9.png)

## How to Work with ChartDataLabel of a Single ChartSeries

Using [ChartDataLabel](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartdatalabel/) you are able to specify the formatting of a single data label of the chart series, like show/hide LegendKey, CategoryName, SeriesName, Value etc:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "work-with-chart-data-label.py" >}}

Please see the result below:

![bar-chart-aspose-words-python](working-with-charts-10.png)

## How to Define Default Options for ChartDataLabels of ChartSeries

The [ChartDataLabelCollection](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartdatalabelcollection/) class defines properties which can be used to set default options for **ChartDataLabels** for Chart **Series**. These properties include ShowCategoryName, ShowBubbleSize, ShowPercentage, ShowSeriesName, ShowValue etc:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "default-options-for-data-labels.py" >}}

Please see the result below:

![pie-chart-aspose-words-python](working-with-charts-11.png)

## How to Format Number of Chart Data Label

Using [ChartDataLabel.number_format](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartdatalabel/number_format/) you are able to specify number formatting of a single data label of the chart.

The following code example shows how to format a number of the data label:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "format-number-of-data-label.py" >}}

## How to Set Chart Axis Properties

If you want to work with chart axis, scaling, and display units for the value axis, please use [ChartAxis](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartaxis/), [AxisDisplayUnit](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/axisdisplayunit/), and [AxisScaling](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/axisscaling/) classes.

The following code example shows how to define X and Y-axis properties:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "define-axis-properties.py" >}}

### How to Set Date Time Value of Axis

The following code example shows how to set date/time values to axis properties:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "date-time-values-to-axis.py" >}}

### How to Format Number Value of Axis

The following code example shows how to change the format of numbers on the value axis:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "number-format-for-axis.py" >}}

### How to Set Bounds of Axis

The `AxisBound` class represents a minimum or maximum bound of axis values. Bound can be specified as a numeric, date-time or a special "auto" value.

The following code example shows how to set bounds of an axis:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "bounds-of-axis.py" >}}

### How to Set Interval Unit Between Labels

The following code example shows how to set the interval unit between labels on an axis:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "interval-unit-between-labels-on-axis.py" >}}

### How to Hide Chart Axis

If you want to show or hide the chart axis, you can simply achieve this by setting the value of [ChartAxis.hidden](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartaxis/hidden/) property.

The following code example shows how to hide the Y-axis of the chart:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "hide-chart-axis.py" >}}

### How to Align Chart Label

If you want to set a text alignment for multi-line labels, you can simply achieve this by setting the value of the [tick_labels](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartaxis/tick_labels/)**.Alignment** property.

The following code example shows how to tick label alignment:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "tick-multi-line-label-alignment.py" >}}

{{% alert color="primary" %}}

Microsoft Word aligns Chart Label to the centre by default.

{{% /alert %}}

## How to Set Fill and Stroke Formatting

Fill and stroke formatting can be set for chart series, data points, and markers. To do this, you need to use the properties of the **ChartFormat** type in the **ChartSeries**, **ChartDataPoint**, and **ChartMarker** classes, as well as aliases for some properties, such as ForeColor, BackColor, Visible, and Transparency in the `Stroke` class.

The following code example shows how to set series color:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "fill-formatting.py" >}}

The following code example shows how to set line color and weight:

{{< gist "aspose-words-gists" "cac7ca6859ace98c8f23cb5c2a4348ee" "stroke-formatting.py" >}}