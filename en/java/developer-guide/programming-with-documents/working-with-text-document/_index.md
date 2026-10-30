---
title: Working with Text Document in Java
second_title: Aspose.Words for Java
articleTitle: Working with Text Document
linktitle: Working with Text Document
description: "Advanced TXT document processing, lists, BiDi, headers/footer, using Java."
type: docs
weight: 430
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-text-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with plain text documents using Aspose.Words.

{{% /alert %}}

In this article, we will learn what options can be useful for working with a text document via Aspose.Words. Please note that this is not a complete list of available options, but only an example of working with some of them.

## Add Bi-Directional Marks

You can use the [setAddBidiMarks()](https://reference.aspose.com/words/java/com.aspose.words/txtsaveoptions/#setAddBidiMarks-boolean) property to specify whether to add bi-directional marks before each BiDi run when exporting in plain text format. Aspose.Words inserts Unicode Character 'RIGHT-TO-LEFT MARK' (U+200F) before each bi-directional Run in the text. This option corresponds to "Add bi-directional marks" option in MS Word File Conversion dialogue when you export to a Plain Text format. Note that it appears in dialogue only if any of Arabic or Hebrew editing languages are added in MS Word.

The following code example shows how to use **getAddBidiMarks()** property. The default value of this property is *false*:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "add-bidi-marks.java" >}}

## Recognize List Items During Loading TXT

Aspose.Words can import list item of a text file as list numbers or plain text in its document object model. The [getDetectNumberingWithWhitespaces()](https://reference.aspose.com/words/java/com.aspose.words/txtloadoptions/#getDetectNumberingWithWhitespaces) property allows specifying how numbered list items are recognized when a document is imported from plain text format:

* If this option is set to *true*, whitespaces are also used as list number delimiters: list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both whitespaces and dot (".") symbols.

* If this option is set to *false*, lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "*", "-" or "o").

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "detect-numbering-with-whitespaces.java" >}}

## Handle Leading and Trailing spaces During Loading TXT

You can control the way of handling leading and trailing spaces during loading TXT file. The leading spaces could be trimmed, preserved or converted to indent and trailing spaces could be trimmed or preserved.

The following code example shows how to trim leading and trailing spaces while importing TXT file:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "handle-spaces-options.java" >}}

## Detect Document Text Direction

Aspose.Words provides the [getDocumentDirection()](https://reference.aspose.com/words/java/com.aspose.words/txtloadoptions/#getDocumentDirection) property in the [TxtLoadOptions](https://reference.aspose.com/words/java/com.aspose.words/txtloadoptions/) class to detect the text direction (RTL / LTR) in the document. This property sets or gets document text directions provided in the [getDocumentDirection()](https://reference.aspose.com/words/java/com.aspose.words/documentdirection/) enumeration. The default value is left to *right*.

The following code example shows how to detect text direction of the document while importing TXT file:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "document-text-direction.java" >}}

## Export Header and Footer in Output TXT

If you want to export header and footer in output TXT document, you can use the [getExportHeadersFootersMode()](https://reference.aspose.com/words/java/com.aspose.words/txtsaveoptions/#getExportHeadersFootersMode) property. This property specifies the way headers and footers are exported to the plain text format.

The following code example shows how to export headers and footers to plain text format:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "export-headers-footers-mode.java" >}}

## Export List Indentation in Output TXT

Aspose.Words introduced the [TxtListIndentation](https://reference.aspose.com/words/java/com.aspose.words/txtlistindentation/) class that allows specifying how list levels are indented while exporting to a plain text format. While working with [TxtSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/txtsaveoptions/), the [getListIndentation()](https://reference.aspose.com/words/java/com.aspose.words/txtsaveoptions/#getListIndentation) property is provided to specify the character to be used for indenting list levels and count specifying how many characters to use as indentation per one list level.

The default value for character property is '\0' indicating that there is no indentation. For count property, the default value is 0 which means no indentation.

### Using Tab Character

The following code example shows how to export list levels using tab characters:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "use-tab-for-list-indentation.java" >}}

### Using Space Character

The following code example shows how to export list levels using space characters:

{{< gist "aspose-words-gists" "c92d84644de8ee6e7148950debea90d6" "use-space-for-list-indentation.java" >}}

## FAQ

1. **Q:** How can I include headers and footers when saving a document as plain text?  
   **A:** Call `TxtSaveOptions.setExportHeadersFootersMode` with the desired mode (e.g., `TxtExportHeadersFootersMode.ALL_AT_END`). This tells Aspose.Words to write header and footer text into the resulting TXT file.

2. **Q:** How do I control list indentation in the exported TXT file?  
   **A:** Use the `getListIndentation()` property of `TxtSaveOptions`. You can specify a character (tab, space, or custom) and the number of such characters per list level to achieve the required indentation.

3. **Q:** How can I preserve leading and trailing spaces when loading a TXT file?  
   **A:** Configure `TxtLoadOptions` by calling `setLeadingSpacesOptions(TxtLeadingSpacesOptions.PRESERVE)` and `setTrailingSpacesOptions(TxtTrailingSpacesOptions.PRESERVE)`. This prevents Aspose.Words from trimming or converting those spaces.

4. **Q:** What does the `getAddBidiMarks()` option do and when should I use it?  
   **A:** When `getAddBidiMarks()` is true, Aspose.Words inserts a RIGHT‑TO‑LEFT MARK (U+200F) before each bi‑directional run in the exported text. Enable it when the document contains Arabic or Hebrew text and you need the correct visual order in plain‑text files.

5. **Q:** How can I detect the text direction (RTL/LTR) of a TXT document during import?  
   **A:** Set `TxtLoadOptions.setDocumentDirection(DocumentDirection.AUTO)` before loading. Aspose.Words then detects the direction from the text and makes right‑to‑left paragraphs bidirectional (`paragraph.getParagraphFormat().getBidi()`). The default is `DocumentDirection.LEFT_TO_RIGHT`.