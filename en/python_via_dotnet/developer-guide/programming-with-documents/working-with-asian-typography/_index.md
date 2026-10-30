---
title: Asian Typography in Python
second_title: Aspose.Words for Python
articleTitle: Working with Asian Typography
linktitle: Working with Asian Typography
description: "Work with Asian typography using Python. Adjust Space between Asian and Latin text in Python."
type: docs
weight: 240
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-asian-typography/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to use Aspose.Words for Python to manage Asian typography, including automatically adjusting spacing between Asian and Latin text and configuring line‑break options. It provides code examples that demonstrate the relevant ParagraphFormat properties such as AddSpaceBetweenFarEastAndAlpha, AddSpaceBetweenFarEastAndDigit, FarEastLineBreakControl, WordWrap, and HangingPunctuation.
{{% /alert %}}

Asian Typography is a set of options for text paragraphs in documents written in Asian languages.

Aspose.Words supports Asian Typography using the [ParagraphFormat](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/) class and some of its properties.

## Automatically Adjust Space between Asian and Latin Text or Numbers

If you are designing a template with both East Asian and Latin text and  want to enhance the appearance of your form template by controlling the spaces between both types of text, you can configure your form template to automatically adjust the spaces between these two types of text. To achieve this, you can use [add_space_between_far_east_and_alpha](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/add_space_between_far_east_and_alpha/) and [add_space_between_far_east_and_digit](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/add_space_between_far_east_and_digit/) properties of the `ParagraphFormat` class.

The following code example shows how to use **add_space_between_far_east_and_alpha** and **add_space_between_far_east_and_digit** properties:

{{< gist "aspose-words-gists" "0eb0780ab42a1b0032793a6eb510da35" "space-between-asian-and-latin-text.py" >}}

## Set Line Break Options

The Asian Typography tab of the paragraph properties dialog box in Microsoft Word has line break group. The options of this group can be set using the [far_east_line_break_control](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/far_east_line_break_control/), [word_wrap](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/word_wrap/), [hanging_punctuation](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/hanging_punctuation/) properties of the **ParagraphFormat** class.

The following code example shows how to use these properties:

{{< gist "aspose-words-gists" "0eb0780ab42a1b0032793a6eb510da35" "asian-typography-line-break-group.py" >}}