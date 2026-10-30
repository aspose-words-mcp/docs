---
title: Convert a Document to an Image in C++
second_title: Aspose.Words for C++
articleTitle: Convert a Document to an Image
linktitle: Convert a Document to an Image
type: docs
description: "Convert a document to image format (JPG, PNG, etc). Create a document preview or create a document scan to send an invoice using C++."
weight: 43
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/convert-a-document-to-an-image/
timestamp: 2024-01-30-16-22-34
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert a Word document into images (e.g., PNG, JPEG) using Aspose.Words.

{{% /alert %}}

Sometimes it is required to get an image instead of documents in other formats, such as DOCX or PDF. For example, you need to add a preview of any document page to your website or application, or create a "scan" of a document to send an invoice. This is when you may need to convert a document in any [supported load format](https://reference.aspose.com/words/cpp/aspose.words/loadformat/) to an image, again, in any [supported save format](https://reference.aspose.com/words/cpp/aspose.words/saveformat/).

## Convert to Image {#convert-to-image-format}

As with all conversion examples already described, you need to create a new document or load an existing one in any supported format, make the necessary changes, and save it in any available image format, for example, JPEG, PNG, or BMP.

The following code example shows how to convert DOCX to JPEG:

{{< gist "aspose-words-gists" "78660568d22b261d148a22cb891ae4d6" "docx-to-jpeg.h" >}}

## Specify Save Options when Converting to Image {#specify-save-options-when-converting-to-an-image}

Aspose.Words provides you with the [ImageSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/) class, which gives more control over how documents are saved in various image formats. Some properties of this class inherit or overload properties of base classes such as [FixedPageSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/fixedpagesaveoptions/) or [SaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/), but there are also options specific to saving images.

It is possible to specify the pages to be converted to image format using the [get_PageSet()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pageset/) property. For example, it can be applied if you only need a preview for the first or for a definite page.

It is also possible to control the output image quality and pixel format using the following properties – [set_HorizontalResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_horizontalresolution/), [get_VerticalResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_verticalresolution/), [set_Resolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_resolution/), [set_Scale()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_scale/), [get_PixelFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pixelformat/), as well as set up image color settings, using the following properties – [get_ImageBrightness()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagebrightness/), [get_ImageColorMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagecolormode/), [get_ImageContrast()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagecontrast/), [get_PaperColor()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_papercolor/).

There are also properties that apply to a certain format, for example, [get_JpegQuality()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_jpegquality/) or [get_TiffCompression()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_tiffcompression/).

The following code example shows how to create a preview of the first document page with applying some additional settings:

{{< gist "aspose-words-gists" "78660568d22b261d148a22cb891ae4d6" "get-jpeg-page-range.h" >}}

------ 

## FAQ

1. **Q:** How do I convert a Word document to a JPEG image using Aspose.Words for C++?  
   **A:** Load the document with `System::SharedPtr<Aspose::Words::Document> doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");`, create an `ImageSaveOptions` object, set `SaveFormat` to `SaveFormat::Jpeg`, and call `doc->Save(u"output.jpg", saveOptions);`.

2. **Q:** Can I convert only selected pages of a document to images?  
   **A:** Yes. Use the `PageSet` property of `ImageSaveOptions`. For example, `saveOptions->set_PageSet(System::MakeObject<Aspose::Words::Saving::PageSet>(0));` converts only the first page (page indexes are zero‑based).

3. **Q:** Which options let me control the resolution and quality of the saved image?  
   **A:** `get_HorizontalResolution()`, `get_VerticalResolution()`, and `Resolution` control DPI. `get_JpegQuality()` (0‑100) adjusts JPEG compression, while `TiffCompression` sets TIFF compression type. Adjust these on the `ImageSaveOptions` instance before saving.

4. **Q:** How can I change the pixel format or color mode of the output image?  
   **A:** Call `set_PixelFormat` (e.g., `ImagePixelFormat::Format24BppRgb`) and `set_ImageColorMode` (e.g., `ImageColorMode::Grayscale`) on the `ImageSaveOptions` object to modify the image's color representation.

5. **Q:** How do I generate separate image files for every page in a document?  
   **A:** Loop through the page count, update `PageSet` for each page, and call `Save` with a distinct file name, e.g.:

   ```cpp
   System::SharedPtr<Aspose::Words::Document> doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   System::SharedPtr<Aspose::Words::Saving::ImageSaveOptions> options = System::MakeObject<Aspose::Words::Saving::ImageSaveOptions>(SaveFormat::Png);
   for (int i = 0; i < doc->get_PageCount(); ++i)
   {
       options->set_PageSet(System::MakeObject<Aspose::Words::Saving::PageSet>(i));
       System::String fileName = System::String::Format(u"page_{0}.png", i + 1);
       doc->Save(fileName, options);
   }
   ```

   This creates one image per page with the specified format and options.