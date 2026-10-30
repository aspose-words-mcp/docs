---
title: Saving a Document as a Multipage TIFF in C#
second_title: Aspose.Words for .NET
articleTitle: Saving a Document as a Multipage TIFF
linktitle: Saving a Document as a Multipage TIFF
description: "Convert a document to a multi-page TIFF using C#. To determine how the document is displayed on the image you need to specify additional options: resolution, number of pages, image binarization, etc."
type: docs
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/saving-a-document-as-a-multipage-tiff/
timestamp: 2024-07-10-14-38-57
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to save a document as a multi-page TIFF image.

{{% /alert %}}

When working with documents, you often need to convert your document to a raster image file(s). This is especially relevant if you have to present your document in a readable and printable, but not editable format. For example, you can use a raster image of the first page of your document as a preview. This article describes how to convert a document to a raster image using the example of the TIFF format – one of the more popular image formats.

## Converting DOC to Multi-Page TIFF

In Aspose.Words, conversion from DOC to TIFF can be performed with one line of code, by simply passing the “save to” path and the relevant file extension to the [Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save) method. The **Save** method automatically derives the `SaveFormat` from the file name extension specified in the path. The following example demonstrates how to convert a document to the TIFF format:

{{< gist "aspose-words-gists" "b20a0ec0e1ff0556aa20d12f486e1963" "save-as-tiff.cs" >}}

## Specifying Additional Options When Rendering TIFF

You often need to specify additional options, which affect the rendering result. For this purpose, use the [ImageSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/) class, which contains properties that determine how the document is displayed on the image. You can specify the following:

- Save format to determine the list of available options ([SaveFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/saveformat/))
- Resolution ([HorizontalResolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/horizontalresolution/), [VerticalResolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/verticalresolution/), [Resolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/resolution/))
- Number of pages ([PageSet](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pageset/))
- Color and lighting settings ([PaperColor](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/papercolor/), [ImageColorMode](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagecolormode/), [ImageBrightness](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagebrightness/), [ImageContrast](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagecontrast/))
- Image quality ([JpegQuality](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/jpegquality/), [Scale](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/scale/), [TiffCompression](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/tiffcompression/), [GraphicsQualityOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/graphicsqualityoptions/))
- Method used to binarize the image ([TiffBinarizationMethod](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/), [ThresholdForFloydSteinbergDithering](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/thresholdforfloydsteinbergdithering/))
- Pixel format for generated images ([PixelFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pixelformat/))
- Windows metafiles handling by Aspose.Words ([MetafileRenderingOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/metafilerenderingoptions/), [UseGdiEmfRenderer](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/usegdiemfrenderer/))
- Additional options that you can see in the **ImageSaveOptions** class

The following example shows how to convert DOC to TIFF with configured options:

{{< gist "aspose-words-gists" "b20a0ec0e1ff0556aa20d12f486e1963" "get-tiff-page-range.cs" >}}

## Threshold for TIFF Binarization

A TIFF image can be saved in 1bpp b/w format by setting the [PixelFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pixelformat/) property to Format1bppIndexed pixel format type, and the [TiffCompression](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/tiffcompression/) property to either Ccitt3 or Ccitt4.

For image segmentation, Aspose.Words uses the simplest method — thresholding. This method converts a gray‑scale TIFF image into a binary image, using a threshold value. Therefore, when a document needs to be converted to the TIFF file format, it is possible to get or set the threshold for TIFF binarization via the [ThresholdForFloydSteinbergDithering](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/thresholdforfloydsteinbergdithering/) property. The default value for this property is set to 128, and the higher this value, the darker the image.

The following example shows how to perform TIFF binarization with a specified threshold:

{{< gist "aspose-words-gists" "b20a0ec0e1ff0556aa20d12f486e1963" "expose-threshold-control.cs" >}}

Below you can compare images on which TIFF binarization was performed at various threshold values:

<img src="saving-a-document-as-a-multipage-tiff-1.jpg" alt="saving-a-document-as-a-multipage-tiff-aspose-words-net" style="width:800px"/>

## Related APIs

- [Document.Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save)
- [ImageSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/)
- [SaveFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/saveformat/)
- [Resolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/resolution/)
- [HorizontalResolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/horizontalresolution/)
- [VerticalResolution](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/verticalresolution/)
- [PageSet](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pageset/)
- [TiffCompression](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/tiffcompression/)
- [TiffBinarizationMethod](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/)
- [ThresholdForFloydSteinbergDithering](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/thresholdforfloydsteinbergdithering/)
- [PixelFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pixelformat/)
- [PaperColor](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/papercolor/)
- [ImageColorMode](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagecolormode/)
- [ImageBrightness](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagebrightness/)
- [ImageContrast](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/imagecontrast/)
- [MetafileRenderingOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/metafilerenderingoptions/)
- [UseGdiEmfRenderer](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/usegdiemfrenderer/)
- [GraphicsQualityOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/graphicsqualityoptions/)

------

## FAQ

1. **Q:** How do I convert a Word document to a multi‑page TIFF using C#?  
   **A:** Load the document with `Document`, create an `ImageSaveOptions` instance, set `SaveFormat` to `Tiff`, and call `Save` with the desired file name. Aspose.Words automatically creates one TIFF page per document page.  

   ```csharp
   Document doc = new Document("input.docx");
   ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);
   doc.Save("output.tiff", options);
   ```

2. **Q:** How can I control the resolution of the generated TIFF images?  
   **A:** Set the `Resolution` property (or `HorizontalResolution` / `VerticalResolution`) on `ImageSaveOptions`. The value is in dots per inch (DPI). Higher DPI yields sharper images but larger file size.  

   ```csharp
   ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);
   options.Resolution = 300; // 300 DPI
   doc.Save("highres.tiff", options);
   ```

3. **Q:** I only need pages 2‑4 of the document in the TIFF file. How can I export a page range?  
   **A:** Use the `PageSet` property of `ImageSaveOptions` to specify the pages (zero‑based) to render.  

   ```csharp
   ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);
   options.PageSet = new PageSet(1, 2, 3);   // pages 2,3,4
   doc.Save("range.tiff", options);
   ```

4. **Q:** How do I create a black‑and‑white (1 bpp) TIFF with binarization?  
   **A:** Set `PixelFormat` to `Format1bppIndexed`, choose a suitable `TiffCompression` (e.g., `Ccitt4`), and optionally set `TiffBinarizationMethod` to `FloydSteinbergDithering` and adjust `ThresholdForFloydSteinbergDithering` to control the binarization threshold.  

   ```csharp
   ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);
   options.PixelFormat = ImagePixelFormat.Format1bppIndexed;
   options.TiffCompression = TiffCompression.Ccitt4;
   options.TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering;
   options.ThresholdForFloydSteinbergDithering = 150; // 0‑255
   doc.Save("bw.tiff", options);
   ```

5. **Q:** Which compression methods are available for TIFF, and how do I choose one?  
   **A:** `ImageSaveOptions.TiffCompression` supports `None`, `Lzw`, `Ccitt3`, `Ccitt4`, and `Rle`. Use `Ccitt3` or `Ccitt4` for black‑and‑white images, `Lzw` for loss‑less color images, and `Rle` for simple run‑length encoding. Select the method that best balances file size and image quality for your scenario.  

   ```csharp
   ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);
   options.TiffCompression = TiffCompression.Lzw; // loss‑less color compression
   doc.Save("compressed.tiff", options);
   ```