---
title: Extract Image from Word Document
second_title: Aspose.Words for .NET
articleTitle: Extract Image from Word Document
linktitle: Extract Image from Word Document
description: "Extract image from a document easily and fast instead of using Open XML SDK in C#."
type: docs
weight: 90
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/extract-image-from-word-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to extract a single image from a Word document.

{{% /alert %}}

On this page we will look at how to extract image from a document using Aspose.Words or Open XML SDK.

{{< nosnippet >}}

{{< tabs tabTotal="2" tabID="1" tabName1="Aspose.Words" tabName2="Open XML SDK" >}}

{{< tab tabNum="1" >}}

In Aspose.Words, use the [Shape](https://reference.aspose.com/words/net/aspose.words.drawing/shape/) class to work with images. To select all shape nodes use the [GetChildNodes](https://reference.aspose.com/words/net/aspose.words/compositenode/getchildnodes/) method and to extract image data use the [ImageData](https://reference.aspose.com/words/net/aspose.words.drawing/shape/imagedata/) property.

The following code example shows how to extract images from a document and save them as files:

{{< gist "aspose-words-gists" "49853740887e9a787707ab66bb4ec5e2" "extract-document-images-aspose-words.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

You can also do the same using the Open XML SDK. At the same time, note that it looks somewhat more complicated and more cumbersome.

The following code example shows how to extract images from a document and save them as files:

{{< gist "aspose-words-gists" "49853740887e9a787707ab66bb4ec5e2" "extract-document-images-open-xml.cs" >}}

{{< /tab >}}

{{< /tabs >}}

{{< /nosnippet >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/tree/master/Plugins/Aspose.WordsVsOpenXml).

{{% /alert %}}

{{% alert color="primary" %}}

For more information about Aspose.Words features please visit [How to Extract Images from a Document](/words/net/working-with-images/#how-to-extract-images-from-a-document).

{{% /alert %}}





