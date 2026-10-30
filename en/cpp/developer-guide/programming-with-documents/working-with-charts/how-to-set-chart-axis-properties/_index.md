---
title: How to Set Chart Axis Properties in C++
second_title: Aspose.Words for C++
articleTitle: How to Set Chart Axis Properties
linktitle: How to Set Chart Axis Properties
description: "Chart axis tuning using C++."
type: docs
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/how-to-set-chart-axis-properties/
timestamp: 2024-01-27-14-07-04
---

If you want to work with chart axis, scaling, and display units for the value axis, please use [ChartAxis](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartaxis/), [AxisDisplayUnit](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/axisdisplayunit/), and [AxisScaling](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/axisscaling/) classes.

The following code example shows how to define X and Y‑axis properties:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-DefineXYAxisProperties.cpp" >}}

## How to Set Date‑Time Value of Axis

The following code example shows how to set date/time values to axis properties:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-SetDateTimeValuesToAxis.cpp" >}}

## How to Format Number Value of Axis

The following code example shows how to change the format of numbers on the value axis:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-SetNumberFormatForAxis.cpp" >}}

## How to Set Bounds of Axis

The `AxisBound` class represents a minimum or maximum bound of axis values. Bound can be specified as a numeric, date‑time or a special "auto" value.

The following code example shows how to set the bounds of an axis:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-SetboundsOfAxis.cpp" >}}

## How to Set Interval Unit Between Labels

The following code example shows how to set the interval unit between labels on an axis:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-SetIntervalUnitBetweenLabelsOnAxis.cpp" >}}

## How to Hide Chart Axis

If you want to show or hide the chart axis, you can simply achieve this by setting the value of the set_Hidden property.

The following code example shows how to hide the Y‑axis of the chart:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-HideChartAxis.cpp" >}}

## How to Align Chart Label

If you want to set a text alignment for multi‑line labels, you can simply achieve this by calling **AxisTickLabels::set_Alignment** on the axis tick labels (`ChartAxis::get_TickLabels()`). The following code example shows how to tick label alignment.

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Charts-WorkingWithChartAxis-TickMultiLineLabelAlignment.cpp" >}}

------ 

## FAQ

1. **Q:** How can I set date‑time values on a chart axis?  
   **A:** Pass an array of `System::DateTime` values as the X values when you add the series (`chart->get_Series()->Add(name, dates, values)`). Set the axis category type to `AxisCategoryType::Time` via `ChartAxis::set_CategoryType` and optionally define the major unit and base unit to control the spacing of the labels.

2. **Q:** How do I change the number format displayed on the value axis?  
   **A:** Call `ChartAxis::get_NumberFormat()->set_FormatCode` with a format string such as `"#,##0.00"` to control how numbers are rendered.

3. **Q:** How can I hide a specific axis in a chart?  
   **A:** Set the `Hidden` property of the desired `ChartAxis` to `true` (e.g., `chart->get_AxisY()->set_Hidden(true);`). The axis will no longer be drawn, but its data remains available for calculations.

4. **Q:** How do I set custom minimum and maximum bounds for an axis?  
   **A:** Use the `AxisBound` class to create lower and upper bounds. Assign them to the axis with `AxisScaling::set_Minimum` and `AxisScaling::set_Maximum`. You can pass a numeric value, a `DateTime`, or a default-constructed `AxisBound()` for automatic scaling.

5. **Q:** How can I align multi‑line tick labels on an axis?  
   **A:** Call `ChartAxis::get_TickLabels()->set_Alignment` with one of the `ParagraphAlignment` values (e.g., `ParagraphAlignment::Center`). This aligns each line of the label according to the chosen alignment.