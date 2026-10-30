---
title: Table Position in Java
second_title: Aspose.Words for Java
articleTitle: Position a Table
linktitle: Position a Table
description: "Specify table position in Java. Get a table alignment, get and set floating table position using Java."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/position-a-table/
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

You can set the position of an inline table using the Aspose.Words API and the [getAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAlignment) property. Thus, you can adjust the alignment of the table relative to the document page.

The following code example shows how to set the position of an inline table:

{{< gist "aspose-words-gists" "0f235c484e5edae70a542ebdaae40fd8" "inline-table-position.java" >}}

## Get Floating Table Alignment

If the table text wrapping is set to **Around**, you can get the table's horizontal and vertical alignment using the [getRelativeHorizontalAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getRelativeHorizontalAlignment) and [getRelativeVerticalAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getRelativeVerticalAlignment) properties.

With **other types of text wrapping**, you can get inline table alignment using the [getAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAlignment) property.

The following code example shows how to get the table's alignment:

{{< gist "aspose-words-gists" "0f235c484e5edae70a542ebdaae40fd8" "get-table-position.java" >}}

## Get Floating Table Position

 The position of a floating table is determined using the following properties: 

* [getHorizontalAnchor()](https://reference.aspose.com/words/java/com.aspose.words/table/#getHorizontalAnchor) – an object for calculating the horizontal positioning of a floating table
* [getVerticalAnchor()](https://reference.aspose.com/words/java/com.aspose.words/table/#getVerticalAnchor) – an object for calculating the vertical positioning of a floating table
* [getAbsoluteHorizontalDistance()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAbsoluteHorizontalDistance) – absolute horizontal floating table position
* [getAbsoluteVerticalDistance()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAbsoluteVerticalDistance) – absolute vertical floating table position
* [getAllowOverlap()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAllowOverlap) – option to enable/disable overlap with other floating objects
* [getRelativeHorizontalAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getRelativeHorizontalAlignment) – floating table relative horizontal alignment.
* [getRelativeVerticalAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getRelativeVerticalAlignment) –  floating table relative vertical alignment.

The following code example shows how to get the position of a floating table:

{{< gist "aspose-words-gists" "0f235c484e5edae70a542ebdaae40fd8" "get-floating-table-position.java" >}}

## Set Floating Table Position

Just like getting, you can set the position of a floating table using the same Aspose.Words API.

It is important to know that alignment and horizontal and vertical distance are combined properties and one can reset the other. For example, setting the **getRelativeHorizontalAlignment()** will reset the **getAbsoluteHorizontalDistance()** to its default value and vice versa. The same is true for the vertical arrangement.

The following code example shows how to set the position of a floating table:

{{< gist "aspose-words-gists" "0f235c484e5edae70a542ebdaae40fd8" "floating-table-position.java" >}}

## Get Distance between Table and Surrounding Text

Aspose.Words also provides an opportunity to find out the distances between tables and surrounding texts:

- [getDistanceTop()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceTop) – the value of the distance from above
- [getDistanceBottom()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceBottom) – the value of the distance of perception
- [getDistanceRight()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceRight) – distance value on the right
- [getDistanceLeft()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceLeft) – distance value on the left

The following code example shows how to get the distance between a table and its surrounding text:

{{< gist "aspose-words-gists" "0f235c484e5edae70a542ebdaae40fd8" "distance-between-table-surrounding-text.java" >}}

## Limitations and Considerations

Limitations and considerations for table positioning in Aspose.Words include:

* Horizontal and vertical alignment properties (`getRelativeHorizontalAlignment()`, `getRelativeVerticalAlignment()`) and distance properties (`getAbsoluteHorizontalDistance()`, `getAbsoluteVerticalDistance()`) are interdependent. Setting one property in each pair will reset the other to its default value.
* Inline tables can only be positioned using the `Alignment` property and cannot be freely positioned like floating tables.
* Floating tables require proper anchor setup and their position is always relative to a paragraph anchor, even when using absolute distances.
* The `getAllowOverlap()` property only affects the visual layering of floating objects and does not prevent layout conflicts.
* Distance properties (`getDistanceTop()`, `getDistanceBottom()`, etc.) apply to both inline and floating tables but may behave differently depending on text wrapping settings.

## Related APIs

- [Table.getAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAlignment)
- [Table.getRelativeHorizontalAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getRelativeHorizontalAlignment)
- [Table.getRelativeVerticalAlignment()](https://reference.aspose.com/words/java/com.aspose.words/table/#getRelativeVerticalAlignment)
- [Table.getHorizontalAnchor()](https://reference.aspose.com/words/java/com.aspose.words/table/#getHorizontalAnchor)
- [Table.getVerticalAnchor()](https://reference.aspose.com/words/java/com.aspose.words/table/#getVerticalAnchor)
- [Table.getAbsoluteHorizontalDistance()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAbsoluteHorizontalDistance)
- [Table.getAbsoluteVerticalDistance()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAbsoluteVerticalDistance)
- [Table.getAllowOverlap()](https://reference.aspose.com/words/java/com.aspose.words/table/#getAllowOverlap)
- [Table.getDistanceTop()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceTop)
- [Table.getDistanceBottom()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceBottom)
- [Table.getDistanceLeft()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceLeft)
- [Table.getDistanceRight()](https://reference.aspose.com/words/java/com.aspose.words/table/#getDistanceRight)