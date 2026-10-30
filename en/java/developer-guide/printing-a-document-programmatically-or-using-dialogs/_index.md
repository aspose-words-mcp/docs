---
title: Printing a Document
second_title: Aspose.Words for Java
articleTitle: Printing a Document Programmatically or Using Dialogs
linktitle: Printing a Document Programmatically or Using Dialogs
description: "Print a document using Java through Settings, Print Preview, and Print progress dialogs."
type: docs
weight: 55
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/print-a-document-programmatically-or-using-dialogs/
timestamp: 2024-01-27-14-07-04
---

This article describes how to print a word processing document using Aspose.Words API. It also demonstrates the methods of printing a document with Settings, Print Preview, and Print progress dialogs.

## Printing a Document with Settings and Print Preview Dialogs

When working with documents, it is often required to print them to a selected printer. It is helpful to utilize a print preview dialog to visually inspect how the printed document will appear and choose relevant print options.

The Aspose.Words has no built-in dialogs or forms but implements the [AsposeWordsPrintDocument](https://reference.aspose.com/words/java/com.aspose.words/asposewordsprintdocument/) class overrides both java.awt.print.Printable and java.awt.print.Pageable.

## Printing Multiple Pages on One Sheet

Aspose.Words implements the **MultipagePrintDocument** class, to fine-tune the printing operation to implement your custom logic by defining the way the document will appear on the printed page. The **MultipagePrintDocument** class provides the ability to print several pages on one sheet of paper.

{{< gist "aspose-words-gists" "c0adc651a9fe8fdc3c6c327bf3537daf" "print-multiple-pages-on-one-sheet.java" >}}

You can download an example of using the **MultipagePrintDocument** class from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/c693ec7a8957051c206edc69612094a4169f6def/Examples/DocsExamples/Java/src/main/java/DocsExamples/Rendering_and_printing/PrintDocuments.java#L46). 

The result of this code example is shown below:

![print_several_pages_on_one_sheet_aspose_words_java](print-several-pages-on-one-sheet.png)/
