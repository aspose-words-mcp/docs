---
title: Asian Typography in C++
second_title: Aspose.Words for C++
articleTitle: Working with Asian Typography
linktitle: Working with Asian Typography
description: "Work with Asian typography using C++. Adjust Space between Asian and Latin text in C++."
type: docs
weight: 240
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-asian-typography/
timestamp: 2024-02-01-16-17-05
---

Asian Typography is a set of options for text paragraphs in documents written in Asian languages.

Aspose.Words supports Asian Typography using the [ParagraphFormat](https://reference.aspose.com/words/cpp/aspose.words/paragraphformat/) class and some of its properties.

## Automatically Adjust Space between Asian and Latin Text or Numbers

If you are designing a template with both East Asian and Latin text and  want to enhance the appearance of your form template by controlling the spaces between both types of text, you can configure your form template to automatically adjust the spaces between these two types of text. To achieve this, you can use [get_AddSpaceBetweenFarEastAndAlpha()](https://reference.aspose.com/words/cpp/aspose.words/paragraphformat/get_addspacebetweenfareastandalpha/) and [get_AddSpaceBetweenFarEastAndDigit()](https://reference.aspose.com/words/cpp/aspose.words/paragraphformat/get_addspacebetweenfareastanddigit/) properties of the `ParagraphFormat` class.

The following code example shows how to use **get_AddSpaceBetweenFarEastAndAlpha()** and **get_AddSpaceBetweenFarEastAndDigit()** properties:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-DocumentBuilderSetFormatting-DocumentBuilderSetSpacebetweenAsianandLatintext.cpp" >}}

## Set Line Break Options

The Asian Typography tab of the paragraph properties dialog box in Microsoft Word has line break group. The options of this group can be set using the [get_FarEastLineBreakControl()](https://reference.aspose.com/words/cpp/aspose.words/paragraphformat/get_fareastlinebreakcontrol/), [get_WordWrap()](https://reference.aspose.com/words/cpp/aspose.words/paragraphformat/get_wordwrap/), [get_HangingPunctuation()](https://reference.aspose.com/words/cpp/aspose.words/paragraphformat/get_hangingpunctuation/) properties of the **ParagraphFormat** class.

The following code example shows how to use these properties:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-DocumentBuilderSetFormatting-SetAsianTypographyLinebreakGroupProp.cpp" >}}




------ 

## FAQ

1. **Q:** How can I automatically add space between Asian characters and Latin letters in a document using C++?  
   **A:** Use the `ParagraphFormat::set_AddSpaceBetweenFarEastAndAlpha(true)` method on the paragraph's format. This inserts a space between Far‑East (CJK) characters and alphabetic characters. Apply the setting to each paragraph you need or set it as the default for newly created paragraphs.

2. **Q:** How do I add space between Asian characters and digits?  
   **A:** Call `ParagraphFormat::set_AddSpaceBetweenFarEastAndDigit(true)`. This property inserts a space between Far‑East characters and numeric digits, improving readability when both appear together.

3. **Q:** Which properties control line‑break behavior for Asian typography?  
   **A:** The properties `get_FarEastLineBreakControl()`, `get_WordWrap()`, and `get_HangingPunctuation()` of `ParagraphFormat` let you enable or disable line‑break control, word wrapping, and hanging punctuation for Far‑East text. Set them via the corresponding `set_` methods.

4. **Q:** Do I need any special configuration to make Asian typography work on Linux?  
   **A:** Ensure the required Asian fonts are installed on the Linux system. If a needed font is missing, configure `FontSettings::get_SubstitutionSettings()` to substitute an available font. The Asian typography properties work cross‑platform once appropriate fonts are accessible.

5. **Q:** Can I apply these Asian typography settings to an existing document without rebuilding it?  
   **A:** Yes. Load the document, iterate through its `Paragraphs`, modify the `ParagraphFormat` properties as needed, and then save the document. The changes are applied in‑place.