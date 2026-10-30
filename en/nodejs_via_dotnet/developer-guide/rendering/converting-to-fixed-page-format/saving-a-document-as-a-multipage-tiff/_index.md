---
title: Saving a Document as a Multipage TIFF
second_title: Aspose.Words for Node.js via .NET
articleTitle: Saving a Document as a Multipage TIFF
linktitle: Saving a Document as a Multipage TIFF
description: "Convert a document to a multi-page TIFF using Node.js. To determine how the document is displayed on the image you need to specify additional options: resolution, number of pages, image binarization, etc."
type: docs
weight: 30
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/saving-a-document-as-a-multipage-tiff/
timestamp: 2025-07-09-10-05-05
---

When working with documents, you often need to convert your document to a raster image file(s). This is especially relevant if you have to present your document in a readable and printable, but not editable format. For example, you can use a raster image of the first page of your document as a preview. This article describes how to convert a document to a raster image using the example of the TIFF format – one of the more popular image formats.

## Converting DOC to Multi-Page TIFF

In Aspose.Words, conversion from DOC to TIFF can be performed with one line of code, by simply passing the “save to” path and the relevant file extension to the [save](https://reference.aspose.com/words/nodejs-net/aspose.words/document/save/) method. The [save](https://reference.aspose.com/words/nodejs-net/aspose.words/document/save/) method automatically derives the [SaveFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/) from the file name extension specified in the path. The following example demonstrates how to convert a document to the TIFF format:

{{< gist "aspose-words-gists" "be83b87ff2e9278db3dae459cf6f7987" "save-as-tiff.js" >}}

## Specifying Additional Options When Rendering TIFF

You often need to specify additional options, which affect the rendering result. For this purpose, use the [ImageSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/) class, which contains properties that determine how the document is displayed on the image. You can specify the following:

- Save format to determine the list of available options ([saveFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/saveFormat/))
- Resolution ([horizontalResolution](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/horizontalResolution/), [verticalResolution](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/verticalResolution/))
- Number of pages ([pageSet](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/pageSet/))
- Color and lighting settings ([paperColor](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/paperColor/), [imageColorMode](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/imageColorMode/), [imageBrightness](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/imageBrightness/), [imageContrast](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/imageContrast/))
- Image quality ([jpegQuality](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/jpegQuality/), [scale](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/scale/), [tiffCompression](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/tiffCompression/))
- Method used to binarize the image ([tiffBinarizationMethod](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/tiffBinarizationMethod/), [thresholdForFloydSteinbergDithering](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/thresholdForFloydSteinbergDithering/))
- Pixel format for generated images ([pixelFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/pixelFormat/))
- Windows metafiles handling by Aspose.Words ([metafileRenderingOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/metafileRenderingOptions/), [useGdiEmfRenderer](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/useGdiEmfRenderer/))
- Additional options that you can see in the [ImageSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/) class

The following example shows how to convert DOC to TIFF with configured options:

{{< gist "aspose-words-gists" "be83b87ff2e9278db3dae459cf6f7987" "get-tiff-page-range.js" >}}

## Threshold for TIFF Binarization

A TIFF image can be saved in 1bpp b/w format by setting the [pixelFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/pixelFormat/) property to [Format1bppIndexed](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagepixelformat/) pixel format type, and the [tiffCompression](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/tiffCompression/) property to either [Ccitt3](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/tiffcompression/) or [Ccitt4](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/tiffcompression/).

For image segmentation, Aspose.Words uses the simplest method — thresholding. This method converts a gray-scale TIFF image into a binary image, using a threshold value. Therefore, when a document needs to be converted to the TIFF file format, it is possible to get or set the threshold for TIFF binarization via the [thresholdForFloydSteinbergDithering](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/imagesaveoptions/thresholdForFloydSteinbergDithering/) property. The default value for this property is set to 128, and the higher this value, the darker the image.

The following example shows how to perform TIFF binarization with a specified threshold:

{{< gist "aspose-words-gists" "be83b87ff2e9278db3dae459cf6f7987" "expose-threshold-control.js" >}}

Below you can compare images on which TIFF binarization was performed at various threshold values:

<img src="saving-a-document-as-a-multipage-tiff-1.jpg" alt="saving-a-document-as-a-multipage-tiff-aspose-words-net" style="width:800px"/>
