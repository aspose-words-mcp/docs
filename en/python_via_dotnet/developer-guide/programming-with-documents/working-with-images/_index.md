---
title: Working with Images in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Images
linktitle: Working with Images
description: "Create and manage images of various formats in a document using Python."
type: docs
weight: 300
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-images/
aliases: [/python/working-with-images/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to insert, extract, modify, and save images in Word documents using Aspose.Words for Python via .NET, covering inline and floating insertion, barcode insertion, aspect‑ratio control, cropping, bounds retrieval, and format conversion.
{{% /alert %}}

Aspose.Words allows users to work with images in a very flexible way. In this article, you can explore only some of the possibilities of working with images.

## How to Insert an Image {#insert-an-image}

[DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) provides several overloads of the [insert_image](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_image/) method that allows you to insert an inline or floating image. If the image is an EMF or WMF metafile, it will be inserted into the document in metafile format. All other images will be stored in PNG format. The **insert_image** method can use images from different sources:

- From a file or `URL` by passing a `String` parameter [insert_image](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_image/)
- From a stream by passing a `Stream` parameter **insert_image**
- From an Image object by passing an Image parameter **insert_image**
- From a byte array by passing a byte array parameter **insert_image**

For each of the **insert_image** methods, there are further overloads which allow you to insert an image with the following options:
- Inline or floating at a specific position, for example, **insert_image**
- Percentage scale or custom size, for example, **insert_image**; furthermore, the **insert_image** method returns a [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) object that was just created and inserted so you can further modify properties of the Shape

### How to Insert an Inline Image {#insert-an-inline-image}

Pass a single string representing a file that contains the image to **insert_image** to insert the image into the document as an inline graphic.

The following code example shows how to insert an inline image at the cursor position into a document:

{{< gist "aspose-words-gists" "5336f9cc9b531d2102da9f79c959a5ee" "insert-inline-image.py" >}}

### How to Insert a Floating Image  {#insert-a-floating-image}

The following code example shows how to insert a floating image from a file or `URL` at a specified position and size:

{{< gist "aspose-words-gists" "5336f9cc9b531d2102da9f79c959a5ee" "insert-floating-image.py" >}}

## How to Extract Images from a Document {#how-to-extract-images-from-a-document}

All images are stored inside **Shape** nodes in a [Document](https://reference.aspose.com/words/python-net/aspose.words/document/). To extract all images or images having specific type from the document, follow these steps:

- Use the [Document.get_child_nodes](https://reference.aspose.com/words/python-net/aspose.words/compositenode/get_child_nodes/) method to select all **Shape** nodes.
- Iterate through resulting node collections.
- Check the [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) boolean property.
- Extract image data using the [Shape.has_image](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/has_image/) property.
- Save image data to a file.

The following code example shows how to extract images from a document and save them as files:

{{< gist "aspose-words-gists" "399801c9a5e656ed05aa2d7ac5ebc41e" "extract-images.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Images.docx).

{{% /alert %}}

## How to Insert Barcode on each Document Page {#how-to-insert-barcode-on-each-documen-page}

This example demonstrates you to add the same or different barcodes on all or specific pages of a Word document. There is no direct way to add barcodes on all pages of a document but you can use the **move_to_section**, **move_to_header_footer** and **insert_image** methods to move to any section or headers/footers and insert the barcode images as you can see in the following code.

The following code example shows how to insert a barcode image on each page of a document:

{{< gist "aspose-words-gists" "5336f9cc9b531d2102da9f79c959a5ee" "insert-barcode-image.py" >}}

{{< gist "aspose-words-gists" "5336f9cc9b531d2102da9f79c959a5ee" "insert-barcode-into-footer.py" >}}

## Lock Aspect Ratio of Image {#lock-aspect-ratio-of-image}

The aspect ratio of a geometric shape is the ratio of its sizes in different dimensions. You can lock the aspect ratio of the image using [aspect_ratio_locked](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/aspect_ratio_locked/). The default value of the shape's aspect ratio depends on the [ShapeType](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapetype/). It is `True` for [ShapeType.IMAGE](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapetype/#image) and `False` for other shape types.

The following code example shows how to work with aspect ratio:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "aspect-ratio-locked.py" >}}

## How to Get Actual Bounds of Shape in Points {#how-to-get-actual-bounds-of-shape-in-points}

If you want the actual bounding box of the shape as rendered on the page, you can achieve this by using the [bounds_in_points](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/bounds_in_points/) property.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "get-actual-shape-bounds-points.py" >}}

## Crop Images {#crop-images}

The cropping of an image usually refers to the removal of the unwanted outer parts of an image to help improve the framing. It is also used for the removal of some of the portions of an image to increase the focus on a particular area.

The following code example shows how to achieve this using Aspose.Words API:

{{< gist "aspose-words-gists" "5336f9cc9b531d2102da9f79c959a5ee" "crop-images.py" >}}

## Save Images as WMF {#save-images-as-wmf}

Aspose.Words provides functionality to save all the available images in a document to [WMF](https://docs.fileformat.com/image/wmf/) format while converting DOCX to RTF.

The following code example shows how to save images as WMF with RTF save options:

{{< gist "aspose-words-gists" "5336f9cc9b531d2102da9f79c959a5ee" "saving-images-as-wmf.py" >}}

## Related APIs

- [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/)
- [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/)
- [ShapeBase](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/)
- [image_data](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/image_data/)
- [NodeRendererBase.bounds_in_points](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/bounds_in_points/) 

## FAQ

1. **Q:** How do I insert an inline image at the current cursor position?  
   **A:** Use `DocumentBuilder.insert_image()` with a file path string. The method returns a `Shape` object representing the inserted image, which you can further manipulate if needed. Example:  
   ```python
   doc = aw.Document()
   builder = aw.DocumentBuilder(doc)
   builder.insert_image(docs_base.images_dir + "Logo.jpg")
   doc.save(docs_base.artifacts_dir + "InlineImage.docx")
   ```

2. **Q:** How can I place an image as a floating object with custom position and size?  
   **A:** Call the overload of `insert_image` that accepts positioning parameters such as `RelativeHorizontalPosition`, `RelativeVerticalPosition`, offsets, width, height, and `WrapType`. This creates a floating `Shape` that can be moved independently of the text flow. Example:  
   ```python
   builder.insert_image(
       docs_base.images_dir + "Logo.jpg",
       aw.drawing.RelativeHorizontalPosition.MARGIN, 100,
       aw.drawing.RelativeVerticalPosition.MARGIN, 100,
       200, 100,
       aw.drawing.WrapType.SQUARE)
   ```

3. **Q:** What is the recommended way to extract all images from a Word document?  
   **A:** Retrieve all `Shape` nodes via `Document.get_child_nodes(NodeType.SHAPE, True)`, filter those where `Shape.has_image` is `True`, and then use `Shape.image_data.save(file_path)` to write each image to disk. This works for any image type stored in the document.

4. **Q:** How do I lock or unlock the aspect ratio of an inserted image?  
   **A:** After inserting the image, set the `aspect_ratio_locked` property of the returned `Shape`. Setting it to `False` allows independent width and height adjustments; setting it to `True` preserves the original proportion. Example:  
   ```python
   shape = builder.insert_image(docs_base.images_dir + "Logo.jpg")
   shape.aspect_ratio_locked = False
   ```

5. **Q:** How can I obtain the actual size and position of an image as it appears on the page?  
   **A:** Use the `bounds_in_points` property of the shape’s renderer: `shape.get_shape_renderer().bounds_in_points`. It returns a rectangle with `x`, `y`, `width`, and `height` measured in points, reflecting the rendered size after any scaling or wrapping. This is useful for precise layout calculations.