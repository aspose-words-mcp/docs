---
title: Shapes Separately from Document
second_title: Aspose.Words for Node.js via .NET
articleTitle: Rendering Shapes Separately from a Document
linktitle: Rendering Shapes Separately from a Document
description: "Extract various graphic objects, such as images, text box containing paragraphs, or arrow shapes, when processing a document, and export them to an external location using Node.js."
type: docs
weight: 40
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/rendering-shapes-separately-from-a-document/
timestamp: 2025-07-09-10-05-05
---

When processing documents, a common task is to extract all images found in the document and export them to an external location. This task becomes simple with the Aspose.Words API, which already provides the functionality for extracting and saving image data. However, sometimes you may want to similarly extract other types of graphic content that is represented by a different type of drawing object, for example, a text box containing paragraphs, arrow shapes, and a small image. There is no straightforward way of rendering this object since it is a combination of individual content elements. You may also encounter a case when the contents have been grouped together into the object that looks like a single image.

Aspose.Words provides functionality for extracting this type of content in the same way you can extract a simple image from a shape as rendered content. This article describes how to utilize this functionality to render shapes independently of the document.

## Shape Types in Aspose.Words

All the content in a document drawing layer is represented by the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) or [GroupShape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/groupshape/) node in the Aspose.Words Document Object Module (DOM). Such contents can be text boxes, images, AutoShapes, OLE objects, etc. Some fields are also imported as shapes, for example, the `INCLUDEPICTURE` field.

A simple image is represented by a [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) node of [ShapeType.Image](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/). This shape node has no child nodes but the image data contained within this shape node can be accessed by the [Shape.imageData](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/imageData/) property. On the other hand, a shape can also be made up of many child nodes. For instance, a text box shape, which is represented by the [Shape.textBox](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/textBox/) property, can be made up of many nodes, such as [Paragraph](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraph/) and **Table**. Most shapes can include the [Paragraph](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraph/) and **Table** block-level nodes. These are the same nodes as those appearing in the main body. Shapes are always parts of some paragraph, either included directly inline or anchored to the [Paragraph](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraph/), but “floating” anywhere in the document page.

![rendering-shapes-separately-from-a-document_1](rendering-shapes-separately-from-a-document-1.png)

A document can also contain shapes which are grouped together. Grouping can be enabled in Microsoft Word by selecting multiple objects and clicking “Group” in the right-click menu.

![rendering-shapes-separately-from-a-document_2](rendering-shapes-separately-from-a-document-2.png)

In Aspose.Words, these groups of shapes are represented by the [GroupShape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/groupshape/) node. These can also be invoked in the same way to render the entire group to image.

![rendering-shapes-separately-from-a-document_3](rendering-shapes-separately-from-a-document-3.png)

The DOCX format can contain special types of images, such as diagrams or charts. These shapes are also represented through the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) node in Aspose.Words, which also provides a similar method for rendering them as images. By design, a shape cannot contain another shape as a child, unless that shape is an image ([ShapeType.Image](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)). For example, Microsoft Word does not allow you to insert a text box inside another text box.

The shape types described above provide a special method to render the shapes through the [ShapeRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/shaperenderer/) class. An instance of the [ShapeRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/shaperenderer/) class is retrieved for a [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) or [GroupShape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/groupshape/) through the [getShapeRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/getShapeRenderer/) method or by passing the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) to the constructor of the [ShapeRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/shaperenderer/) class. This class provides access to members, which allow rendering a shape to the following:

- File on the disk
- Stream

{{% alert color="primary" %}}

When rendering a [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/), it must be a part of the document hierarchy. If the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) is not a part of the document tree then the rendered output will be blank after invoking [ShapeRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/shaperenderer/) methods.

{{% /alert %}}

## Rendering to File or Stream

The [save](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/noderendererbase/save/) method provides overloads that render a shape directly to a file or stream. Both overloads accept an instance of the [ImageSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/) class, which allows to define options for rendering the shape. This works in the same way as the [Document.save](https://reference.aspose.com/words/nodejs-net/aspose.words/document/save/) method. Even though this parameter is required, you can pass a null value, specifying that there are no custom options.

The shape can be exported in any image format specified in the [SaveFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/) enumeration. For example, the image can be rendered as a raster image, such as JPEG by specifying the [SaveFormat.Jpeg](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/) enumeration, or as a vector image, such as EMF by specifying the [SaveFormat.Emf](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/).

The code example below illustrates rendering a shape to an EMF image separately from document, and saving to disk:

{{< gist "aspose-words-gists" "e9a02a29ae68be63f1fdfa266a642ea1" "render-shape-as-emf.js" >}}

The code example below illustrates rendering a shape to a JPEG image separately from document, and saving to a stream:

{{< gist "aspose-words-gists" "e9a02a29ae68be63f1fdfa266a642ea1" "render-shape-as-jpeg.js" >}}

The [ImageSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/) class allows you to specify a variety of options that control how the image is rendered. The functionality described above can be applied in the same manner to the [GroupShape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/groupshape/) and [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) nodes.

## Rendering a Shape Image

The [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) class represents objects in the drawing layer, such as an AutoShape, text box, freeform, OLE object, ActiveX control, or a picture. Using the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) class, you can create or modify shapes in a Microsoft Word document. An important property of a shape is its [shapeType](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/shapeType/). Shapes of different types can have different capabilities in a Word document. For example, only image and OLE shapes can have images inside them while most of the shapes can have text only.

The following example shows how to render a Shape image to a JPEG image separately from the document and save it to the disk:

{{< gist "aspose-words-gists" "e9a02a29ae68be63f1fdfa266a642ea1" "render-shape-image.js" >}}

## Retrieving a Shape Size

The [ShapeRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/shaperenderer/) class also provides functionality to retrieve the size of the shape in pixels through the **getBoundsInPixels2** method. This method accepts two parameters – the scale and DPI, which are used in calculation of the shape size when the shape is rendered. The method returns the bounds of the shape in pixels, with the `width` and `height` of the calculated size. This is useful when it is required to know the size of the rendered shape in advance. The [sizeInPoints2](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/noderendererbase/sizeInPoints2/) property returns the Shape size measured in points. The result is an object containing the `width` and `height`. Also you can use [boundsInPoints2](https://reference.aspose.com/words/nodejs-net/aspose.words.rendering/noderendererbase/boundsInPoints2/) property to get actual bounds of the shape.

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "get-actual-shape-bounds-points.js" >}}

------ 

## FAQ

1. Q: How can I render a shape to an image file using Node.js?  
   A: Retrieve a `ShapeRenderer` for the shape via `shape.getShapeRenderer()` (or by passing the shape to the `ShapeRenderer` constructor). Then call `shapeRenderer.save(filePath, imageSaveOptions)` where `imageSaveOptions` specifies the desired format (e.g., `SaveFormat.Jpeg` or `SaveFormat.Emf`). The method writes the rendered image directly to the specified file.

2. Q: Is it possible to render a shape directly to a stream instead of a file?  
   A: Not directly. In Node.js, `ShapeRenderer.save` writes to a file only (`save(fileName, imageSaveOptions)`). Save the image to a temporary file and read it with `fs.readFileSync` to send it over HTTP or keep it in memory.

3. Q: How do I obtain the size of a shape before rendering it?  
   A: Call `shapeRenderer.getBoundsInPixels2(scale, dpi)` to get the bounds of the shape (with `width` and `height`) in pixels. For size in points, use the `sizeInPoints2` property, which returns a `SizeF`. These values help you decide the appropriate image dimensions or DPI settings.

4. Q: Can a GroupShape containing multiple shapes be rendered as a single image?  
   A: Absolutely. Retrieve a `ShapeRenderer` for the `GroupShape` instance and invoke `save` just like with a regular shape. The renderer composites all child shapes into one image, preserving their relative positions.

5. Q: What happens if I try to render a shape that is not part of the document tree?  
   A: The shape is rendered as usual: `ShapeRenderer` does not require the shape to be inserted into the document tree. The shape only has to be created for a document, for example, `new aw.Drawing.Shape(doc, aw.Drawing.ShapeType.Rectangle)`.