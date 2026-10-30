---
title: Working with Text Document in C++
second_title: Aspose.Words for C++
articleTitle: Working with Text Document
linktitle: Working with Text Document
description: "Advanced TXT document processing, lists, BiDi, headers/footer, using C++."
type: docs
weight: 430
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-text-document/
timestamp: 2024-01-27-14-07-04
---

In this article, we will learn what options can be useful for working with a text document via Aspose.Words. Please note that this is not a complete list of available options, but only an example of working with some of them.

## Add Bi-Directional Marks

You can use the [get_AddBidiMarks()](https://reference.aspose.com/words/cpp/aspose.words.saving/txtsaveoptions/get_addbidimarks/) property to specify whether to add bi-directional marks before each BiDi run when exporting in plain text format. Aspose.Words inserts Unicode Character 'RIGHT-TO-LEFT MARK' (U+200F) before each bi-directional Run in the text. This option corresponds to "Add bi-directional marks" option in MS Word File Conversion dialogue when you export to a Plain Text format. Note that it appears in dialogue only if any of Arabic or Hebrew editing languages are added in MS Word.

The following code example shows how to use **get_AddBidiMarks()** property. The default value of this property is *false*:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-AddBidiMarks.cpp" >}}

## Recognize List Items During Loading TXT

Aspose.Words can import list item of a text file as list numbers or plain text in its document object model. The [get_DetectNumberingWithWhitespaces()](https://reference.aspose.com/words/cpp/aspose.words.loading/txtloadoptions/get_detectnumberingwithwhitespaces/) property allows to specify how numbered list items are recognized when a document is imported from plain text format:

* If this option is set to *true*, whitespaces are also used as list number delimiters: list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both whitespaces and dot (".") symbols.
* If this option is set to *false*, lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "*", "-" or "o").

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-DetectNumberingWithWhitespaces.cpp" >}}

## How to Handle Leading and Trailing spaces During Loading TXT

You can control the way of handling leading and trailing spaces during loading TXT file. The leading spaces could be trimmed, preserved or converted to indent and trailing spaces could be trimmed or preserved.

The following code example shows how to trim leading and trailing spaces while importing TXT file:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-HandleSpacesOptions.cpp" >}}

## Export Header and Footer in Output TXT

If you want to export header and footer in output TXT document, you can use the [get_ExportHeadersFootersMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/txtsaveoptionsbase/get_exportheadersfootersmode/) property. This property specifies the way headers and footers are exported to the plain text format.

The following code example shows how to export headers and footers to plain text format:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-ExportHeadersFootersMode.cpp" >}}

## Export List Indentation in Output TXT

Aspose.Words introduced the [TxtListIndentation](https://reference.aspose.com/words/cpp/aspose.words.saving/txtlistindentation/) class that allows specifying how list levels are indented while exporting to a plain text format. While working with [TxtSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/txtsaveoptions/), the [get_ListIndentation()](https://reference.aspose.com/words/cpp/aspose.words.saving/txtsaveoptions/get_listindentation/) property is provided to specify the character to be used for indenting list levels and count specifying how many characters to use as indentation per one list level.

The default value for character property is '\0' indicating that there is no indentation. For count property, the default value is 0 which means no indentation.

### Using Tab Character

The following code example shows how to export list levels using tab characters:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-UseTabCharacterPerLevelForListIndentation.cpp" >}}

### Using Space Character

The following code example shows how to export list levels using space characters:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-UseSpaceCharacterPerLevelForListIndentation.cpp" >}}

### Using Default Indentation

The following code example shows how to export list levels using default indentation:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithTxt-DefaultLevelForListIndentation.cpp" >}}

------  

## FAQ

1. **Q:** How can I enable bi‑directional marks when saving a TXT document?  
   **A:** Set the `set_AddBidiMarks()` property of `TxtSaveOptions` to `true` before calling `Document::Save`. This inserts the Unicode RIGHT‑TO‑LEFT MARK (U+200F) before each BiDi run, preserving the correct visual order for Arabic or Hebrew text.

2. **Q:** Which option controls the detection of numbered list items when loading a plain‑text file?  
   **A:** Use the `get_DetectNumberingWithWhitespaces()` property of `TxtLoadOptions`. When set to `true`, whitespaces are treated as delimiters for list numbers, allowing recognition of Arabic‑style numbering such as “1. 1.2”. Set it to `false` to rely only on punctuation characters.

3. **Q:** How do I trim leading and trailing spaces while importing a TXT file?  
   **A:** Configure `TxtLoadOptions::set_LeadingSpacesOptions` and `TxtLoadOptions::set_TrailingSpacesOptions` to `TxtLeadingSpacesOptions::Trim` and `TxtTrailingSpacesOptions::Trim` respectively. Then load the document with these options; the spaces will be removed during import.

4. **Q:** Can headers and footers be exported to a plain‑text file?  
   **A:** Yes. Call `TxtSaveOptions::set_ExportHeadersFootersMode` with `TxtExportHeadersFootersMode::AllAtEnd` (or `TxtExportHeadersFootersMode::PrimaryOnly`) to include header and footer text in the generated TXT output.

5. **Q:** How can I customize list indentation when saving to TXT (tabs, spaces, or default)?  
   **A:** Get the `TxtListIndentation` object via `TxtSaveOptions::get_ListIndentation()`, call `TxtListIndentation::set_Character` with `'\t'` for tabs or `' '` for spaces, and `TxtListIndentation::set_Count` (e.g., `4` for four spaces). If you leave the character as `'\0'` and count as `0`, no indentation is added.