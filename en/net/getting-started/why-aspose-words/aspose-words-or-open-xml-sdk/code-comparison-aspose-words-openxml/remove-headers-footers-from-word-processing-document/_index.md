---
title: Remove Headers and Footers from a Word Document
second_title: Aspose.Words for .NET
articleTitle: Remove Headers and Footers from a Word Document
linktitle: Remove Headers and Footers from a Word Document
description: "Remove headers or footers from a word processing document easily and fast instead of using Open XML SDK in C#."
type: docs
weight: 70
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/remove-headers-footers-from-word-processing-document/
aliases: [/net/remove-the-headers-and-footers-from-a-word-processing-document/]
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to remove headers and footers from a document.

{{% /alert %}}

On this page we will look at how to remove headers or footers from a Word processing document using Aspose.Words or Open XML SDK.

{{< nosnippet >}}

{{< tabs tabTotal="2" tabID="1" tabName1="Aspose.Words" tabName2="Open XML SDK" >}}

{{< tab tabNum="1" >}}

Aspose.Words provide API for working with headers and footers in Microsoft Word document. We can use the [Section.HeadersFooters](https://reference.aspose.com/words/net/aspose.words/section/headersfooters/) object to get the collection of header/footer in a document section. The [HeaderFooter](https://reference.aspose.com/words/net/aspose.words/headerfooter/) class is a container for section header or footer text. That being said, **HeaderFooter** is a section-level node and can only be a child of a section. There can be only one or each **HeaderFooter** of [HeaderFooterType](https://reference.aspose.com/words/net/aspose.words/headerfootertype/) in a section.

The following code example shows how to remove header and footer from a Word document:

{{< gist "aspose-words-gists" "3fbf1435ff3b2e08f9968067e177307d" "remove-header-footer-aspose-words.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

You can also do the same using the Open XML SDK. At the same time, note that it looks somewhat more complicated and more cumbersome.

The method works with the document you specify, deleting all of the header and footer parts and references to those parts. The code starts by opening the document, using the `Open` method and indicating that the document should be opened for read/write access (the final true parameter). Given the open document, the code uses the **MainDocumentPart** property to navigate to the main document, storing the reference in a variable named docPart.

Given a reference to the document part, the code next determines if it has any work to do─that is, if the document contains any headers or footers. This simple method **DeleteParts** provides a shortcut for deleting a collection of parts.

To remove the stranded references, the code first retrieves a collection of **HeaderReference** elements, converts the collection to a List, and then loops through the collection, calling the **Remove** method for each element found.

The following code example shows how to remove header and footer from a Word document:

{{< gist "aspose-words-gists" "3fbf1435ff3b2e08f9968067e177307d" "remove-header-footer-open-xml.cs" >}}

{{< /tab >}}

{{< /tabs >}}

{{< /nosnippet >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/tree/master/Plugins/Aspose.WordsVsOpenXml).

{{% /alert %}}

{{% alert color="primary" %}}

For more information about Aspose.Words features please visit [Working with Headers and Footers](/words/net/working-with-headers-and-footers/).

{{% /alert %}}
