---
title: Working with Images in Java
second_title: Aspose.Words for Java
articleTitle: Working with Images
linktitle: Working with Images
description: "Image shapes in details and advanced features provided by Aspose.Words for Java."
type: docs
weight: 300
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-images/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with images inside Word documents.

{{% /alert %}}

Aspose.Words allows users to work with images in a very flexible way. In this article, you can explore only some of the possibilities of working with images.

## How to Insert an Image {#insert-an-image}

[DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) provides several overloads of the [insertImage()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertImage-java.lang.String) method that allows you to insert an inline or floating image. If the image is an EMF or WMF metafile, it will be inserted into the document in metafile format. All other images will be stored in PNG format. The **insertImage()** method can use images from different sources:

- From a file or `URL` by passing a `String` parameter [insertImage()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertImage-java.lang.String)
- From a stream by passing a `Stream` parameter **insertImage()**
- From an Image object by passing an Image parameter **insertImage()**
- From a byte array by passing a byte array parameter **insertImage()**

For each of the **insertImage()** methods, there are further overloads which allow you to insert an image with the following options:
- Inline or floating at a specific position, for example, **insertImage()**
- Percentage scale or custom size, for example, **insertImage()**; furthermore, the **insertImage()** method returns a [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/) object that was just created and inserted so you can further modify properties of the Shape

### How to Insert an Inline Image {#insert-an-inline-image}

Pass a single string representing a file that contains the image to **insertImage()** to insert the image into the document as an inline graphic.

The following code example shows how to insert an inline image at the cursor position into a document:

{{< gist "aspose-words-gists" "5b273ed7ba940f81b6a42a3a78609316" "insert-inline-image.java" >}}

### How to Insert a Floating Image  {#insert-a-floating-image}

The following code example shows how to insert a floating image from a file or `URL` at a specified position and size:

{{< gist "aspose-words-gists" "5b273ed7ba940f81b6a42a3a78609316" "insert-floating-image.java" >}}

## How to Extract Images from a Document {#how-to-extract-images-from-a-document}

All images are stored inside **Shape** nodes in a [Document](https://reference.aspose.com/words/java/com.aspose.words/document/). To extract all images or images having specific type from the document, follow these steps:

- Use the [getChildNodes()](https://reference.aspose.com/words/java/com.aspose.words/compositenode/#getChildNodes-int-boolean) method to select all **Shape** nodes.
- Iterate through resulting node collections.
- Check the [hasImage()](https://reference.aspose.com/words/java/com.aspose.words/shape/#hasImage) boolean property.
- Extract image data using the [getImageData()](https://reference.aspose.com/words/java/com.aspose.words/shape/#getImageData) property.
- Save image data to a file.

The following code example shows how to extract images from a document and save them as files:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-images.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Images.docx).

{{% /alert %}}

## How to Insert Barcode on each Document Page {#how-to-insert-barcode-on-each-documen-page}

This example demonstrates you to add the same or different barcodes on all or specific pages of a Word document. There is no direct way to add barcodes on all pages of a document but you can use the **moveToSection()**, **moveToHeaderFooter()** and **insertImage()** methods to move to any section or headers/footers and insert the barcode images as you can see in the following code.

The following code example shows how to insert a barcode image on each page of a document:

{{< gist "aspose-words-gists" "5b273ed7ba940f81b6a42a3a78609316" "insert-barcode-image.java" >}}

{{< gist "aspose-words-gists" "5b273ed7ba940f81b6a42a3a78609316" "insert-barcode-into-footer.java" >}}

## Lock Aspect Ratio of Image {#lock-aspect-ratio-of-image}

The aspect ratio of a geometric shape is the ratio of its sizes in different dimensions. You can lock the aspect ratio of the image using [getAspectRatioLocked()](https://reference.aspose.com/words/java/com.aspose.words/shapebase/#getAspectRatioLocked). The default value of the shape's aspect ratio depends on the [ShapeType](https://reference.aspose.com/words/java/com.aspose.words/shapetype/).

The following code example shows how to work with aspect ratio:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "aspect-ratio-locked.java" >}}

## How to Get Actual Bounds of Shape in Points {#how-to-get-actual-bounds-of-shape-in-points}

If you want the actual bounding box of the shape as rendered on the page, you can achieve this by using the [getBoundsInPoints()](https://reference.aspose.com/words/java/com.aspose.words/noderendererbase/#getBoundsInPoints) property.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "get-actual-shape-bounds-points.java" >}}

## Crop Images {#crop-images}

The cropping of an image usually refers to the removal of the unwanted outer parts of an image to help improve the framing. It is also used for the removal of some of the portions of an image to increase the focus on a particular area.

The following code example shows how to achieve this using Aspose.Words API:

{{< gist "aspose-words-gists" "5b273ed7ba940f81b6a42a3a78609316" "crop-images.java" >}}

## Save Images as WMF {#save-images-as-wmf}

Aspose.Words provides functionality to save all the available images in a document to [WMF](https://docs.fileformat.com/image/wmf/) format while converting DOCX to RTF.

The following code example shows how to save images as WMF with RTF save options:

{{< gist "aspose-words-gists" "5b273ed7ba940f81b6a42a3a78609316" "saving-images-as-wmf.java" >}}

## Related APIs

- [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/)
- [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/)
- [ShapeBase](https://reference.aspose.com/words/java/com.aspose.words/shapebase/)
- [getImageData()](https://reference.aspose.com/words/java/com.aspose.words/shape/#getImageData)
- [NodeRendererBase.getBoundsInPoints()](https://reference.aspose.com/words/java/com.aspose.words/noderendererbase/#getBoundsInPoints) 

## FAQ

1. **Q:** How can I extract all images from a Word document using Aspose.Words for Java?  
   **A:** Load the document, retrieve all `Shape` nodes with `document.getChildNodes(NodeType.SHAPE, true)`, iterate the collection, check `shape.hasImage()`, then obtain the image bytes via `shape.getImageData().getImageBytes()` and write them to files.

2. **Q:** What is the recommended way to add a barcode image to every page of a document?  
   **A:** Use `DocumentBuilder` to navigate to each section's header or footer with `moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY)` (or footer), then call `insertImage(byte[])` with the barcode image data. Repeat for all sections to place the barcode on each page.

3. **Q:** How do I lock the aspect ratio of an image after inserting it?  
   **A:** After inserting the image, the returned `Shape` object represents the picture. Call `shape.setAspectRatioLocked(true)` to keep the original width‑to‑height proportion when the shape is resized.

4. **Q:** Can I crop an image that is already inside a Word document?  
   **A:** Yes. Obtain the `Shape` that contains the image and use the cropping properties: `shape.getImageData().setCropTop(value)`, `setCropBottom(value)`, `setCropLeft(value)`, and `setCropRight(value)`. The values are specified as percentages (0.0 to 1.0).

5. **Q:** How can I save all images in a document as WMF when converting to RTF?  
   **A:** Create an `RtfSaveOptions` instance and call `options.setSaveImagesAsWmf(true)`. Then call `document.save("output.rtf", options)` to produce an RTF where all images are stored as WMF.