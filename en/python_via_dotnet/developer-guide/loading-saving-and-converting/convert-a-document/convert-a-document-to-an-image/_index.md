---
title: Convert a Document to an Image
second_title: Aspose.Words for Python via .NET
articleTitle: Convert a Document to an Image
linktitle: Convert a Document to an Image
type: docs
description: "Convert a document to image format (JPG, PNG, etc). Create a document preview or create a document scan to send an invoice using Python."
weight: 43
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/convert-a-document-to-an-image/
aliases: [/python/convert-a-document-to-an-image/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to convert documents to image formats (e.g., JPEG, PNG, BMP) using Aspose.Words for Python via .NET, and explains how to customize the conversion with ImageSaveOptions such as page selection, resolution, quality, and pixel format.
{{% /alert %}}

Sometimes it is required to get an image instead of documents in other formats, such as DOCX or PDF. For example, you need to add a preview of any document page to your website or application, or create a "scan" of a document to send an invoice. This is when you may need to convert a document in any [supported load format](https://reference.aspose.com/words/python-net/aspose.words/loadformat/) to an image, again, in any [supported save format](https://reference.aspose.com/words/python-net/aspose.words/saveformat/).

## Convert to Image {#convert-to-image-format}

As with all conversion examples already described, you need to create a new document or load an existing one in any supported format, make the necessary changes, and save it in any available image format, for example, JPEG, PNG, or BMP.

The following code example shows how to convert PDF to JPEG:

{{< gist "aspose-words-gists" "f9e5cde75221f622f636297c5fcc7297" "pdf-to-jpeg.py" >}}

## Specify Save Options when Converting to Image {#specify-save-options-when-converting-to-an-image}

Aspose.Words provides you with the [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/) class, which gives more control over how documents are saved in various image formats. Some properties of this class inherit or overload properties of base classes such as [FixedPageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/fixedpagesaveoptions/) or [SaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/), but there are also options specific to saving images.

It is possible to specify the pages to be converted to image format using the [page_set](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/page_set/) property. For example, it can be applied if you only need a preview for the first or for a definite page.

It is also possible to control the output image quality and pixel format using the following properties – [horizontal_resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/horizontal_resolution/), [vertical_resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/vertical_resolution/), [scale](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/scale/), [pixel_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/pixel_format/), [image_brightness](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_brightness/), as well as set up image color settings, using the following properties – [image_color_mode](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_color_mode/), [image_contrast](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_contrast/), [paper_color](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/paper_color/), [paper_color](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/paper_color/).

There are also properties that apply to a certain format, for example, [jpeg_quality](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/jpeg_quality/) or [tiff_compression](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/tiff_compression/).

The following code example shows how to create a preview of the first document page with applying some additional settings:

{{< gist "aspose-words-gists" "f9e5cde75221f622f636297c5fcc7297" "get-jpeg-page-range.py" >}} 

## FAQ

1. **Q:** How can I convert only selected pages of a document to images?  
   **A:** Use the `ImageSaveOptions.page_set` property to specify a collection of page indices. For example, to convert pages 1 and 3 only into a multi-page TIFF:

   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.page_set = aw.saving.PageSet([0, 2])   # zero-based page indices
   doc.save("output.tiff", options)
   ```

2. **Q:** How do I change the resolution of the generated image?  
   **A:** Set `horizontal_resolution` and `vertical_resolution` (in DPI) on `ImageSaveOptions`. Higher DPI yields a larger, higher‑quality image.

   ```python
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.PNG)
   options.horizontal_resolution = 300
   options.vertical_resolution = 300
   doc.save("high_res.png", options)
   ```

3. **Q:** How can I control JPEG quality when saving as JPEG?  
   **A:** Adjust the `jpeg_quality` property (0‑100). A higher value gives better quality but larger file size.

   ```python
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.JPEG)
   options.jpeg_quality = 85   # typical high‑quality setting
   doc.save("photo.jpeg", options)
   ```

4. **Q:** Is it possible to change the pixel format of the output image?  
   **A:** Yes. Use the `pixel_format` property with values from the `ImagePixelFormat` enumeration (e.g., `FORMAT_24BPP_RGB`, `FORMAT_32BPP_RGB`).

   ```python
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.pixel_format = aw.saving.ImagePixelFormat.FORMAT_24BPP_RGB
   doc.save("output.tiff", options)
   ```

5. **Q:** Can I convert a PDF document directly to an image using Aspose.Words for Python via .NET?  
   **A:** Absolutely. Load the PDF with `Document`, configure `ImageSaveOptions`, and save it in the desired image format.

   ```python
   doc = aw.Document("source.pdf")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.JPEG)
   options.page_set = aw.saving.PageSet(1)   # second page only
   doc.save("pdf_page2.jpeg", options)
   ```