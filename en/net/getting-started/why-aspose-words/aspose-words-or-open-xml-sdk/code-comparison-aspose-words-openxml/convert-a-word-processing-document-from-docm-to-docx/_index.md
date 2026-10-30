---
title: Convert DOCM to DOCX
second_title: Aspose.Words for .NET
articleTitle: Convert DOCM to DOCX
linktitle: Convert DOCM to DOCX
description: "Convert DOCM to DOCX easily and fast instead of using Open XML SDK in C#."
type: docs
weight: 50
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/convert-a-word-processing-document-from-docm-to-docx/
aliases: [/net/convert-a-word-processing-document-from-the-docm-to-the-docx-file-format/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to convert DOCM documents to DOCX while preserving macros and embedded content in a compliant manner.

{{% /alert %}}

On this page we will look at how to convert a document that contains VBA code and has a .docm extension to a .docx document. With this conversion, macros and vbaProject parts stored in a document in DOCM format will not be written to the DOCX.

{{< nosnippet >}}

{{< tabs tabTotal="2" tabID="1" tabName1="Aspose.Words" tabName2="Open XML SDK" >}}

{{< tab tabNum="1" >}}

In Aspose.Words, we normally use the [Document](https://reference.aspose.com/words/net/aspose.words/document/document/) constructor of Aspose.Words API to load a document in DOCM format and the  [Document.Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save/) method to save the document to DOCX.

The following code example shows how to convert DOCM to DOCX:

{{< gist "aspose-words-gists" "b70165dae131a133c643d59a4ebd7441" "docm-to-docx-aspose-words.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

You can also do the same using the Open XML SDK. At the same time, note that it looks somewhat more complicated and more cumbersome.

The following code example modifies the specified document by verifying that the document contains a vbaProject part and removing that part. After the code removes the part, it changes the document type internally and renames the document so that it uses .docx extension.

{{< gist "aspose-words-gists" "b70165dae131a133c643d59a4ebd7441" "docm-to-docx-open-xml.cs" >}}

{{< /tab >}}
{{< /tabs >}}
{{< /nosnippet >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/tree/master/Plugins/Aspose.WordsVsOpenXml).

{{% /alert %}}

{{% alert color="primary" %}}

For more information about Aspose.Words features please visit [Convert a Document](/words/net/convert-a-document/).

{{% /alert %}}
