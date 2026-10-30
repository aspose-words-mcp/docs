---
title: Working with Watermark in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Watermark
linktitle: Working with Watermark
description: "Document watermark manipulation using C#."
type: docs
weight: 340
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-watermark/
timestamp: 2025-04-16-07-02-05
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with watermarks in Word documents.

{{% /alert %}}

This topic discusses how to work programmatically with watermark using Aspose.Words. A watermark is a background image that displays behind the text in a document. A watermark can contain a text or an image represented by the [Watermark](https://reference.aspose.com/words/net/aspose.words/watermark/) class.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online document watermark](https://products.aspose.app/words/watermark).

{{% /alert %}}

## Add a Watermark to a Document

In Microsoft Word, a watermark can easily be inserted in a document using the Insert Watermark command. Aspose.Words provides the [watermark](https://reference.aspose.com/words/net/aspose.words/watermark/) class to add or remove watermark in documents. Aspose.Words provides the [WatermarkType](https://reference.aspose.com/words/net/aspose.words/watermark/type/) enumeration defining three possible types of watermarks (Text, Image, and None) to work with.

### Add Text Watermark

The following code example demonstrates how to insert a text watermark in a document by defining [TextWatermarkOptions](https://reference.aspose.com/words/net/aspose.words/textwatermarkoptions/) using the [SetText](https://reference.aspose.com/words/net/aspose.words/watermark/settext/#settext) method:

{{< gist "aspose-words-gists" "1f690a31c188a851d80d7aed4ff7e44c" "add-text-watermark.cs" >}}

### Add Image Watermark

The following code example demonstrates how to insert an image watermark in a document by defining [ImageWatermarkOptions](https://reference.aspose.com/words/net/aspose.words/imagewatermarkoptions/) using the [SetImage](https://reference.aspose.com/words/net/aspose.words/watermark/setimage/#setimage) method:

{{< gist "aspose-words-gists" "1f690a31c188a851d80d7aed4ff7e44c" "add-image-watermark.cs" >}}

Image watermark can be inserted as image, string, or stream.

The watermark can also be inserted using shape class as well. It is very easy to insert any shape or image into a header or footer and thus create a watermark of any imaginable type.

The following code example inserts a watermark into a Word document:

{{< gist "aspose-words-gists" "1f690a31c188a851d80d7aed4ff7e44c" "add-document-watermark.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}


## Remove Watermark from a Document

The [Watermark](https://reference.aspose.com/words/net/aspose.words/watermark/) class provides the remove method to remove the watermark from a document.

The following code example shows how to remove a watermark from documents:

{{< gist "aspose-words-gists" "1f690a31c188a851d80d7aed4ff7e44c" "remove-document-watermark.cs" >}}

If the watermarks are added using the [Shape](https://reference.aspose.com/words/net/aspose.words.drawing/shape/) class object then to remove the watermark from a document you have to set only the name of watermark shape during inserting and then remove watermark shape by an assigned name.

The following code example show you how to set the name of the watermark shape and remove it from the document:

{{< gist "aspose-words-gists" "1f690a31c188a851d80d7aed4ff7e44c" "set-shape-name.cs" >}}

{{< gist "aspose-words-gists" "1f690a31c188a851d80d7aed4ff7e44c" "remove-watermark-shape.cs" >}}

## Add a Watermark into a Table Cell

Sometimes you need to insert a watermark/image into a table's cell and display it outside the table, you can use the [IsLayoutInCell](https://reference.aspose.com/words/net/aspose.words.drawing/shapebase/islayoutincell/) property. This property gets or sets a flag indicating whether the shape is displayed inside a table or outside of it. Note that this property works only when you optimize the document for Microsoft Word 2010 using the [OptimizeFor](https://reference.aspose.com/words/net/aspose.words.settings/compatibilityoptions/optimizefor/) method.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "ad463bf5f128fe6e6c1485df3c046a4c" "layout-in-cell.cs" >}}
