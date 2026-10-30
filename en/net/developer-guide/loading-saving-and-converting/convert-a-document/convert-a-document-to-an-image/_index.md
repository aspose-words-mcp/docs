---
title: Convert a Document to an Image in C#
second_title: Aspose.Words for .NET
articleTitle: Convert a Document to an Image
linktitle: Convert a Document to an Image
type: docs
description: "Convert a document to image format (JPG, PNG, etc). Create a document preview or create a document scan to send an invoice using C#."
weight: 43
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/convert-a-document-to-an-image/
timestamp: 2024-07-09-19-00-42
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert a Word document into images (e.g., PNG, JPEG) using Aspose.Words.

{{% /alert %}}

Sometimes it is required to get an image instead of documents in other formats, such as DOCX or PDF. For example, you need to add a preview of any document page to your website or application, or create a "scan" of a document to send an invoice. This is when you may need to convert a document in any [supported load format](https://reference.aspose.com/words/net/aspose.words/loadformat/) to an image, again, in any [supported save format](https://reference.aspose.com/words/net/aspose.words/saveformat/).

## Convert to Image {#convert-to-image-format}

As with all conversion examples already described, you need to create a new document or load an existing one in any supported format, make the necessary changes, and save it in any available image format, for example, JPEG, PNG, or BMP.

The following code example shows how to convert PDF to JPEG:

{{< gist "aspose-words-gists" "ebbb90d74ef57db456685052a18f8e86" "pdf-to-jpeg.cs" >}}

## Specify Save Options when Converting to Image {#specify-save-options-when-converting-to-an-image}

Aspose.Words provides you with the [ImageSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/) class, which gives more control over how documents are saved in various image formats. Some properties of this class inherit or overload properties of base classes such as [FixedPageSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/fixedpagesaveoptions/) or [SaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/), but there are also options specific to saving images.

It is possible to specify the pages to be converted to image format using the [PageSet](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pageset/) property. For example, it can be applied if you only need a preview for the first or for a definite page.

It is also possible to control the output image quality and pixel format using the following properties – [HorizontalResolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/horizontalresolution/), [VerticalResolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/verticalresolution/), [Resolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/resolution/), [Scale](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/scale/), [PixelFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pixelformat/), as well as set up image color settings, using the following properties – [ImageBrightness](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagebrightness/), [ImageColorMode](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagecolormode/), [ImageContrast](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagecontrast/), [PaperColor](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/papercolor/).

There are also properties that apply to a certain format, for example, [JpegQuality](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/jpegquality/) or [TiffCompression](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/tiffcompression/).

The following code example shows how to create a preview of the first document page with applying some additional settings:

{{< gist "aspose-words-gists" "ebbb90d74ef57db456685052a18f8e86" "get-jpeg-page-range.cs" >}}

------

## FAQ

1. **Q:** How do I convert a Word document to an image using C#?  
   **A:** Load the document with `Document doc = new Document("input.docx");`, create an `ImageSaveOptions` object specifying the desired format (e.g., `SaveFormat.Jpeg`), and call `doc.Save("output.jpg", saveOptions);`. The API handles all supported source formats.

2. **Q:** Which image formats can Aspose.Words save to?  
   **A:** Aspose.Words supports JPEG, PNG, BMP, GIF, TIFF, and EMF when using `ImageSaveOptions`. The `SaveFormat` enumeration lists all available formats.

3. **Q:** How can I convert only specific pages of a document to images?  
   **A:** Set the `PageSet` property of `ImageSaveOptions` to a `PageSet` that defines the required pages, e.g., `saveOptions.PageSet = new PageSet(new PageRange(0, 4));` to export the first five pages (page indexes are zero-based; `new PageSet(1, 5)` would export only the pages with indexes 1 and 5).

4. **Q:** What options are available to control image quality and resolution?  
   **A:** Use properties such as `JpegQuality` (0‑100), `HorizontalResolution`, `VerticalResolution`, `Resolution`, `Scale`, and `PixelFormat`. Adjusting these values lets you balance file size and visual fidelity.

5. **Q:** Can I convert a PDF (or other non‑Word format) to an image with Aspose.Words?  
   **A:** Yes. Aspose.Words can load PDF, DOC, DOCX, RTF, HTML, and many other formats. Load the PDF with `Document doc = new Document("input.pdf");` and then save it using `ImageSaveOptions` as described above.