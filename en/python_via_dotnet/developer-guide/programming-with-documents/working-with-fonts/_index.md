---
title: Working with Fonts in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Fonts
linktitle: Working with Fonts
description: "Customize font settings using Python."
type: docs
weight: 230
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-fonts/
aliases: [/python/working-with-fonts/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to format fonts, retrieve line spacing, and apply emphasis marks, providing code examples for each operation.
{{% /alert %}}

A font is a set of characters with a certain size, color, and design. Aspose.Words allows you to work with fonts using the [fonts](https://reference.aspose.com/words/python-net/aspose.words.fonts/) namespace and the [Font](https://reference.aspose.com/words/python-net/aspose.words/font/) class.

## Font Formatting

The current font formatting is represented by the **Font** object returned by the [font](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/font/) property. The **Font** class contains a wide variety of font properties, replicating those available in Microsoft Word.

The following code example shows how to set font formatting:

{{< gist "aspose-words-gists" "6f1507edd307e59ceb7d5a73afa61526" "set-font-formatting.py" >}}

Fill properties are also available for fonts to set text fill formatting. This makes it possible to change, for example, the foreground color or the transparency of the text fill.

## Getting Font Line Spacing

Font line spacing is the vertical distance between the baselines of two consecutive lines of text. So line spacing includes the blank space between lines along with the height of the character itself.

The [line_spacing](https://reference.aspose.com/words/python-net/aspose.words/font/line_spacing/) property was introduced to the **Font** class to obtain this value, as shown in the example below:

{{< gist "aspose-words-gists" "6f1507edd307e59ceb7d5a73afa61526" "get-font-line-spacing.py" >}}

## Font EmphasisMark

Some East Asian languages use a special emphasis mark to indicate an emphasis. The **Font** class provides the [emphasis_mark](https://reference.aspose.com/words/python-net/aspose.words/font/emphasis_mark/) property to get or set the [EmphasisMark](https://reference.aspose.com/words/python-net/aspose.words/emphasismark/) enumeration values to be applied when formatting.

The following code example shows how to set the **emphasis_mark** property:

{{< gist "aspose-words-gists" "6f1507edd307e59ceb7d5a73afa61526" "set-font-emphasis-mark.py" >}}