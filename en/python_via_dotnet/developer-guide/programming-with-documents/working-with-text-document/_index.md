---
title: Working with Text Document
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Text Document
linktitle: Working with Text Document
description: "Work with a text document and modify its objects using Python."
type: docs
weight: 430
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-text-document/
aliases:
- /python/work-with-text-document/
- /python-net/work-with-text-document/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use various Aspose.Words for Python via .NET options for loading and saving plain‑text (TXT) documents, including bi‑directional marks, list detection, space handling, text direction, header/footer export, and list indentation, with code examples for each feature.
{{% /alert %}}

In this article, we will learn what options can be useful for working with a text document via Aspose.Words. Please note that this is not a complete list of available options, but only an example of working with some of them.

## Add Bi-Directional Marks

You can use the [add_bidi_marks](https://reference.aspose.com/words/python-net/aspose.words.saving/txtsaveoptions/add_bidi_marks/) property to specify whether to add bi-directional marks before each BiDi run when exporting in plain text format. Aspose.Words inserts Unicode Character 'RIGHT-TO-LEFT MARK' (U+200F) before each bi-directional Run in the text. This option corresponds to "Add bi-directional marks" option in MS Word File Conversion dialogue when you export to a Plain Text format. Note that it appears in dialogue only if any of Arabic or Hebrew editing languages are added in MS Word.

The following code example shows how to use **add_bidi_marks** property. The default value of this property is *false*:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "add-bidi-marks.py" >}}

## Recognize List Items During Loading TXT

Aspose.Words can import list item of a text file as list numbers or plain text in its document object model. The [detect_numbering_with_whitespaces](https://reference.aspose.com/words/python-net/aspose.words.loading/txtloadoptions/detect_numbering_with_whitespaces/) property allows specifying how numbered list items are recognized when a document is imported from plain text format:

* If this option is set to *true*, whitespaces are also used as list number delimiters: list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both whitespaces and dot (".") symbols.

* If this option is set to *false*, lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "*", "-" or "o").

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "detect-numbering-with-whitespaces.py" >}}

## Handle Leading and Trailing spaces During Loading TXT

You can control the way of handling leading and trailing spaces during loading TXT file. The leading spaces could be trimmed, preserved or converted to indent and trailing spaces could be trimmed or preserved.

The following code example shows how to trim leading and trailing spaces while importing TXT file:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "handle-spaces-options.py" >}}

## Detect Document Text Direction

Aspose.Words provides the [document_direction](https://reference.aspose.com/words/python-net/aspose.words.loading/txtloadoptions/document_direction/) property in the [TxtLoadOptions](https://reference.aspose.com/words/python-net/aspose.words.loading/txtloadoptions/) class to detect the text direction (RTL / LTR) in the document. This property sets or gets document text directions provided in the [DocumentDirection](https://reference.aspose.com/words/python-net/aspose.words.loading/documentdirection/) enumeration. The default value is left to *right*.

The following code example shows how to detect text direction of the document while importing TXT file:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "document-text-direction.py" >}}

## Export Header and Footer in Output TXT

If you want to export header and footer in output TXT document, you can use the [export_headers_footers_mode](https://reference.aspose.com/words/python-net/aspose.words.saving/txtsaveoptionsbase/export_headers_footers_mode/) property. This property specifies the way headers and footers are exported to the plain text format.

The following code example shows how to export headers and footers to plain text format:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "export-headers-footers-mode.py" >}}

## Export List Indentation in Output TXT

Aspose.Words introduced the [TxtListIndentation](https://reference.aspose.com/words/python-net/aspose.words.saving/txtlistindentation/) class that allows specifying how list levels are indented while exporting to a plain text format. While working with [TxtSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/txtsaveoptions/), the [list_indentation](https://reference.aspose.com/words/python-net/aspose.words.saving/txtsaveoptions/list_indentation/) property is provided to specify the character to be used for indenting list levels and count specifying how many characters to use as indentation per one list level.

The default value for character property is '\0' indicating that there is no indentation. For count property, the default value is 0 which means no indentation.

### Using Tab Character

The following code example shows how to export list levels using tab characters:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "use-tab-for-list-indentation.py" >}}

### Using Space Character

The following code example shows how to export list levels using space characters:

{{< gist "aspose-words-gists" "5e05b790a4d2258054abbf842ce6e427" "use-space-for-list-indentation.py" >}} 

## FAQ

1. **Q:** How can I include headers and footers when saving a document as plain text?  
   **A:** Set the `export_headers_footers_mode` property of `TxtSaveOptions` to one of the enum values: `ALL_AT_END` to place them at the end of the file, `PRIMARY_ONLY` to export only primary headers/footers at the start and end of each section, or `NONE` to omit them completely.

2. **Q:** How do I control the indentation of list levels in a TXT export?  
   **A:** Use the `list_indentation` property of `TxtSaveOptions`. The property is read-only: set its `character` (e.g., tab `"\t"` or space `" "` ) and `count` (number of characters per level) directly, e.g., `options.list_indentation.count = 3`.

3. **Q:** Can I preserve leading and trailing spaces when loading a TXT file?  
   **A:** Yes. Configure `TxtLoadOptions` with the appropriate `leading_spaces_options` and `trailing_spaces_options` settings (e.g., `TxtLeadingSpacesOptions.TRIM`, `PRESERVE`, or `CONVERT_TO_INDENT`) and pass them to the `Document` constructor.

4. **Q:** How do I make Aspose.Words detect the text direction (RTL or LTR) of a TXT document during import?  
   **A:** Set the `document_direction` property of `TxtLoadOptions` to `DocumentDirection.AUTO` to let the library detect direction, or explicitly set it to `DocumentDirection.LEFT_TO_RIGHT` (default) or `DocumentDirection.RIGHT_TO_LEFT` as needed.

5. **Q:** What does the `add_bidi_marks` option do when saving to TXT?  
   **A:** When `add_bidi_marks` is `True`, Aspose.Words inserts a Unicode RIGHT-TO-LEFT MARK (U+200F) before each bi‑directional run, ensuring correct display of mixed‑direction text in the plain‑text output.