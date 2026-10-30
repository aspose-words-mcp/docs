---
title: Working with Watermark in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Watermark
linktitle: Working with Watermark
description: "Create and manage watermarks in a document using Python."
type: docs
weight: 340
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-watermark/
aliases: [/python/working-with-watermark/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to add, customize, and remove text or image watermarks in Word documents. It includes code examples for inserting watermarks via the Watermark class, using shapes, and handling watermarks inside table cells.  
{{% /alert %}}

This topic discusses how to work programmatically with watermark using Aspose.Words. A watermark is a background image that displays behind the text in a document. A watermark can contain a text or an image represented by the [Watermark](https://reference.aspose.com/words/python-net/aspose.words/watermark/) class.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online document watermark](https://products.aspose.app/words/watermark).

{{% /alert %}}

## Add a Watermark to a Document

In Microsoft Word, a watermark can easily be inserted in a document using the Insert Watermark command. Aspose.Words provides the [Watermark](https://reference.aspose.com/words/python-net/aspose.words/watermark/) class to add or remove watermark in documents. Aspose.Words provides the [WatermarkType](https://reference.aspose.com/words/python-net/aspose.words/watermarktype/) enumeration defining three possible types of watermarks (Text, Image, and None) to work with. 

### Add Text Watermark

The following code example demonstrates how to insert a text watermark in a document by defining [TextWatermarkOptions](https://reference.aspose.com/words/python-net/aspose.words/textwatermarkoptions/) using the [set_text](https://reference.aspose.com/words/python-net/aspose.words/watermark/set_text/) method:

{{< gist "aspose-words-gists" "1773c0992ab338091979cdd43e22557c" "add-text-watermark.py" >}}

### Add Image Watermark

The following code example demonstrates how to insert an image watermark in a document by defining [ImageWatermarkOptions](https://reference.aspose.com/words/python-net/aspose.words/imagewatermarkoptions/) using the [set_image](https://reference.aspose.com/words/python-net/aspose.words/watermark/set_image/) method:

{{< gist "aspose-words-gists" "1773c0992ab338091979cdd43e22557c" "add-image-watermark.py" >}}

Image watermark can be inserted as image, string, or stream.

The watermark can also be inserted using shape class as well. It is very easy to insert any shape or image into a header or footer and thus create a watermark of any imaginable type.

The following code example inserts a watermark into a Word document:

{{< gist "aspose-words-gists" "1773c0992ab338091979cdd43e22557c" "add-document-watermark.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [here](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}


## Remove Watermark from a Document

The [Watermark](https://reference.aspose.com/words/python-net/aspose.words/watermark/) class provides the remove method to remove the watermark from a document.

The following code example shows how to remove a watermark from documents:

{{< gist "aspose-words-gists" "1773c0992ab338091979cdd43e22557c" "remove-document-watermark.py" >}}

If the watermarks are added using the [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) class object then to remove the watermark from a document you have to set only the name of watermark shape during inserting and then remove watermark shape by an assigned name.

The following code example show you how to set the name of the watermark shape and remove it from the document:

{{< gist "aspose-words-gists" "1773c0992ab338091979cdd43e22557c" "set-shape-name.py" >}}

{{< gist "aspose-words-gists" "1773c0992ab338091979cdd43e22557c" "remove-watermark-shape.py" >}}

## Add a Watermark into a Table Cell

Sometimes you need to insert a watermark/image into a table's cell and display it outside the table, you can use the [is_layout_in_cell](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/is_layout_in_cell/) property. This property gets or sets a flag indicating whether the shape is displayed inside a table or outside of it. Note that this property works only when you optimize the document for Microsoft Word 2010 using the [optimize_for](https://reference.aspose.com/words/python-net/aspose.words.settings/compatibilityoptions/optimize_for/) method.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "layout-in-cell.py" >}} 

## FAQ

1. **Q:** How can I add a text watermark with a specific font size and color?  
   **A:** Create a `TextWatermarkOptions` object, set the `font_family`, `font_size`, and `color` properties, and then call `doc.watermark.set_text("Your Text", options)`. Example:  

   ```python
   import aspose.pydrawing
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.TextWatermarkOptions()
   options.font_family = "Arial"
   options.font_size = 72
   options.color = aspose.pydrawing.Color.gray
   doc.watermark.set_text("CONFIDENTIAL", options)
   doc.save("output.docx")
   ```

2. **Q:** How do I insert an image watermark from a file path or a stream?  
   **A:** Use `ImageWatermarkOptions` and the `doc.watermark.set_image` method. Provide either a file path or a stream to the image. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.ImageWatermarkOptions()
   options.scale = 0.5   # optional scaling
   doc.watermark.set_image("logo.png", options)
   doc.save("output.docx")
   ```

3. **Q:** What is the recommended way to remove a watermark that was added with the `Watermark` class?  
   **A:** Call the `remove` method of the document's `watermark`. This removes any watermark added via the `Watermark` API. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("watermarked.docx")
   doc.watermark.remove()
   doc.save("clean.docx")
   ```

4. **Q:** I added a watermark as a `Shape`. How can I delete it later?  
   **A:** Assign a unique name to the shape when you create it (e.g., `watermark.name = "MyWatermark"`). Later, retrieve the shape by name from the document’s node collection and remove it. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   shape = aw.drawing.Shape(doc, aw.drawing.ShapeType.TEXT_PLAIN_TEXT)
   shape.name = "MyWatermark"
   # ... configure shape as watermark ...
   # later: find the shape by name and remove it
   for node in doc.get_child_nodes(aw.NodeType.SHAPE, True):
       if node.as_shape().name == "MyWatermark":
           node.remove()
           break
   doc.save("output.docx")
   ```

5. **Q:** Can I place a watermark inside a table cell but have it appear outside the cell boundaries?  
   **A:** Yes. Set the shape’s `is_layout_in_cell` property to `False` and ensure the document is optimized for Word 2010 using `CompatibilityOptions.optimize_for`. This forces the watermark to be rendered relative to the page rather than the cell. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   shape = aw.drawing.Shape(doc, aw.drawing.ShapeType.IMAGE)
   shape.is_layout_in_cell = False
   doc.compatibility_options.optimize_for(aw.settings.MsWordVersion.WORD2010)
   # add shape to the desired cell
   doc.save("output.docx")
   ```
