---
title: Working with Watermark in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Watermark
linktitle: Working with Watermark
description: "Create and manage watermarks in a document using Node.js."
type: docs
weight: 340
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-watermark/
timestamp: 2025-07-09-10-05-05
---

This topic discusses how to work programmatically with watermark using Aspose.Words. A watermark is a background image that displays behind the text in a document. A watermark can contain a text or an image represented by the [Watermark](https://reference.aspose.com/words/nodejs-net/aspose.words/watermark/) class.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online document watermark](https://products.aspose.app/words/watermark).

{{% /alert %}}

## How to Add a Watermark to a Document

In Microsoft Word, a watermark can easily be inserted in a document using the Insert Watermark command. Aspose.Words provides the [Watermark](https://reference.aspose.com/words/nodejs-net/aspose.words/watermark/) class to add or remove watermark in documents. Aspose.Words provides the [WatermarkType](https://reference.aspose.com/words/nodejs-net/aspose.words/watermarktype/) enumeration defining three possible types of watermarks ([Text](https://reference.aspose.com/words/nodejs-net/aspose.words/watermarktype/), [Image](https://reference.aspose.com/words/nodejs-net/aspose.words/watermarktype/), and [None](https://reference.aspose.com/words/nodejs-net/aspose.words/watermarktype/)) to work with.

### Add Text Watermark

The following code example demonstrates how to insert a text watermark in a document by defining [TextWatermarkOptions](https://reference.aspose.com/words/nodejs-net/aspose.words/textwatermarkoptions/) using the [setText](https://reference.aspose.com/words/nodejs-net/aspose.words/watermark/setText/) method:

{{< gist "aspose-words-gists" "2936fee38a4d9a8256f95e4276400579" "add-text-watermark.js" >}}

### Add Image Watermark

The following code example demonstrates how to insert an image watermark in a document by defining [ImageWatermarkOptions](https://reference.aspose.com/words/nodejs-net/aspose.words/imagewatermarkoptions/) using the [setImage](https://reference.aspose.com/words/nodejs-net/aspose.words/watermark/setImage/#jsimage) method:

{{< gist "aspose-words-gists" "2936fee38a4d9a8256f95e4276400579" "add-image-watermark.js" >}}

Image watermark can be inserted as image, string, or stream.

The watermark can also be inserted using shape class as well. It is very easy to insert any shape or image into a header or footer and thus create a watermark of any imaginable type.

The following code example inserts a watermark into a Word document:

{{< gist "aspose-words-gists" "2936fee38a4d9a8256f95e4276400579" "add-document-watermark.js" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [here](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Document.docx).

{{% /alert %}}

## Remove Watermark from a Document

The [Watermark](https://reference.aspose.com/words/nodejs-net/aspose.words/watermark/) class provides the remove method to remove the watermark from a document.

The following code example shows how to remove a watermark from documents:

{{< gist "aspose-words-gists" "2936fee38a4d9a8256f95e4276400579" "remove-document-watermark.js" >}}

If the watermarks are added using the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) class object then to remove the watermark from a document you have to set only the name of watermark shape during inserting and then remove watermark shape by an assigned name.

The following code example show you how to set the name of the watermark shape and remove it from the document:

{{< gist "aspose-words-gists" "2936fee38a4d9a8256f95e4276400579" "set-shape-name.js" >}}

{{< gist "aspose-words-gists" "2936fee38a4d9a8256f95e4276400579" "remove-watermark-shape.js" >}}

## Add a Watermark in Table Cell

Sometimes you need to insert a watermark/image into a table's cell and display it outside the table, you can use the [isLayoutInCell](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/isLayoutInCell/) property. This property gets or sets a flag indicating whether the shape is displayed inside a table or outside of it. Note that this property works only when you optimize the document for Microsoft Word 2010 using the [optimizeFor](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/compatibilityoptions/optimizeFor/) method.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "layout-in-cell.js" >}}

------  

## FAQ

1. **Q:** How do I add a text watermark to a document using Node.js?  
   **A:** Configure a `TextWatermarkOptions` instance with the desired font, color, etc., and call `doc.watermark.setText("Your text", options)`. Finally, save the document.

2. **Q:** Can I insert an image as a watermark, and what formats are supported?  
   **A:** Yes. Call `doc.watermark.setImage(image, options)` with the image file name or a `Buffer` with the image data; `ImageWatermarkOptions` only sets the `scale` and `isWashout` options. All image formats supported by Aspose.Words (PNG, JPEG, BMP, GIF, TIFF) can be used.

3. **Q:** How can I remove a watermark that was added with the `Watermark` class?  
   **A:** Call `watermark.remove()` on the document's `Watermark` instance. This removes any watermark added via the `Watermark` API.

4. **Q:** My watermark was added using a `Shape`; how do I delete it?  
   **A:** When inserting the shape, assign a unique name (e.g., `watermarkShape.name = "MyWatermark"`). Later loop through `document.getChildNodes(aw.NodeType.Shape, true)`, cast each node with `node.asShape()`, and call `remove()` on the shape whose `name` is `"MyWatermark"`.

5. **Q:** Is it possible to place a watermark inside a table cell but have it appear outside the cell boundaries?  
   **A:** Set the shape's `isLayoutInCell` property to `false` and ensure the document compatibility is set to Word 2010 or later using `document.compatibilityOptions.optimizeFor(aw.Settings.MsWordVersion.Word2010)`. This makes the watermark render outside the cell while being anchored to it.