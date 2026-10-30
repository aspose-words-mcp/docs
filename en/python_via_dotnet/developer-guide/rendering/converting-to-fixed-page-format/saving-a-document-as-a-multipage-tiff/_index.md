---
title: Saving a Document as a Multipage TIFF
second_title: Aspose.Words for Python via .NET
articleTitle: Saving a Document as a Multipage TIFF
linktitle: Saving a Document as a Multipage TIFF
description: "Convert a document to a multi-page TIFF using Python. To determine how the document is displayed on the image you need to specify additional options: resolution, number of pages, image binarization, etc."
type: docs
weight: 30
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/saving-a-document-as-a-multipage-tiff/
aliases: [/python/saving-a-document-as-a-multipage-tiff/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This article demonstrates how to convert a document to a multi‑page TIFF using Aspose.Words for Python via .NET, including basic conversion and configuring rendering options such as resolution, page range, compression, color mode, and binarization.

{{% /alert %}}

When working with documents, you often need to convert your document to a raster image file(s). This is especially relevant if you have to present your document in a readable and printable, but not editable format. For example, you can use a raster image of the first page of your document as a preview. This article describes how to convert a document to a raster image using the example of the TIFF format – one of the more popular image formats.

## Converting DOC to Multi-Page TIFF

In Aspose.Words, conversion from DOC to TIFF can be performed with one line of code, by simply passing the “save to” path and the relevant file extension to the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method. The **Save** method automatically derives the `SaveFormat` from the file name extension specified in the path. The following example demonstrates how to convert a document to the TIFF format:

{{< gist "aspose-words-gists" "bd5cd6839da6238300d3e0af47d1a262" "save-as-tiff.py" >}}

## Specifying Additional Options When Rendering TIFF

You often need to specify additional options, which affect the rendering result. For this purpose, use the [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/) class, which contains properties that determine how the document is displayed on the image. You can specify the following:

- Save format to determine the list of available options ([save_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/save_format/))
- Resolution ([horizontal_resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/horizontal_resolution/), [vertical_resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/vertical_resolution/), [page_set](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/page_set/))
- Pages to render ([page_set](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/page_set/))
- Color and lighting settings ([paper_color](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/paper_color/), [image_color_mode](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_color_mode/), [image_brightness](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_brightness/), [image_contrast](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_contrast/))
- Image quality ([jpeg_quality](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/jpeg_quality/), [scale](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/scale/), [tiff_compression](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/tiff_compression/), [use_anti_aliasing](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/use_anti_aliasing/), [use_high_quality_rendering](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/use_high_quality_rendering/))
- Method used to binarize the image ([tiff_binarization_method](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/tiff_binarization_method/), [threshold_for_floyd_steinberg_dithering](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/threshold_for_floyd_steinberg_dithering/))
- Pixel format for generated images ([pixel_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/pixel_format/))
- Windows metafiles handling by Aspose.Words ([metafile_rendering_options](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/metafile_rendering_options/), [use_gdi_emf_renderer](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/use_gdi_emf_renderer/))
- Additional options that you can see in the **ImageSaveOptions** class

The following example shows how to convert DOC to TIFF with configured options:

{{< gist "aspose-words-gists" "bd5cd6839da6238300d3e0af47d1a262" "get-tiff-page-range.py" >}}

## Threshold for TIFF Binarization

A TIFF image can be saved in 1bpp b/w format by setting the [pixel_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/pixel_format/) property to Format1bppIndexed pixel format type, and the [tiff_compression](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/tiff_compression/) property to either Ccitt3 or Ccitt4.

For image segmentation, Aspose.Words uses the simplest method — thresholding. This method converts a gray‑scale TIFF image into a binary image, using a threshold value. Therefore, when a document needs to be converted to the TIFF file format, it is possible to get or set the threshold for TIFF binarization via the [threshold_for_floyd_steinberg_dithering](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/threshold_for_floyd_steinberg_dithering/) property. The default value for this property is set to 128, and the higher this value, the darker the image.

The following example shows how to perform TIFF binarization with a specified threshold:

{{< gist "aspose-words-gists" "bd5cd6839da6238300d3e0af47d1a262" "expose-threshold-control.py" >}}

Below you can compare images on which TIFF binarization was performed at various threshold values:

<img src="saving-a-document-as-a-multipage-tiff-1.jpg" alt="saving-a-document-as-a-multipage-tiff-aspose-words-net" style="width:800px"/>

## Related APIs

- [Document.save](https://reference.aspose.com/words/python-net/aspose.words/document/save/)
- [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/)
- [save_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/save_format/)
- [Resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/)
- [horizontal_resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/horizontal_resolution/)
- [vertical_resolution](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/vertical_resolution/)
- [page_set](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/page_set/)
- [tiff_compression](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/tiff_compression/)
- [tiff_binarization_method](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/tiff_binarization_method/)
- [threshold_for_floyd_steinberg_dithering](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/threshold_for_floyd_steinberg_dithering/)
- [pixel_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/pixel_format/)
- [paper_color](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/paper_color/)
- [image_color_mode](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_color_mode/)
- [image_brightness](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_brightness/)
- [image_contrast](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/image_contrast/)
- [metafile_rendering_options](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/metafile_rendering_options/)
- [use_gdi_emf_renderer](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/use_gdi_emf_renderer/)
- [use_anti_aliasing](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/use_anti_aliasing/)
- [use_high_quality_rendering](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/use_high_quality_rendering/) 

## FAQ

1. **Q:** How can I change the resolution of the saved TIFF image?  
   **A:** Use the `horizontal_resolution` and `vertical_resolution` properties of `ImageSaveOptions`. Set them to the desired DPI before calling `document.save`. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.horizontal_resolution = 300
   options.vertical_resolution = 300
   doc.save("output.tiff", options)
   ```

2. **Q:** How do I save only specific pages of a document to a multi‑page TIFF?  
   **A:** Configure the `page_set` property with a `PageSet` that lists the required zero-based page indices. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.page_set = aw.saving.PageSet([0, 2, 4])   # saves the 1st, 3rd and 5th pages
   doc.save("selected_pages.tiff", options)
   ```

3. **Q:** Which settings control TIFF compression and how can I choose CCITT4 compression?  
   **A:** Set the `tiff_compression` property of `ImageSaveOptions` to `TiffCompression.CCITT4`. This is suitable for 1‑bit black‑and‑white images. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.tiff_compression = aw.saving.TiffCompression.CCITT4
   doc.save("compressed.tiff", options)
   ```

4. **Q:** How can I produce a 1‑bit black‑and‑white TIFF image?  
   **A:** Set `pixel_format` to `ImagePixelFormat.FORMAT_1BPP_INDEXED` and choose an appropriate compression (CCITT3 or CCITT4). Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.pixel_format = aw.saving.ImagePixelFormat.FORMAT_1BPP_INDEXED
   options.tiff_compression = aw.saving.TiffCompression.CCITT3
   doc.save("bw.tiff", options)
   ```

5. **Q:** How do I adjust the threshold used for TIFF binarization?  
   **A:** Use the `threshold_for_floyd_steinberg_dithering` property. The default is 128; increase the value for a darker image. Example:  

   ```python
   import aspose.words as aw
   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.TIFF)
   options.tiff_binarization_method = aw.saving.ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING
   options.threshold_for_floyd_steinberg_dithering = 150
   doc.save("threshold.tiff", options)
   ```
