---
title: Table Position in C#
second_title: Aspose.Words for .NET
articleTitle: Position a Table
linktitle: Position a Table
description: "Specify table position in C#. Get a table alignment, get and set floating table position using C#."
type: docs
weight: 50
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/position-a-table/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to position tables precisely within a document using layout and formatting options.

{{% /alert %}}

There are floating tables and inline tables:

* **Inline tables** are placed on the same layer as the text and are placed in a flow of text that only surrounds the table above and below. Inline tables will always appear between the paragraphs where you placed them.
* **Floating tables** are layered over the text, and the position of the table relative to the paragraph is determined by the table anchor. Because of this, the position of the floating table in the document is affected by the vertical and horizontal positioning settings.

Sometimes you need to position a table in a document in a certain way. To do this, you need to use the alignment tools and set the indents between the table and the surrounding text.

In this article, we will discuss what options Aspose.Words provides for positioning.

## Specify Inline Table Position

You can set the position of an inline table using the Aspose.Words API and the [Alignment](https://reference.aspose.com/words/net/aspose.words.tables/table/alignment/) property. Thus, you can adjust the alignment of the table relative to the document page.

The following code example shows how to set the position of an inline table:

{{< gist "aspose-words-gists" "8df1ad0825619cab7c80b571c6e6ba99" "inline-table-position.cs" >}}

## Get Floating Table Alignment

If the table text wrapping is set to **Around**, you can get the table's horizontal and vertical alignment using the [RelativeHorizontalAlignment](https://reference.aspose.com/words/net/aspose.words.tables/table/relativehorizontalalignment/) and [RelativeVerticalAlignment](https://reference.aspose.com/words/net/aspose.words.tables/table/relativeverticalalignment/) properties.

With **other types of text wrapping**, you can get inline table alignment using the [Alignment](https://reference.aspose.com/words/net/aspose.words.tables/table/alignment/) property.

The following code example shows how to get the table's alignment:

{{< gist "aspose-words-gists" "8df1ad0825619cab7c80b571c6e6ba99" "get-table-position.cs" >}}

## Get Floating Table Position

 The position of a floating table is determined using the following properties: 

* [HorizontalAnchor](https://reference.aspose.com/words/net/aspose.words.tables/table/horizontalanchor/) – an object for calculating the horizontal positioning of a floating table
* [VerticalAnchor](https://reference.aspose.com/words/net/aspose.words.tables/table/verticalanchor/) – an object for calculating the vertical positioning of a floating table
* [AbsoluteHorizontalDistance](https://reference.aspose.com/words/net/aspose.words.tables/table/absolutehorizontaldistance/) – absolute horizontal floating table position
* [AbsoluteVerticalDistance](https://reference.aspose.com/words/net/aspose.words.tables/table/absoluteverticaldistance/) – absolute vertical floating table position
* [AllowOverlap](https://reference.aspose.com/words/net/aspose.words.tables/table/allowoverlap/) – option to enable/disable overlap with other floating objects
* [RelativeHorizontalAlignment](https://reference.aspose.com/words/net/aspose.words.tables/table/relativehorizontalalignment/) – floating table relative horizontal alignment.
* [RelativeVerticalAlignment](https://reference.aspose.com/words/net/aspose.words.tables/table/relativeverticalalignment/) –  floating table relative vertical alignment.

The following code example shows how to get the position of a floating table:

{{< gist "aspose-words-gists" "8df1ad0825619cab7c80b571c6e6ba99" "get-floating-table-position.cs" >}}

## Set Floating Table Position

Just like getting, you can set the position of a floating table using the same Aspose.Words API.

It is important to know that alignment and horizontal and vertical distance are combined properties and one can reset the other. For example, setting the **RelativeHorizontalAlignment** will reset the **AbsoluteHorizontalDistance** to its default value and vice versa. The same is true for the vertical arrangement.

The following code example shows how to set the position of a floating table:

{{< gist "aspose-words-gists" "8df1ad0825619cab7c80b571c6e6ba99" "floating-table-position.cs" >}}

## Get Distance between Table and Surrounding Text

Aspose.Words also provides an opportunity to find out the distances between tables and surrounding texts:

- [DistanceTop](https://reference.aspose.com/words/net/aspose.words.tables/table/distancetop/) – the value of the distance from above
- [DistanceBottom](https://reference.aspose.com/words/net/aspose.words.tables/table/distancebottom/) – the value of the distance of perception
- [DistanceRight](https://reference.aspose.com/words/net/aspose.words.tables/table/distanceright/) – distance value on the right
- [DistanceLeft](https://reference.aspose.com/words/net/aspose.words.tables/table/distanceleft/) – distance value on the left

The following code example shows how to get the distance between a table and its surrounding text:

{{< gist "aspose-words-gists" "8df1ad0825619cab7c80b571c6e6ba99" "distance-between-table-surrounding-text.cs" >}}

## Limitations and Considerations

Limitations and considerations for table positioning in Aspose.Words include:

* Horizontal and vertical alignment properties (`RelativeHorizontalAlignment`, `RelativeVerticalAlignment`) and distance properties (`AbsoluteHorizontalDistance`, `AbsoluteVerticalDistance`) are interdependent. Setting one property in each pair will reset the other to its default value.
* Inline tables can only be positioned using the `Alignment` property and cannot be freely positioned like floating tables.
* Floating tables require proper anchor setup and their position is always relative to a paragraph anchor, even when using absolute distances.
* The `AllowOverlap` property only affects the visual layering of floating objects and does not prevent layout conflicts.
* Distance properties (`DistanceTop`, `DistanceBottom`, etc.) apply to both inline and floating tables but may behave differently depending on text wrapping settings.

## Related APIs

- [Table.Alignment](https://reference.aspose.com/words/net/aspose.words.tables/table/alignment/)
- [Table.RelativeHorizontalAlignment](https://reference.aspose.com/words/net/aspose.words.tables/table/relativehorizontalalignment/)
- [Table.RelativeVerticalAlignment](https://reference.aspose.com/words/net/aspose.words.tables/table/relativeverticalalignment/)
- [Table.HorizontalAnchor](https://reference.aspose.com/words/net/aspose.words.tables/table/horizontalanchor/)
- [Table.VerticalAnchor](https://reference.aspose.com/words/net/aspose.words.tables/table/verticalanchor/)
- [Table.AbsoluteHorizontalDistance](https://reference.aspose.com/words/net/aspose.words.tables/table/absolutehorizontaldistance/)
- [Table.AbsoluteVerticalDistance](https://reference.aspose.com/words/net/aspose.words.tables/table/absoluteverticaldistance/)
- [Table.AllowOverlap](https://reference.aspose.com/words/net/aspose.words.tables/table/allowoverlap/)
- [Table.DistanceTop](https://reference.aspose.com/words/net/aspose.words.tables/table/distancetop/)
- [Table.DistanceBottom](https://reference.aspose.com/words/net/aspose.words.tables/table/distancebottom/)
- [Table.DistanceLeft](https://reference.aspose.com/words/net/aspose.words.tables/table/distanceleft/)
- [Table.DistanceRight](https://reference.aspose.com/words/net/aspose.words.tables/table/distanceright/)


## FAQ


1. **Q:** How do I set the alignment of an inline table?  
   **A:** Use the `Table.Alignment` property. For example, `Table.Alignment = TableAlignment.Center;` aligns the table to the center of the page. The property works only for inline tables.

2. **Q:** How can I retrieve the horizontal and vertical alignment of a floating table?  
   **A:** Access the `Table.RelativeHorizontalAlignment` and `Table.RelativeVerticalAlignment` properties. They return `HorizontalAlignment` and `VerticalAlignment` values, such as `HorizontalAlignment.Center`. What the floating table is positioned relative to comes from `Table.HorizontalAnchor` and `Table.VerticalAnchor`, which return values such as `RelativeHorizontalPosition.Page` or `RelativeVerticalPosition.Margin`.

3. **Q:** What properties are required to set the position of a floating table?  
   **A:** Set `HorizontalAnchor`, `VerticalAnchor`, `AbsoluteHorizontalDistance`, and `AbsoluteVerticalDistance`. You can also use `RelativeHorizontalAlignment` or `RelativeVerticalAlignment`. Note that changing an alignment property resets the corresponding absolute distance to its default.

4. **Q:** How can I control the distance between a table and the surrounding text?  
   **A:** Use the `DistanceTop`, `DistanceBottom`, `DistanceLeft`, and `DistanceRight` properties of the `Table` object. These properties specify the amount of space on each side of the table in points.

5. **Q:** What does the `AllowOverlap` property do for floating tables?  
   **A:** `AllowOverlap` tells whether the floating table allows other floating objects to overlap it when displayed (the default is `true`). The property is read-only: you can read the value stored in the document, but not change it.