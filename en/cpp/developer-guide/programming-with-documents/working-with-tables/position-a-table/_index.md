---
title: Table Position in C++
second_title: Aspose.Words for C++
articleTitle: Position a Table
linktitle: Position a Table
description: "Specify table position in C++. Get a table alignment, get and set floating table position using C++."
type: docs
weight: 50
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/position-a-table/
timestamp: 2024-01-27-14-07-04
---

There are floating tables and inline tables:

* **Inline tables** are placed on the same layer as the text and are placed in a flow of text that only surrounds the table above and below. Inline tables will always appear between the paragraphs where you placed them.
* **Floating tables** are layered over the text, and the position of the table relative to the paragraph is determined by the table anchor. Because of this, the position of the floating table in the document is affected by the vertical and horizontal positioning settings.

Sometimes you need to position a table in a document in a certain way. To do this, you need to use the alignment tools and set the indents between the table and the surrounding text.

In this article, we will discuss what options Aspose.Words provides for positioning.

## Specify Inline Table Position

You can set the position of an inline table using the Aspose.Words API and the [get_Alignment()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_alignment/) property. Thus, you can adjust the alignment of the table relative to the document page.

The following code example shows how to set the position of an inline table:

{{< gist "aspose-words-gists" "eb66dfc4c4820add33be9df57ba4c4cd" "inline-table-position.h" >}}

## Get Floating Table Alignment

If the table text wrapping is set to **Around**, you can get the table's horizontal and vertical alignment using the [get_RelativeHorizontalAlignment()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_relativehorizontalalignment/) and [get_RelativeVerticalAlignment()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_relativeverticalalignment/) properties.

With **other types of text wrapping**, you can get inline table alignment using the [get_Alignment()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_alignment/) property.

The following code example shows how to get the table's alignment:

{{< gist "aspose-words-gists" "eb66dfc4c4820add33be9df57ba4c4cd" "get-table-position.h" >}}

## Get Floating Table Position

 The position of a floating table is determined using the following properties: 

* [get_HorizontalAnchor()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_horizontalanchor/) – an object for calculating the horizontal positioning of a floating table
* [get_VerticalAnchor()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_verticalanchor/) – an object for calculating the vertical positioning of a floating table
* [get_AbsoluteHorizontalDistance()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_absolutehorizontaldistance/) – absolute horizontal floating table position
* [get_AbsoluteVerticalDistance()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_absoluteverticaldistance/) – absolute vertical floating table position
* [get_AllowOverlap()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_allowoverlap/) – option to enable/disable overlap with other floating objects
* [get_RelativeHorizontalAlignment()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_relativehorizontalalignment/) – floating table relative horizontal alignment.
* [get_RelativeVerticalAlignment()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_relativeverticalalignment/) –  floating table relative vertical alignment.

The following code example shows how to get the position of a floating table:

{{< gist "aspose-words-gists" "eb66dfc4c4820add33be9df57ba4c4cd" "get-floating-table-position.h" >}}

## Set Floating Table Position

Just like getting, you can set the position of a floating table using the same Aspose.Words API.

It is important to know that alignment and horizontal and vertical distance are combined properties and one can reset the other. For example, setting the **set_RelativeHorizontalAlignment()** will reset the **get_AbsoluteHorizontalDistance()** to its default value and vice versa. The same is true for the vertical arrangement.

The following code example shows how to set the position of a floating table:

{{< gist "aspose-words-gists" "eb66dfc4c4820add33be9df57ba4c4cd" "floating-table-position.h" >}}

## Get Distance between Table and Surrounding Text

Aspose.Words also provides an opportunity to find out the distances between tables and surrounding texts:

- [get_DistanceTop()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_distancetop/) – the value of the distance from above
- [get_DistanceBottom()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_distancebottom/) – the value of the distance of perception
- [get_DistanceRight()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_distanceright/) – distance value on the right
- [get_DistanceLeft()](https://reference.aspose.com/words/cpp/aspose.words.tables/table/get_distanceleft/) – distance value on the left

The following code example shows how to get the distance between a table and its surrounding text:

{{< gist "aspose-words-gists" "eb66dfc4c4820add33be9df57ba4c4cd" "distance-between-table-surrounding-text.h" >}}

------ 

## FAQ

1. **Q:** How do I change the alignment of an inline table?  
   **A:** Use the `Table::set_Alignment()` method and pass one of the `TableAlignment` enum values (e.g., `TableAlignment::Center`). This aligns the table relative to the page margins.

2. **Q:** Which properties let me read the horizontal and vertical alignment of a floating table?  
   **A:** Retrieve `Table::get_RelativeHorizontalAlignment()` and `Table::get_RelativeVerticalAlignment()`. They return `HorizontalAlignment` and `VerticalAlignment` enum values that describe the table's placement.

3. **Q:** How can I set the exact position of a floating table?  
   **A:** Set the anchor properties (`get_HorizontalAnchor()`, `get_VerticalAnchor()`) and then specify distances with `get_AbsoluteHorizontalDistance()` and `get_AbsoluteVerticalDistance()`. For example:  
   ```cpp
   System::SharedPtr<Aspose::Words::Tables::Table> table = doc->get_FirstSection()->get_Body()->get_Tables()->idx_get(0);
   table->set_HorizontalAnchor(Aspose::Words::Drawing::RelativeHorizontalPosition::Page);
   table->set_VerticalAnchor(Aspose::Words::Drawing::RelativeVerticalPosition::Paragraph);
   table->set_AbsoluteHorizontalDistance(72.0); // 1 inch
   table->set_AbsoluteVerticalDistance(36.0);   // 0.5 inch
   ```

4. **Q:** What method returns the distances between a table and surrounding text?  
   **A:** Use `Table::get_DistanceTop()`, `Table::get_DistanceBottom()`, `Table::get_DistanceLeft()`, and `Table::get_DistanceRight()`. Each returns the distance in points, which you can convert to inches or centimeters as needed.

5. **Q:** Why does setting `set_RelativeHorizontalAlignment()` reset `get_AbsoluteHorizontalDistance()`?  
   **A:** In Aspose.Words, alignment and absolute distance are mutually exclusive for floating tables. Changing one automatically clears the other to avoid contradictory positioning. Set either alignment **or** absolute distances, but not both simultaneously.