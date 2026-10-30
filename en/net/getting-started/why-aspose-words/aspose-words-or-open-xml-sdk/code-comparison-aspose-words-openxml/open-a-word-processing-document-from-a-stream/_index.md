---
title: Open a Document from a Stream
second_title: Aspose.Words for .NET
articleTitle: Open a Document from a Stream
linktitle: Open a Document from a Stream
description: "Load a document from a stream easily and fast instead of using Open XML SDK in C#."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/open-a-word-processing-document-from-a-stream/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to open a Word document from a stream and manage stream-based loading.

{{% /alert %}}

On this page we will look at how to load a document from a stream using Aspose.Words or Open XML SDK.

{{< nosnippet >}}

{{< tabs tabTotal="2" tabID="1" tabName1="Aspose.Words" tabName2="Open XML SDK" >}}

{{< tab tabNum="1" >}}

Simply pass a stream object that contains the document into the [Document](https://reference.aspose.com/words/net/aspose.words/document/document/) constructor.

The following code example shows how to open a document from a stream:

{{< gist "aspose-words-gists" "a230affc64d19e458a3a6a5452903946" "add-text-stream-aspose-words.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

You can also do the same using the Open XML SDK. At the same time, note that it looks somewhat more complicated and more cumbersome.

The example shown here can be used to open a Word document from an already open stream and append some text using the Open XML SDK. You can call it by passing a handle to the open stream as the first parameter and the text to add as the second. For example, the following code example opens the file in the Public Documents folder and adds text to it:

{{< gist "aspose-words-gists" "a230affc64d19e458a3a6a5452903946" "add-text-stream-open-xml.cs" >}}

{{< /tab >}}

{{< /tabs >}}

{{< /nosnippet >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/tree/master/Plugins/Aspose.WordsVsOpenXml).

{{% /alert %}}

{{% alert color="primary" %}}

For more information about Aspose.Words features please visit [Create or Load a Document](/words/net/create-or-load-a-document/#load-from-a-stream).

{{% /alert %}}
