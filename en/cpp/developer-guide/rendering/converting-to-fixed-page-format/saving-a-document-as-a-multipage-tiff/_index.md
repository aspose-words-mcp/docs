---
title: Saving a Document as a Multipage TIFF in C++
second_title: Aspose.Words for C++
articleTitle: Saving a Document as a Multipage TIFF
linktitle: Saving a Document as a Multipage TIFF
description: "Convert a document to a multi-page TIFF using C++. To determine how the document is displayed on the image you need to specify additional options: resolution, number of pages, image binarization, etc."
type: docs
weight: 40
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/saving-a-document-as-a-multipage-tiff/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to save a document as a multi-page TIFF image.

{{% /alert %}}

When working with documents, you often need to convert your document to a raster image file(s). This is especially relevant if you have to present your document in a readable and printable, but not editable format. For example, you can use a raster image of the first page of your document as a preview. This article describes how to convert a document to a raster image using the example of the TIFF format – one of the more popular image formats.

## Converting DOC to Multi-Page TIFF

In Aspose.Words, conversion from DOC to TIFF can be performed with one line of code, by simply passing the “save to” path and the relevant file extension to the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method. The **Save** method automatically derives the `SaveFormat` from the file name extension specified in the path. The following example demonstrates how to convert a document to the TIFF format:

{{< gist "aspose-words-gists" "9f8dd7d3c3d34f36e69c8fa9382f453d" "save-as-tiff.h" >}}

## Specifying Additional Options When Rendering TIFF

You often need to specify additional options, which affect the rendering result. For this purpose, use the [ImageSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/) class, which contains properties that determine how the document is displayed on the image. You can specify the following:

- Save format to determine the list of available options ([get_SaveFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_saveformat/))
- Resolution ([get_HorizontalResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_horizontalresolution/), [get_VerticalResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_verticalresolution/), [set_Resolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_resolution/))
- Number of pages ([get_PageSet()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pageset/))
- Color and lighting settings ([set_PaperColor()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_papercolor/), [get_ImageColorMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagecolormode/), [set_ImageBrightness()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_imagebrightness/), [set_ImageContrast()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_imagecontrast/))
- Image quality ([set_JpegQuality()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_jpegquality/), [get_Scale()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_scale/), [get_TiffCompression()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_tiffcompression/), [get_GraphicsQualityOptions()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_graphicsqualityoptions/))
- Method used to binarize the image ([get_TiffBinarizationMethod()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_tiffbinarizationmethod/), [get_ThresholdForFloydSteinbergDithering()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_thresholdforfloydsteinbergdithering/))
- Pixel format for generated images ([get_PixelFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pixelformat/))
- Windows metafiles handling by Aspose.Words ([get_MetafileRenderingOptions()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_metafilerenderingoptions/), [get_UseGdiEmfRenderer()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_usegdiemfrenderer/))
- Additional options that you can see in the **ImageSaveOptions** class

The following example shows how to convert DOC to TIFF with configured options:

{{< gist "aspose-words-gists" "9f8dd7d3c3d34f36e69c8fa9382f453d" "get-tiff-page-range.h" >}}

## Threshold for TIFF Binarization

A TIFF image can be saved in 1bpp b/w format by setting the [get_PixelFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pixelformat/) property to Format1bppIndexed pixel format type, and the [get_TiffCompression()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_tiffcompression/) property to either Ccitt3 or Ccitt4.

For image segmentation, Aspose.Words uses the simplest method — thresholding. This method converts a gray‑scale TIFF image into a binary image, using a threshold value. Therefore, when a document needs to be converted to the TIFF file format, it is possible to get or set the threshold for TIFF binarization via the [get_ThresholdForFloydSteinbergDithering()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_thresholdforfloydsteinbergdithering/) property. The default value for this property is set to 128, and the higher this value, the darker the image.

The following example shows how to perform TIFF binarization with a specified threshold:

{{< gist "aspose-words-gists" "9f8dd7d3c3d34f36e69c8fa9382f453d" "expose-threshold-control.h" >}}

Below you can compare images on which TIFF binarization was performed at various threshold values:

<img src="saving-a-document-as-a-multipage-tiff-1.jpg" alt="saving-a-document-as-a-multipage-tiff-aspose-words-cpp" style="width:800px"/>

## Related APIs

- [Document::Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/)
- [ImageSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/)
- [get_SaveFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_saveformat/)
- [set_Resolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_resolution/)
- [get_HorizontalResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_horizontalresolution/)
- [get_VerticalResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_verticalresolution/)
- [get_PageSet()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pageset/)
- [get_TiffCompression()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_tiffcompression/)
- [get_TiffBinarizationMethod()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_tiffbinarizationmethod/)
- [get_ThresholdForFloydSteinbergDithering()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_thresholdforfloydsteinbergdithering/)
- [get_PixelFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_pixelformat/)
- [get_PaperColor()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_papercolor/)
- [get_ImageColorMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagecolormode/)
- [get_ImageBrightness()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagebrightness/)
- [get_ImageContrast()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_imagecontrast/)
- [get_MetafileRenderingOptions()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_metafilerenderingoptions/)
- [get_UseGdiEmfRenderer()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_usegdiemfrenderer/)
- [get_GraphicsQualityOptions()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/get_graphicsqualityoptions/)

------ 

## FAQ

1. **Q:** How do I save a document as a multipage TIFF in C++ with Aspose.Words?
   **A:** Create a `Document` object, configure an `ImageSaveOptions` instance with `SaveFormat::Tiff`, set any desired options (resolution, page range, compression, etc.), and call `doc->Save(u"output.tiff", saveOptions);`.

2. **Q:** How can I control the DPI (resolution) of the generated TIFF images?
   **A:** Set the `Resolution` property of `ImageSaveOptions`, or set `set_HorizontalResolution()` and `get_VerticalResolution()` individually to the required DPI value before saving.

3. **Q:** Which property defines the compression type for the TIFF file?
   **A:** Use the `TiffCompression` property of `ImageSaveOptions`. Common values are `TiffCompression::Ccitt3`, `TiffCompression::Ccitt4`, `TiffCompression::Lzw`, etc.

4. **Q:** How do I create a black‑and‑white (1 bpp) TIFF and adjust its binarization threshold?
   **A:** Set `set_PixelFormat()` to `ImagePixelFormat::Format1bppIndexed` and `TiffCompression` to `TiffCompression::Ccitt3` or `TiffCompression::Ccitt4`, choose a `get_TiffBinarizationMethod()` (e.g., `ImageBinarizationMethod::FloydSteinbergDithering`), and set `set_ThresholdForFloydSteinbergDithering()` to a value between 0 and 255 (default is 128).

5. **Q:** How can I export only specific pages of a document to the TIFF output?
   **A:** Set the `PageSet` property of the `ImageSaveOptions` object before calling `Save`. For example, `saveOptions->set_PageSet(System::MakeObject<PageSet>(System::MakeArray<System::SharedPtr<PageRange>>({System::MakeObject<PageRange>(0, 2)})));` limits the TIFF to the first three pages (page indexes are zero‑based and the range is inclusive).