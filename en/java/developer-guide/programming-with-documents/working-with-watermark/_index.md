---
title: Working with Watermark in Java
second_title: Aspose.Words for Java
articleTitle: Working with Watermark
linktitle: Working with Watermark
type: docs
description: "Document watermark manipulation using Java."
weight: 70
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-watermark/
aliases: [/java/how-to-add-a-watermark-to-a-document/]
timestamp: 2025-04-22-08-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with watermarks in Word documents.

{{% /alert %}}

This topic discusses how to work programmatically with watermark using Aspose.Words. A watermark is a background image that displays behind the text in a document. A watermark can contain a text or an image represented by the [Watermark](https://reference.aspose.com/words/java/com.aspose.words/watermark/) class.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online document watermark](https://products.aspose.app/words/watermark).

{{% /alert %}}

## Add a Watermark to a Document

In Microsoft Word, a watermark can easily be inserted in a document using the Insert Watermark command. Aspose.Words provides the [watermark](https://reference.aspose.com/words/java/com.aspose.words/watermark/) class to add or remove watermark in documents. Aspose.Words provides the [WatermarkType](https://reference.aspose.com/words/java/com.aspose.words/watermarktype/) enumeration defining three possible types of watermarks (Text, Image, and None) to work with.

### Add Text Watermark

The following code example demonstrates how to insert a text watermark in a document by defining [TextWatermarkOptions](https://reference.aspose.com/words/java/com.aspose.words/textwatermarkoptions/) using the [setText()](https://reference.aspose.com/words/java/com.aspose.words/watermark/#setText-java.lang.String) method:

{{< gist "aspose-words-gists" "45164877cf7053ae51abc84d2e3bc172" "add-text-watermark.java" >}}

### Add Image Watermark

The following code example demonstrates how to insert an image watermark in a document by defining [ImageWatermarkOptions](https://reference.aspose.com/words/java/com.aspose.words/imagewatermarkoptions/) using the [setImage()](https://reference.aspose.com/words/java/com.aspose.words/watermark/#setImage-java.awt.image.BufferedImage) method:

{{< gist "aspose-words-gists" "45164877cf7053ae51abc84d2e3bc172" "add-image-watermark.java" >}}

Image watermark can be inserted as image, string, or stream.

The watermark can also be inserted using shape class as well. It is very easy to insert any shape or image into a header or footer and thus create a watermark of any imaginable type.

The following code example inserts a watermark into a Word document:

{{< gist "aspose-words-gists" "45164877cf7053ae51abc84d2e3bc172" "add-document-watermark.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Document.docx).

{{% /alert %}}


## Remove Watermark from a Document

The [Watermark](https://reference.aspose.com/words/java/com.aspose.words/watermark/) class provides the remove method to remove the watermark from a document.

The following code example shows how to remove a watermark from documents:

{{< gist "aspose-words-gists" "45164877cf7053ae51abc84d2e3bc172" "remove-document-watermark.java" >}}

If the watermarks are added using the [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/) class object then to remove the watermark from a document you have to set only the name of watermark shape during inserting and then remove watermark shape by an assigned name.

The following code example show you how to set the name of the watermark shape and remove it from the document:

{{< gist "aspose-words-gists" "45164877cf7053ae51abc84d2e3bc172" "set-shape-name.java" >}}

{{< gist "aspose-words-gists" "45164877cf7053ae51abc84d2e3bc172" "remove-watermark-shape.java" >}}

## Add a Watermark into a Table Cell

Sometimes you need to insert a watermark/image into a table's cell and display it outside the table, you can use the [isLayoutInCell()](https://reference.aspose.com/words/java/com.aspose.words/shapebase/#isLayoutInCell-boolean) property. This property gets or sets a flag indicating whether the shape is displayed inside a table or outside of it. Note that this property works only when you optimize the document for Microsoft Word 2010 using the [optimizeFor()](https://reference.aspose.com/words/java/com.aspose.words/compatibilityoptions/#optimizeFor-int) method.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "layout-in-cell.java" >}}

## FAQ

1. **Q:** How can I add a watermark to only a specific page in a document?  
   **A:** Insert the watermark into a header/footer that is linked only to the desired page (e.g., using a different first‑page header). Set the watermark's `Name` property so you can later remove or modify it without affecting other pages.

2. **Q:** Can I control the opacity of a text or image watermark?  
   **A:** Not with an exact opacity value. For text watermarks, `TextWatermarkOptions.isSemitrasparent(true)` makes the text semi-transparent; for image watermarks, `ImageWatermarkOptions.isWashout(true)` applies a washout effect.

3. **Q:** How do I remove a watermark that was added without specifying a name?  
   **A:** Call `doc.getWatermark().remove()`; it removes the watermark added with `Watermark.setText` or `Watermark.setImage`, with or without a name. For a watermark shape you added yourself, naming it (`watermark.setName("MyMark")`) makes it easy to find and remove later.

4. **Q:** Is it possible to add a watermark inside a table cell and have it appear behind the cell's text?  
   **A:** Yes. Call `isLayoutInCell(false)` on the watermark shape and ensure the document is optimized for Word 2010 (`doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010)`). This places the watermark outside the cell layout while keeping it visually aligned with the table.

5. **Q:** Can I add a watermark to a document that is being generated in memory (without saving to disk first)?  
   **A:** Absolutely. Create a `Document` instance from a stream or from scratch, apply the watermark using the `Watermark` class, and then save the document directly to a `ByteArrayOutputStream` or any other output stream. No intermediate file is required.