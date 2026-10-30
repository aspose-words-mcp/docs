---
title: Creating OOXML Charts from Scratch
second_title: Aspose.Words for C++
articleTitle: Creating OOXML Charts from Scratch
linktitle: Creating OOXML Charts from Scratch
description: "How to create different charts in your document using C++."
type: docs
weight: 10
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/creating-ooxml-charts-from-scratch-using-aspose-words/
timestamp: 2024-01-27-14-07-04
---

## Creating OOXML Charts from Scratch using Aspose.Words

Aspose.Words provides the `InsertChart` method which was added into the `DocumentBuilder` class. So, let's see how to insert a simple column chart into the document using `DocumentBuilder->InsertChart` method:

### How to Insert Column chart

The code example given below shows how to insert a column chart.

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-CreateColumnChart-InsertSimpleColumnChart.cpp" >}}

The code produces the following result:

![insert-column-chart-aspose-words-cpp-1](creating-ooxml-charts-using-aspose-words-2.png)

There are four different overloads for series Add method, which was exposed to cover all possible variants of data sources for all chart types:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-CreateColumnChart-InsertColumnChart.cpp" >}}

The code produces the following result:

![insert-column-chart-aspose-words-cpp-2](creating-ooxml-charts-using-aspose-words-3.png)


### How to InsertScatterChart

The code example given below shows how to insert a scatter chart.

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-InsertScatterChart-InsertScatterChart.cpp" >}}

The code produces the following result:

![insert-scatter-chart-aspose-words-cpp-1](creating-ooxml-charts-using-aspose-words-4.png)


### How to Insert Area Chart

The code example given below shows how to insert an area chart.

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-InsertAreaChart-InsertAreaChart.cpp" >}}

The code produces the following result:

![insert-area-chart-aspose-words-cpp-1](creating-ooxml-charts-using-aspose-words-5.png)


### How to Insert Bubble Chart

The code example given below shows how to insert a bubble chart.

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-InsertBubbleChart-InsertBubbleChart.cpp" >}}

The code produces the following result:

![insert-bubble-chart-aspose-words-cpp-1](creating-ooxml-charts-from-scratch-using-aspose-words-1.png)

------ 

## FAQ

1. **Q:** How can I insert a chart at a specific location such as a bookmark?  
   **A:** Use a `DocumentBuilder` to move to the desired bookmark or paragraph first (e.g., `builder->MoveToBookmark(u"MyBookmark");`) and then call `builder->InsertChart(...)`. The chart will be placed exactly where the builder's cursor is positioned.

2. **Q:** After inserting a chart, how do I add data series and points to it?  
   **A:** Get the chart from the inserted shape (`auto chart = builder->InsertChart(...)->get_Chart();`). Then call `chart->get_Series()->Add(seriesName, categories, values)` to create a series with its values, and use `ChartSeries::get_DataPoints()` to format individual data points.

3. **Q:** Can I change the chart type after it has been inserted?  
   **A:** Aspose.Words has no API to change the type of an existing chart. Insert a new chart of the desired type with `DocumentBuilder::InsertChart` (e.g., `ChartType::Pie`) and remove the old chart shape.

4. **Q:** How do I set a chart title and axis labels?  
   **A:** Use `chart->get_Title()->set_Text(u"Sales Overview");` for the main title. For axes, use the axis titles: `chart->get_AxisX()->get_Title()->set_Text(u"Month");` and `chart->get_AxisY()->get_Title()->set_Text(u"Revenue");`, and call `set_Show(true)` on each axis title (axis titles are hidden by default).

5. **Q:** Why does the chart appear blank or without data in the generated document?  
   **A:** Ensure that you add at least one series with data points before saving the document. Also verify that the chart's width and height are non‑zero (e.g., `builder->InsertChart(ChartType::Column, 400, 300);`). Missing series or zero size will result in an empty chart.