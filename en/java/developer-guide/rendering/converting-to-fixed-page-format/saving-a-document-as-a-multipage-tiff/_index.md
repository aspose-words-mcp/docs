---
title: Saving a Document as a Multipage TIFF in Java
second_title: Aspose.Words for Java
articleTitle: Saving a Document as a Multipage TIFF
linktitle: Saving a Document as a Multipage TIFF
description: "Convert a document to a raster image, which is discussed on the example of the TIFF format. To determine how TIFF is displayed you need to specify additional options: resolution, number of pages, image binarization, etc using Java."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/saving-a-document-as-a-multipage-tiff/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to save a document as a multi-page TIFF image.

{{% /alert %}}

When working with documents, you often need to convert your document to a raster image file(s). This is especially relevant if you have to present your document in a readable and printable, but not editable format. For example, you can use a raster image of the first page of your document as a preview. This article describes how to convert a document to a raster image using the example of the TIFF format – one of the more popular image formats.

## Converting DOC to Multi-Page TIFF

In Aspose.Words, conversion from DOC to TIFF can be performed with one line of code, by simply passing the “save to” path and the relevant file extension to the [save()](https://reference.aspose.com/words/java/com.aspose.words/document/#save-java.io.OutputStream-com.aspose.words.SaveOptions) method. The **Save** method automatically derives the `SaveFormat` from the file name extension specified in the path. The following example demonstrates how to convert a document to the TIFF format:

{{< gist "aspose-words-gists" "402579012106180dd1687e6d7f6386b8" "save-as-tiff.java" >}}

## Specifying Additional Options When Rendering TIFF

You often need to specify additional options, which affect the rendering result. For this purpose, use the [ImageSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/) class, which contains properties that determine how the document is displayed on the image. You can specify the following:

- Save format to determine the list of available options ([getSaveFormat()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getSaveFormat))
- Resolution ([getHorizontalResolution()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getHorizontalResolution), [getVerticalResolution()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getVerticalResolution), [setResolution()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#setResolution-float))
- Number of pages ([getPageSet()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getPageSet))
- Color and lighting settings ([getPaperColor()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getPaperColor), [getImageColorMode()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getImageColorMode), [getImageBrightness()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getImageBrightness), [getImageContrast()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getImageContrast))
- Image quality ([getJpegQuality()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getJpegQuality), [getScale()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getScale), [getTiffCompression()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getTiffCompression), [getGraphicsQualityOptions()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getGraphicsQualityOptions))
- The method used to binarize the image ([getTiffBinarizationMethod()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getTiffBinarizationMethod), [getThresholdForFloydSteinbergDithering()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getThresholdForFloydSteinbergDithering))
- Pixel format for generated images ([getPixelFormat()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getPixelFormat))
- Windows metafiles handling by Aspose.Words ([getMetafileRenderingOptions()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getMetafileRenderingOptions), [getUseGdiEmfRenderer()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getUseGdiEmfRenderer))
- Additional options that you can see in the **ImageSaveOptions** class

The following example shows how to convert DOC to TIFF with configured options:

{{< gist "aspose-words-gists" "402579012106180dd1687e6d7f6386b8" "get-tiff-page-range.java" >}}

## Threshold for TIFF Binarization

A TIFF image can be saved in 1bpp b/w format by setting the [getPixelFormat()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getPixelFormat) property to Format1bppIndexed pixel format type, and the [getTiffCompression()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getTiffCompression) property to either Ccitt3 or Ccitt4.

For image segmentation, Aspose.Words uses the simplest method — thresholding. This method converts a gray-scale TIFF image into a binary image, using a threshold value. Therefore, when a document needs to be converted to the TIFF file format, it is possible to get or set the threshold for TIFF binarization via the [getThresholdForFloydSteinbergDithering()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getThresholdForFloydSteinbergDithering) property. The default value for this property is set to 128, and the higher this value, the darker the image.

The following example shows how to perform TIFF binarization with a specified threshold:

{{< gist "aspose-words-gists" "402579012106180dd1687e6d7f6386b8" "expose-threshold-control.java" >}}

Below you can compare images on which TIFF binarization was performed at various threshold values:

<img src="saving-a-document-as-a-multipage-tiff-1.jpg" alt="saving-a-document-as-a-multipage-tiff-aspose-words-java" style="width:800px"/>
