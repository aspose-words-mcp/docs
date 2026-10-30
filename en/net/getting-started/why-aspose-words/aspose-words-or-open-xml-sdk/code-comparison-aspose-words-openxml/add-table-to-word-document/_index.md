---
title: Add Table to Word Document
second_title: Aspose.Words for .NET
articleTitle: Add Table to Word Document
linktitle: Add Table to Word Document
description: "Add a table to a Word document easily and fast instead of using Open XML SDK in C#."
type: docs
weight: 100
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/add-table-to-word-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page outlines how to create and populate tables in a Word document using Aspose.Words.

{{% /alert %}}

On this page we will look at how to add a table to a document in a Word format using Aspose.Words or Open XML SDK.

{{< nosnippet >}}
{{< tabs tabTotal="2" tabID="1" tabName1="Aspose.Words" tabName2="Open XML SDK" >}}
{{< tab tabNum="1" >}}

In Aspose.Words a table is normally inserted using [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/). Use its methods to build a table and insert content into table cells, for example, the following:

- [StartTable](https://reference.aspose.com/words/net/aspose.words/documentbuilder/starttable/)
- [InsertCell](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertcell/)
- [EndRow](https://reference.aspose.com/words/net/aspose.words/documentbuilder/endrow/)
- [EndTable](https://reference.aspose.com/words/net/aspose.words/documentbuilder/endtable/)
- [Write](https://reference.aspose.com/words/net/aspose.words/documentbuilder/write/)

The following code example shows how to add a table to a document:

{{< gist "aspose-words-gists" "657c3f65a58ea6dba182a07a830bcf4f" "table-aspose-words.cs" >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

The basic structure of a **WordProcessingML** document consists of document and body elements, followed by one or more block-level elements, such as paragraphs. A paragraph contains one or more run elements, which is a region of text with a common set of properties, such as formatting. A run contains one or more table elements. A table element contains a range of text.

The following code example shows how to add a table to a document:

{{< gist "aspose-words-gists" "657c3f65a58ea6dba182a07a830bcf4f" "table-open-xml.cs" >}}

{{< /tab >}}
{{< /tabs >}}
{{< /nosnippet >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/tree/master/Plugins/Aspose.WordsVsOpenXml).

{{% /alert %}}

{{% alert color="primary" %}}

For more information about Aspose.Words features please visit [Working with Tables](/words/net/working-with-tables/).

{{% /alert %}}
