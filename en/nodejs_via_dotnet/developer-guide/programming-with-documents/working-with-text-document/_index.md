---
title: Working with Text Document
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Text Document
linktitle: Working with Text Document
description: "Work with a text document and modify its objects using Node.js."
type: docs
weight: 430
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-text-document/
timestamp: 2025-07-09-10-05-05
---

In this article, we will learn what options can be useful for working with a text document via Aspose.Words. Please note that this is not a complete list of available options, but only an example of working with some of them.

## Add Bi-Directional Marks

You can use [addBidiMarks](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/txtsaveoptions/addBidiMarks/) property to specify whether to add bi-directional marks before each BiDi run when exporting in plain text format. Aspose.Words inserts Unicode Character 'RIGHT-TO-LEFT MARK' (U+200F) before each bi-directional [Run](https://reference.aspose.com/words/nodejs-net/aspose.words/run/) in the text. This option corresponds to "Add bi-directional marks" option in MS Word File Conversion dialogue when you export to a Plain Text format. Note that it appears in dialogue only if any of Arabic or Hebrew editing languages are added in MS Word.

The following code example shows how to use [addBidiMarks](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/txtsaveoptions/addBidiMarks/) property. The default value of this property is `False`:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "add-bidi-marks.js" >}}

## Recognize List Items During Loading TXT

Aspose.Words can import list item of a text file as list numbers or plain text in its document object model. The [detectNumberingWithWhitespaces](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/txtloadoptions/detectNumberingWithWhitespaces/) property allows specifying how numbered list items are recognized when a document is imported from plain text format:

* If this option is set to `True`, whitespaces are also used as list number delimiters: list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both whitespaces and dot (".") symbols.
* If this option is set to `False`, lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "*", "-" or "o").

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "detect-numbering-with-whitespaces.js" >}}

## Handle Leading and Trailing spaces During Loading TXT

You can control the way of handling leading and trailing spaces during loading TXT file. The leading spaces could be trimmed, preserved or converted to indent and trailing spaces could be trimmed or preserved.

The following code example shows how to trim leading and trailing spaces while importing TXT file:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "handle-spaces-options.js" >}}

## Detect Document Text Direction

Aspose.Words provides [documentDirection](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/txtloadoptions/documentDirection/) property in [TxtLoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/txtloadoptions/) class to detect the text direction (RTL / LTR) in the document. This property sets or gets document text directions provided in [documentDirection](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/txtloadoptions/documentdirection/) enumeration. The default value is left to right.

The following code example shows how to detect text direction of the document while importing TXT file:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "document-text-direction.js" >}}

## Export Header and Footer in Output TXT

If you want to export header and footer in output TXT document, you can use [exportHeadersFootersMode](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/txtsaveoptionsbase/exportHeadersFootersMode/) property. This property specifies the way headers and footers are exported to the plain text format.

The following code example shows how to export headers and footers to plain text format:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "export-headers-footers-mode.js" >}}

## Export List Indentation in Output TXT

Aspose.Words introduced [TxtListIndentation](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/txtlistindentation/) class that allows specifying how list levels are indented while exporting to a plain text format. While working with [TxtSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/txtsaveoptions/), the [listIndentation](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/txtsaveoptions/listindentation/) property is provided to specify the character to be used for indenting list levels and count specifying how many characters to use as indentation per one list level. The default value for character property is '\0' indicating that there is no indentation. For count property, the default value is 0 which means no indentation.

### Using Tab Character

The following code example shows how to export list levels using tab characters:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "use-tab-for-list-indentation.js" >}}

### Using Space Character

The following code example shows how to export list levels using space characters:

{{< gist "aspose-words-gists" "ee038b97a80cf17ce52665651e81d832" "use-space-for-list-indentation.js" >}}

------ 

## FAQ

1. **Q:** How can I include bi‑directional marks when saving a document to plain text?  
   **A:** Set the `addBidiMarks` property of `TxtSaveOptions` to `true`. This inserts a RIGHT‑TO‑LEFT MARK (U+200F) before each BiDi run, ensuring correct display of Arabic or Hebrew text in the exported TXT file.

2. **Q:** My numbered lists are not recognized when loading a TXT file. What should I do?  
   **A:** Enable `detectNumberingWithWhitespaces` on `TxtLoadOptions`. When set to `true`, the loader treats whitespaces as valid delimiters for list numbers, allowing both “1.” and “1 ” styles to be detected correctly.

3. **Q:** How do I control leading and trailing spaces while importing a TXT document?  
   **A:** Use the `leadingSpacesOptions` and `trailingSpacesOptions` properties of `TxtLoadOptions`. You can choose to trim, preserve, or convert leading spaces to indents, and similarly decide how trailing spaces are handled.

4. **Q:** Can I export headers and footers to a plain‑text file?  
   **A:** Yes. Set the `exportHeadersFootersMode` property of `TxtSaveOptions` to the desired mode (e.g., `TxtExportHeadersFootersMode.AllAtEnd`). This determines whether headers, footers, or both are included in the TXT output.

5. **Q:** How can I customize list indentation in the exported TXT file?  
   **A:** Set the `character` and `count` properties of the read-only `listIndentation` object of `TxtSaveOptions`, for example, `saveOptions.listIndentation.character = '\t'; saveOptions.listIndentation.count = 1;`.