---
title: Shapes Separately from Document
second_title: Aspose.Words for Python via .NET
articleTitle: Rendering Shapes Separately from a Document
linktitle: Rendering Shapes Separately from a Document
description: "Extract various graphic objects, such as images, text box containing paragraphs, or arrow shapes, when processing a document, and export them to an external location using Python."
type: docs
weight: 40
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/rendering-shapes-separately-from-a-document/
aliases: [/python/rendering-shapes-separately-from-a-document/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains how to use Aspose.Words for Python via .NET to render individual shapes, group shapes, and shape images from a Word document to image files or streams, and how to obtain shape size information.

{{% /alert %}}

When processing documents, a common task is to extract all images found in the document and export them to an external location. This task becomes simple with the Aspose.Words API, which already provides the functionality for extracting and saving image data. However, sometimes you may want to similarly extract other types of graphic content that is represented by a different type of drawing object, for example, a text box containing paragraphs, arrow shapes, and a small image. There is no straightforward way of rendering this object since it is a combination of individual content elements. You may also encounter a case when the contents have been grouped together into the object that looks like a single image.

Aspose.Words provides functionality for extracting this type of content in the same way you can extract a simple image from a shape as rendered content. This article describes how to utilize this functionality to render shapes independently of the document.

## Shape Types in Aspose.Words

All the content in a document drawing layer is represented by the [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) or [GroupShape](https://reference.aspose.com/words/python-net/aspose.words.drawing/groupshape/) node in the Aspose.Words Document Object Module (DOM). Such contents can be text boxes, images, AutoShapes, OLE objects, etc. Some fields are also imported as shapes, for example, the `INCLUDEPICTURE` field.

A simple image is represented by a **Shape** node of [ShapeType.IMAGE](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapetype/#image). This shape node has no child nodes but the image data contained within this shape node can be accessed by the [Shape.image_data](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/image_data/) property. On the other hand, a shape can also be made up of many child nodes. For instance, a text box shape, which is represented by the [ShapeType.TEXT_BOX](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapetype/#text_box) property, can be made up of many nodes, such as [Paragraph](https://reference.aspose.com/words/python-net/aspose.words/paragraph/) and [Table](https://reference.aspose.com/words/python-net/aspose.words.tables/table/). Most shapes can include the **Paragraph** and **Table** block-level nodes. These are the same nodes as those appearing in the main body. Shapes are always parts of some paragraph, either included directly inline or anchored to the **Paragraph,** but “floating” anywhere in the document page.

![rendering-shapes-separately-from-a-document_1](rendering-shapes-separately-from-a-document-1.png)

A document can also contain shapes which are grouped together. Grouping can be enabled in Microsoft Word by selecting multiple objects and clicking “Group” in the right‑click menu.

![rendering-shapes-separately-from-a-document_2](rendering-shapes-separately-from-a-document-2.png)

In Aspose.Words, these groups of shapes are represented by the [GroupShape](https://reference.aspose.com/words/python-net/aspose.words.drawing/groupshape/) node. These can also be invoked in the same way to render the entire group to image.

![rendering-shapes-separately-from-a-document_3](rendering-shapes-separately-from-a-document-3.png)

The DOCX format can contain special types of images, such as diagrams or charts. These shapes are also represented through the **Shape** node in Aspose.Words, which also provides a similar method for rendering them as images. By design, a shape cannot contain another shape as a child, unless that shape is an image (**ShapeType.IMAGE**). For example, Microsoft Word does not allow you to insert a text box inside another text box.

The shape types described above provide a special method to render the shapes through the [ShapeRenderer](https://reference.aspose.com/words/python-net/aspose.words.rendering/shaperenderer/) class. An instance of the **ShapeRenderer** class is retrieved for a **Shape** or **GroupShape** through the **get_shape_renderer** method or by passing the **Shape** to the constructor of the **ShapeRenderer** class. This class provides access to members, which allow rendering a shape to the following:

- File on the disk using the [save](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/save/) method
- Stream using the [save](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/save/) method

{{% alert color="primary" %}}

When rendering a **Shape**, it must be a part of the document hierarchy. If the **Shape** is not a part of the document tree then the rendered output will be blank after invoking **ShapeRenderer** methods.

{{% /alert %}}

## Rendering to File or Stream

The [save](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/save/) method renders a shape directly to a file or a stream. It accepts an instance of the [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/) class, which allows to define options for rendering the shape. This works in the same way as the [Document.save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method. Even though this parameter is required, you can pass `None`, specifying that there are no custom options.

Note that when rendering to a stream, the stream must be readable as well as writable – for example, an `io.BytesIO` instance.

The shape can be exported in any image format specified in the [SaveFormat](https://reference.aspose.com/words/python-net/aspose.words/saveformat/) enumeration. For example, the image can be rendered as a raster image, such as JPEG by specifying the [SaveFormat.JPEG](https://reference.aspose.com/words/python-net/aspose.words/saveformat/#jpeg) enumeration, or as a vector image, such as EMF by specifying the [SaveFormat.EMF](https://reference.aspose.com/words/python-net/aspose.words/saveformat/#emf).

The code example below illustrates rendering a shape to an EMF image separately from document, and saving to disk:

{{< gist "aspose-words-gists" "d95a7c191b62bdce78605ee22d39b9ab" "render-shape-as-emf.py" >}}

The code example below illustrates rendering a shape to a JPEG image separately from document, and saving to a stream:

{{< gist "aspose-words-gists" "d95a7c191b62bdce78605ee22d39b9ab" "render-shape-as-jpeg.py" >}}

The **ImageSaveOptions** class allows you to specify a variety of options that control how the image is rendered. The functionality described above can be applied in the same manner to the **GroupShape** and **Shape** nodes.

## Rendering a Shape Image

The [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) class represents objects in the drawing layer, such as an AutoShape, text box, freeform, OLE object, ActiveX control, or a picture. Using the **Shape** class, you can create or modify shapes in a Microsoft Word document. An important property of a shape is its [shape_type](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/shape_type/). Shapes of different types can have different capabilities in a Word document. For example, only image and OLE shapes can have images inside them while most of the shapes can have text only.

The following example shows how to render a Shape image to a JPEG image separately from the document and save it to the disk:

{{< gist "aspose-words-gists" "d95a7c191b62bdce78605ee22d39b9ab" "render-shape-image.py" >}}

## Retrieving a Shape Size

The [ShapeRenderer](https://reference.aspose.com/words/python-net/aspose.words.rendering/shaperenderer/) class also provides functionality to retrieve the size of the shape in pixels through the [get_size_in_pixels](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/get_size_in_pixels/) method. This method accepts two float parameters – the scale and DPI, which are used in calculation of the shape size when the shape is rendered. The method returns a `Size` object, which contains the width and height of the calculated size in pixels. This is useful when it is required to know the size of the rendered shape in advance.

The [size_in_points](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/size_in_points/) property returns the shape size measured in points. The result is a `SizeF` object containing the width and height.

## Related APIs

- **[Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/)** - Represents objects in the drawing layer such as AutoShapes, text boxes, and pictures
- **[GroupShape](https://reference.aspose.com/words/python-net/aspose.words.drawing/groupshape/)** - Represents a group of shapes that can be rendered together
- **[ShapeRenderer](https://reference.aspose.com/words/python-net/aspose.words.rendering/shaperenderer/)** - Provides methods for rendering shapes to files or streams
- **[ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/)** - Controls rendering options when saving shapes as images
- **[NodeRendererBase](https://reference.aspose.com/words/python-net/aspose.words.rendering/noderendererbase/)** - Base class providing common rendering functionality including the `save` and `get_size_in_pixels` methods