---
title: Working with Images in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Images
linktitle: Working with Images
description: "Create and manage images of various formats in a document using Node.js."
type: docs
weight: 300
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-images/
timestamp: 2025-07-09-10-05-05
---

Aspose.Words allows users to work with images in a very flexible way. In this article, you can explore only some of the possibilities of working with images.

## Inserting an Image

[DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) provides several overloads of the [insertImage](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertimage/) method that allows you to insert an inline or floating image. If the image is an EMF or WMF metafile, it will be inserted into the document in metafile format. All other images will be stored in PNG format. The **insertImage** method can use images from different sources:

- From a file or `URL` by passing a string parameter
- From a stream by passing a `Stream` parameter
- From a byte array by passing a byte array parameter

For each of the **insertImage** methods, there are further overloads which allow you to insert an image with the following options:
- Inline or floating at a specific position, for example, **insertImage**
- Percentage scale or custom size, furthermore, the [DocumentBuilder.insertImage](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertImage/) method returns a [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) object that was just created and inserted so you can further modify properties of the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/)

### Inserting an Inline Image

Pass a single string representing a file that contains the image to [insertImage](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertimage/) to insert the image into the document as an inline graphic.

The following code example shows how to insert an inline image at the cursor position into a document:

{{< gist "aspose-words-gists" "e2b8f833f9ab5de7c0598ddfd0ab1414" "insert-inline-image.js" >}}

### Inserting a Floating (Absolutely Positioned) Image

The following code example shows how to insert a floating image from a file or `URL` at a specified position and size:

{{< gist "aspose-words-gists" "e2b8f833f9ab5de7c0598ddfd0ab1414" "insert-floating-image.js" >}}

## How to Extract Images from a Document

All images are stored inside [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) nodes in a [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/). To extract all images or images having specific type from the document, follow these steps:

- Use the [Document.getChildNodes](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/getChildNodes/) method to select all [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) nodes.
- Iterate through resulting node collections.
- Check the [Shape.hasImage](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/hasimage/) boolean property.
- Extract image data using the [Shape.imageData](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/imagedata/) property.
- Save image data to a file.

The following code example shows how to extract images from a document and save them as files:

{{< gist "aspose-words-gists" "433f5122fe18fdc24a406528b70b0020" "extract-images.js" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Images.docx).

{{% /alert %}}

## How to Insert Barcode on each Page of a Document

This example demonstrates you to add the same or different barcodes on all or specific pages of a Word document. There is no direct way to add barcodes on all pages of a document but you can use the [moveToSection](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/moveToSection/), [moveToHeaderFooter](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/moveToHeaderFooter/) and [insertImage](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertimage/) methods to move to any section or headers/footers and insert the barcode images as you can see in the following code.

The following code example shows how to insert a barcode image on each page of a document:

{{< gist "aspose-words-gists" "e2b8f833f9ab5de7c0598ddfd0ab1414" "insert-barcode-image.js" >}}

{{< gist "aspose-words-gists" "e2b8f833f9ab5de7c0598ddfd0ab1414" "insert-barcode-into-footer.js" >}}

## Lock Aspect Ratio of Image

The aspect ratio of a geometric shape is the ratio of its sizes in different dimensions. You can lock the aspect ratio of the image using [aspectRatioLocked](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/aspectratiolocked/). The default value of the shape's aspect ratio depends on the [ShapeType](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/). It is `True` for [ShapeType.Image](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/) and `False` for other shape types.

The following code example shows how to work with aspect ratio:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "aspect-ratio-locked.js" >}}

## How to Get Actual Bounds of Shape in Points

If you want the actual bounding box of the shape as rendered on the page, you can achieve this by using the [boundsInPoints2](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/noderendererbase/boundsinpoints2/) property.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "get-actual-shape-bounds-points.js" >}}

## Crop Images

The cropping of an image usually refers to the removal of the unwanted outer parts of an image to help improve the framing. It is also used for the removal of some of the portions of an image to increase the focus on a particular area.

The following code example shows how to achieve this using Aspose.Words API:

{{< gist "aspose-words-gists" "e2b8f833f9ab5de7c0598ddfd0ab1414" "crop-images.js" >}}

## Saving Images as WMF

Aspose.Words provides functionality to save all the available images in a document to [WMF](https://docs.fileformat.com/image/wmf/) format while converting DOCX to RTF.

The following code example shows how to save images as WMF with RTF save options:

{{< gist "aspose-words-gists" "e2b8f833f9ab5de7c0598ddfd0ab1414" "saving-images-as-wmf.js" >}}
