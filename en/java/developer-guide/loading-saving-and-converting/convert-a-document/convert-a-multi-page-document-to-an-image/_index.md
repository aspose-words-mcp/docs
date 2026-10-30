---
title: Convert a Multi-page Document to an Image in Java
second_title: Aspose.Words for Java
articleTitle: Convert a Multi-page Document to an Image
linktitle: Convert a Multi-page Document to an Image
type: docs
description: "Export multi-page documents to raster images (JPG, PNG, GIF, BMP, TIFF, WebP) using Java."
weight: 37
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/convert-a-multi-page-document-to-an-image/
timestamp: 2025-06-18-10-00-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert multi-page documents into multi-frame images, including configuration of image size, resolution, and page range.

{{% /alert %}}

Aspose.Words for Java allows users to export multi-page documents to raster images. This can be useful for generating previews, archives, or visual representations of documents for non-editable use.

## What Formats Support Multi-page Export?

Aspose.Words supports multi-page export to the following raster image formats:

* Jpeg
* Gif
* Png
* Bmp
* Tiff
* WebP

## How to Export a Multi-page Document to an Image

The feature of exporting a multi-page document to an image is implemented using the [MultiPageLayout](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/) class – you can specify how the pages should be organized when saving to an image:

* [singlePage()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#singlePage) – save only the first of the specified pages
* [grid()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#grid-int-float-float) – arrange the pages in a grid, left-to-right and top-to-bottom, while specifying the number of columns
* [horizontal()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#horizontal-float) – arrange the pages horizontally side-by-side, left-to-right, in a single output
* [vertical()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#vertical-float) – arrange the pages vertically one below the other in a single output
* [tiffFrames()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#tiffFrames) – arrange each page as a separate frame in a multi-frame TIFF image, applies only to TIFF image formats

The following code example shows how to save a multi-page DOCX document as JPEG image with Horizontal layout:

{{< gist "aspose-words-gists" "90715b6eecef1740f54f3eddb072b5d2" "horizontal-layout.java" >}}

You can also customize the output file page appearance – specify [getBackColor()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#getBackColor), [getBorderColor()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#getBorderColor), and [getBorderWidth()](https://reference.aspose.com/words/java/com.aspose.words/multipagelayout/#getBorderWidth).

The following code example shows how to save a multi-page DOCX document as PNG image with Grid layout:

{{< gist "aspose-words-gists" "90715b6eecef1740f54f3eddb072b5d2" "grid-layout.java" >}}