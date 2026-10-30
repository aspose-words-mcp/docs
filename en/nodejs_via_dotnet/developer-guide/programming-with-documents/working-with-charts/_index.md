---
title: Working with Charts in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Charts
linktitle: Working with Charts
description: "Create and modify charts of various types in a document using Node.js."
type: docs
weight: 310
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-charts/
timestamp: 2025-07-09-10-05-05
---

New [insertChart](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertchart/) method was added into the [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) class. So, let's see how to insert a simple column chart into the document using [DocumentBuilder.insertChart](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertchart/) method:

### How to Insert a Chart

In this section we will learn how to insert a chart into a document.

### Insert Column Chart

The following code example shows how to insert column chart:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "insert-simple-column-chart.js" >}}

The code produces the following result:

![create-column-chart-aspose-words-net](working-with-charts-1.png)

There are [add](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartseriescollection/add/), **addDouble** and **addDate** methods, which was exposed to cover all possible variants of data sources for all chart types:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "insert-column-chart.js" >}}

The code produces the following result:

![create-column-chart-from-datasource-aspose-words-net](working-with-charts-2.png)

### Insert Scatter Chart

Below example shows how to insert a scatter chart.

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "insert-scatter-chart.js" >}}

The code produces the following result:

![scatter-chart-aspose-words-net](working-with-charts-3.png)

### Insert Area Chart

The following code example shows how to insert an area chart:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "insert-area-chart.js" >}}

The code produces the following result:

![area-chart-aspose-words-net](working-with-charts-4.png)

### Insert Bubble Chart

The following code example shows how to insert a bubble chart:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "insert-bubble-chart.js" >}}

The code produces the following result:

![bubble-chart-aspose-words-net](working-with-charts-5.png)

## Working with Charts through Shape.chart Object

Once the chart was inserted and filled with data, you are able to change its appearance. [Shape.chart](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/chart/) property contains all chart related options available through the public API.

For example, let's change [ChartTitle](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/charttitle/) title or [ChartLegend](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartlegend/) behavior:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "create-chart-using-shape.js" >}}

The code generates the followings results:

![line-chart-aspose-words-net](working-with-charts-6.png)

## How to Work with ChartSeriesCollection of Chart

Let's look into [ChartSeries](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartseries/) collection. All chart series are available through [Chart.series](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/chart/series/) collection:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "chart-series-collection.js" >}}

You can remove series one by one or clear all of them as well as add a new one if needed. The newly inserted chart has some default series added to this collection. To remove them you need to call [chart.series.clear()](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartseriescollection/clear/) method.

## Working with Single ChartSeries Class

Here is how to work with a particular series.

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "work-with-single-chart-series.js" >}}

Please see the result below:

![line-chart-chartseries-aspose-words-net](working-with-charts-7.png)


All single [ChartSeries](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartseries/) have default [ChartDataPoint](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatapoint/) options, please try using the following code to change them:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "chart-data-point.js" >}}

Please see the result below:

![line-chart-chartdatapoint-aspose-words-net](working-with-charts-8.png)

## How to Work with Single ChartDataPoint of a `ChartSeries` 

Using [ChartDataPoint](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatapoint/) you are able to customize the formatting of a single data point of the chart series:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "work-with-single-chart-data-point.js" >}}

Please see the result below:

![line-chart-datapoint-aspose-words-net](working-with-charts-9.png)

## How to Work with ChartDataLabel of a Single ChartSeries

Using [ChartDataLabel](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabel/) you are able to specify the formatting of a single data label of the chart series, like show/hide LegendKey, CategoryName, SeriesName, Value etc.

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "work-with-chart-data-label.js" >}}

Please see the result below:

![bar-chart-aspose-words-net](working-with-charts-10.png)

## How to Define Default Options for ChartDataLabels of ChartSeries

The [ChartDataLabelCollection](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabelcollection/) class defines properties which can be used to set default options for [ChartDataLabel](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabel/) for Chart Series. These properties include [showCategoryName](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabelcollection/showcategoryname/), [showBubbleSize](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabelcollection/showbubblesize/), [showPercentage](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabelcollection/showpercentage/), [showSeriesName](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabelcollection/showseriesname/), [showValue](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabelcollection/showvalue/) etc.

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "default-options-for-data-labels.js" >}}

Please see the result below:

![pie-chart-aspose-words-net](working-with-charts-11.png)

## How to Format Number of Chart Data Label

Using [ChartDataLabel.numberFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatalabel/numberformat/) you are able to specify number formatting of a single data label of the chart.

The following code example shows how to format a number of the data label:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "format-number-of-data-label.js" >}}

## How to Set Chart Axis Properties

If you want to work with chart axis, scaling, and display units for the value axis, please use [ChartAxis](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartaxis/), [AxisDisplayUnit](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/axisdisplayunit/), and [AxisScaling](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/axisscaling/) classes.

The following code example shows how to define X and Y-axis properties:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "define-axis-properties.js" >}}

### How to Set Date Time Value of Axis

The following code example shows how to set date/time values to axis properties:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "date-time-values-to-axis.js" >}}

### How to Format Number Value of Axis

The following code example shows how to change the format of numbers on the value axis:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "number-format-for-axis.js" >}}

### How to Set Bounds of Axis

The [AxisBound](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/axisbound/) class represents a minimum or maximum bound of axis values. Bound can be specified as a numeric, date-time or a special "auto" value.

The following code example shows how to set bounds of an axis:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "bounds-of-axis.js" >}}

### How to Set Interval Unit Between Labels

The following code example shows how to set the interval unit between labels on an axis:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "interval-unit-between-labels-on-axis.js" >}}

### How to Hide Chart Axis

If you want to show or hide the chart axis, you can simply achieve this by setting the value of [ChartAxis.hidden](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartaxis/hidden/) property.

The following code example shows how to hide the Y-axis of the chart:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "hide-chart-axis.js" >}}

### How to Align Chart Label

If you want to set a text alignment for multi-line labels, you can simply achieve this by setting the value of **ChartAxis.tickLabels.alignment** property.

The following code example shows how to tick label alignment:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "tick-multi-line-label-alignment.js" >}}

{{% alert color="primary" %}}

MS Word aligns Chart Label to the centre by default.

{{% /alert %}}

## How to Set Fill and Stroke Formatting

Fill and stroke formatting can be set for chart series, data points, and markers. To do this, you need to use the properties of the [ChartFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartformat/) type in the [ChartSeries](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartseries/), [ChartDataPoint](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartdatapoint/), and [ChartMarker](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing.charts/chartmarker/) classes, as well as aliases for some properties, such as [foreColor](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/stroke/forecolor/), [backColor](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/stroke/backcolor/), [visible](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/stroke/visible/), and [transparency](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/stroke/transparency/) in the [stroke](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/stroke/) class.

The following code example shows how to set series color:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "fill-formatting.js" >}}

The following code example shows how to set line color and weight:

{{< gist "aspose-words-gists" "7ce46b3fa44be2f120f85d4e070329db" "stroke-formatting.js" >}}
