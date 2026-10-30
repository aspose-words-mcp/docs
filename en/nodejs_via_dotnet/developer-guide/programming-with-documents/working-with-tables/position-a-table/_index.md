---
title: Table Position in Node.js
second_title: Aspose.Words for Node.js
articleTitle: Position a Table
linktitle: Position a Table
description: "Specify table position in Node.js. Get a table alignment, get and set floating table position using Node.js."
type: docs
weight: 50
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/position-a-table/
timestamp: 2025-07-09-10-05-05
---

There are floating tables and inline tables:

* **Inline tables** are placed on the same layer as the text and are placed in a flow of text that only surrounds the table above and below. Inline tables will always appear between the paragraphs where you placed them.
* **Floating tables** are layered over the text, and the position of the table relative to the paragraph is determined by the table anchor. Because of this, the position of the floating table in the document is affected by the vertical and horizontal positioning settings.

Sometimes you need to position a table in a document in a certain way. To do this, you need to use the alignment tools and set the indents between the table and the surrounding text.

In this article, we will discuss what options Aspose.Words provides for positioning.

## Specify Inline Table Position

You can set the position of an inline table using the Aspose.Words API and the [alignment](https://reference.aspose.com/words/nodejs-net/aspose.words/table/alignment/) property. Thus, you can adjust the alignment of the table relative to the document page.

The following code example shows how to set the position of an inline table:

{{< gist "aspose-words-gists" "b55c18ec2f5fe3f033f8d24c508b6a0f" "inline-table-position.js" >}}

## Get Floating Table Alignment

If the table text wrapping is set to **Around**, you can get the table's horizontal and vertical alignment using the [relativeHorizontalAlignment](https://reference.aspose.com/words/nodejs-net/aspose.words/table/relativeHorizontalAlignment/) and [relativeVerticalAlignment](https://reference.aspose.com/words/nodejs-net/aspose.words/table/relativeVerticalAlignment/) properties.

With **other types of text wrapping**, you can get inline table alignment using the [alignment](https://reference.aspose.com/words/nodejs-net/aspose.words/table/alignment/) property.

The following code example shows how to get the table's alignment:

{{< gist "aspose-words-gists" "b55c18ec2f5fe3f033f8d24c508b6a0f" "get-table-position.js" >}}

## Get Floating Table Position

 The position of a floating table is determined using the following properties: 

* [horizontalAnchor](https://reference.aspose.com/words/nodejs-net/aspose.words/table/horizontalAnchor/) – an object for calculating the horizontal positioning of a floating table
* [verticalAnchor](https://reference.aspose.com/words/nodejs-net/aspose.words/table/verticalAnchor/) – an object for calculating the vertical positioning of a floating table
* [absoluteHorizontalDistance](https://reference.aspose.com/words/nodejs-net/aspose.words/table/absoluteHorizontalDistance/) – absolute horizontal floating table position
* [absoluteVerticalDistance](https://reference.aspose.com/words/nodejs-net/aspose.words/table/absoluteVerticalDistance/) – absolute vertical floating table position
* [allowOverlap](https://reference.aspose.com/words/nodejs-net/aspose.words/table/allowOverlap/) – option to enable/disable overlap with other floating objects
* [relativeHorizontalAlignment](https://reference.aspose.com/words/nodejs-net/aspose.words/table/relativeHorizontalAlignment/) – floating table relative horizontal alignment.
* [relativeVerticalAlignment](https://reference.aspose.com/words/nodejs-net/aspose.words/table/relativeVerticalAlignment/) – floating table relative vertical alignment.

The following code example shows how to get the position of a floating table:

{{< gist "aspose-words-gists" "b55c18ec2f5fe3f033f8d24c508b6a0f" "get-floating-table-position.js" >}}

## Set Floating Table Position

Just like getting, you can set the position of a floating table using the same Aspose.Words API.

It is important to know that alignment and horizontal and vertical distance are combined properties and one can reset the other. For example, setting the **relativeHorizontalAlignment** will reset the **absoluteHorizontalDistance** to its default value and vice versa. The same is true for the vertical arrangement.

The following code example shows how to set the position of a floating table:

{{< gist "aspose-words-gists" "b55c18ec2f5fe3f033f8d24c508b6a0f" "floating-table-position.js" >}}

## Get Distance between Table and Surrounding Text

Aspose.Words also provides an opportunity to find out the distances between tables and surrounding texts:

- [distanceTop](https://reference.aspose.com/words/nodejs-net/aspose.words/table/distanceTop/) – the value of the distance from above
- [distanceBottom](https://reference.aspose.com/words/nodejs-net/aspose.words/table/distanceBottom/) – the value of the distance of perception
- [distanceRight](https://reference.aspose.com/words/nodejs-net/aspose.words/table/distanceRight/) – distance value on the right
- [distanceLeft](https://reference.aspose.com/words/nodejs-net/aspose.words/table/distanceLeft/) – distance value on the left

The following code example shows how to get the distance between a table and its surrounding text:

{{< gist "aspose-words-gists" "b55c18ec2f5fe3f033f8d24c508b6a0f" "distance-between-table-surrounding-text.js" >}}

------ 

## FAQ

1. **Q:** How can I change the horizontal alignment of a floating table in Node.js?  
   **A:** Use the `relativeHorizontalAlignment` property of the `Table` object. Assign a value from the `HorizontalAlignment` enum (e.g., `HorizontalAlignment.Left`). Setting this property automatically resets any previously set `absoluteHorizontalDistance`.

2. **Q:** Which property controls the vertical distance of a floating table from its anchor paragraph?  
   **A:** The `absoluteVerticalDistance` property defines the exact vertical offset (in points) from the anchor. You can set it directly, but note that changing `relativeVerticalAlignment` will reset this value to its default.

3. **Q:** How do I prevent a floating table from overlapping other floating objects?  
   **A:** Aspose.Words cannot change this option: the `allowOverlap` property is read-only. It shows whether the floating table allows other floating objects to overlap it (`true` by default); change the setting in Microsoft Word if needed.

4. **Q:** Can I retrieve the distances between a table and surrounding text?  
   **A:** Yes. Use the `distanceTop`, `distanceBottom`, `distanceLeft`, and `distanceRight` properties of the `Table` object. They return the spacing (in points) that the table maintains on each side.

5. **Q:** What is the difference between `horizontalAnchor` and `relativeHorizontalAlignment`?  
   **A:** `horizontalAnchor` specifies the reference point (e.g., page, margin, column) used for positioning the table. `relativeHorizontalAlignment` defines how the table aligns relative to that anchor (left, center, right). Both must be set appropriately to achieve the desired placement.