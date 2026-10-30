---
title: Table Position in Python
second_title: Aspose.Words for Python
articleTitle: Position a Table
linktitle: Position a Table
description: "Specify table position in Python. Get a table alignment, get and set floating table position using Python."
type: docs
weight: 50
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/position-a-table/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to use Aspose.Words for Python to retrieve and modify the alignment, position, and surrounding‑text distances of both inline and floating tables, with code examples for each operation.
{{% /alert %}}

There are floating tables and inline tables:

* **Inline tables** are placed on the same layer as the text and are placed in a flow of text that only surrounds the table above and below. Inline tables will always appear between the paragraphs where you placed them.
* **Floating tables** are layered over the text, and the position of the table relative to the paragraph is determined by the table anchor. Because of this, the position of the floating table in the document is affected by the vertical and horizontal positioning settings.

Sometimes you need to position a table in a document in a certain way. To do this, you need to use the alignment tools and set the indents between the table and the surrounding text.

In this article, we will discuss what options Aspose.Words provides for positioning.

## Specify Inline Table Position

You can set the position of an inline table using the Aspose.Words API and the [alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/alignment/) property. Thus, you can adjust the alignment of the table relative to the document page.

The following code example shows how to set the position of an inline table:

{{< gist "aspose-words-gists" "1768d04dbe9222138611d5ad4047beef" "inline-table-position.py" >}}

## Get Floating Table Alignment

If the table text wrapping is set to **Around**, you can get the table's horizontal and vertical alignment using the [relative_horizontal_alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/relative_horizontal_alignment/) and [relative_vertical_alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/relative_vertical_alignment/) properties.

With **other types of text wrapping**, you can get inline table alignment using the [alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/alignment/) property.

The following code example shows how to get the table's alignment:

{{< gist "aspose-words-gists" "1768d04dbe9222138611d5ad4047beef" "get-table-position.py" >}}

## Get Floating Table Position

 The position of a floating table is determined using the following properties: 

* [horizontal_anchor](https://reference.aspose.com/words/python-net/aspose.words.tables/table/horizontal_anchor/) – an object for calculating the horizontal positioning of a floating table
* [vertical_anchor](https://reference.aspose.com/words/python-net/aspose.words.tables/table/vertical_anchor/) – an object for calculating the vertical positioning of a floating table
* [absolute_horizontal_distance](https://reference.aspose.com/words/python-net/aspose.words.tables/table/absolute_horizontal_distance/) – absolute horizontal floating table position
* [absolute_vertical_distance](https://reference.aspose.com/words/python-net/aspose.words.tables/table/absolute_vertical_distance/) – absolute vertical floating table position
* [allow_overlap](https://reference.aspose.com/words/python-net/aspose.words.tables/table/allow_overlap/) – option to enable/disable overlap with other floating objects
* [relative_horizontal_alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/relative_horizontal_alignment/) – floating table relative horizontal alignment.
* [relative_vertical_alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/relative_vertical_alignment/) – floating table relative vertical alignment.

The following code example shows how to get the position of a floating table:

{{< gist "aspose-words-gists" "1768d04dbe9222138611d5ad4047beef" "get-floating-table-position.py" >}}

## Set Floating Table Position

Just like getting, you can set the position of a floating table using the same Aspose.Words API.

It is important to know that alignment and horizontal and vertical distance are combined properties and one can reset the other. For example, setting the **relative_horizontal_alignment** will reset the **absolute_horizontal_distance** to its default value and vice versa. The same is true for the vertical arrangement.

The following code example shows how to set the position of a floating table:

{{< gist "aspose-words-gists" "1768d04dbe9222138611d5ad4047beef" "floating-table-position.py" >}}

## Get Distance between Table and Surrounding Text

Aspose.Words also provides an opportunity to find out the distances between tables and surrounding texts:

- [distance_top](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_top/) – the value of the distance from above
- [distance_bottom](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_bottom/) – the value of the distance of perception
- [distance_right](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_right/) – distance value on the right
- [distance_left](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_left/) – distance value on the left

The following code example shows how to get the distance between a table and its surrounding text:

{{< gist "aspose-words-gists" "1768d04dbe9222138611d5ad4047beef" "distance-between-table-surrounding-text.py" >}}

## Limitations and Considerations

Limitations and considerations for table positioning in Aspose.Words include:

* Horizontal and vertical alignment properties (`relative_horizontal_alignment`, `relative_vertical_alignment`) and distance properties (`absolute_horizontal_distance`, `absolute_vertical_distance`) are interdependent. Setting one property in each pair will reset the other to its default value.
* Inline tables can only be positioned using the `alignment` property and cannot be freely positioned like floating tables.
* Floating tables require proper anchor setup and their position is always relative to a paragraph anchor, even when using absolute distances.
* The `allow_overlap` property only affects the visual layering of floating objects and does not prevent layout conflicts.
* Distance properties (`distance_top`, `distance_bottom`, etc.) apply to both inline and floating tables but may behave differently depending on text wrapping settings.

## Related APIs

- [Table.alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/alignment/)
- [Table.relative_horizontal_alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/relative_horizontal_alignment/)
- [Table.relative_vertical_alignment](https://reference.aspose.com/words/python-net/aspose.words.tables/table/relative_vertical_alignment/)
- [Table.horizontal_anchor](https://reference.aspose.com/words/python-net/aspose.words.tables/table/horizontal_anchor/)
- [Table.vertical_anchor](https://reference.aspose.com/words/python-net/aspose.words.tables/table/vertical_anchor/)
- [Table.absolute_horizontal_distance](https://reference.aspose.com/words/python-net/aspose.words.tables/table/absolute_horizontal_distance/)
- [Table.absolute_vertical_distance](https://reference.aspose.com/words/python-net/aspose.words.tables/table/absolute_vertical_distance/)
- [Table.allow_overlap](https://reference.aspose.com/words/python-net/aspose.words.tables/table/allow_overlap/)
- [Table.distance_top](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_top/)
- [Table.distance_bottom](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_bottom/)
- [Table.distance_left](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_left/)
- [Table.distance_right](https://reference.aspose.com/words/python-net/aspose.words.tables/table/distance_right/) 

## FAQ

1. **Q:** How can I change the alignment of an inline table?  
   **A:** Use the `Table.alignment` property. Set it to one of the `TableAlignment` enum values such as `CENTER`, `LEFT`, or `RIGHT` to align the table relative to the page margins.

2. **Q:** Which properties let me read the alignment of a floating table?  
   **A:** For floating tables with text wrapping set to **Around**, read `Table.relative_horizontal_alignment` and `Table.relative_vertical_alignment`. These return values from the `HorizontalAlignment` and `VerticalAlignment` enums (`aw.drawing` module).

3. **Q:** What is the correct way to position a floating table at a specific location?  
   **A:** Set the appropriate anchor (`Table.horizontal_anchor`, `Table.vertical_anchor`) and then specify either the absolute distances (`Table.absolute_horizontal_distance`, `Table.absolute_vertical_distance`) **or** the relative alignments. Remember that changing a relative alignment resets the corresponding absolute distance to its default.

4. **Q:** How can I obtain the distances between a table and the surrounding text?  
   **A:** Use the four distance properties: `Table.distance_top`, `Table.distance_bottom`, `Table.distance_left`, and `Table.distance_right`. Each returns the distance in points.

5. **Q:** How do I change the text wrapping mode of a table to enable floating positioning?  
   **A:** Set the `Table.text_wrapping` property to `TextWrapping.AROUND`. After that, you can manipulate the floating‑table properties such as anchors, distances, and alignments.