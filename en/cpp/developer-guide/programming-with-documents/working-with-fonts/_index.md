---
title: Working with Fonts in C++
second_title: Aspose.Words for C++
articleTitle: Working with Fonts
linktitle: Working with Fonts
description: "Font formatting in details using C++. Emphasis mark in C++. Get font line spacing using C++."
type: docs
weight: 230
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-fonts/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with fonts, including substitution rules and embedding.

{{% /alert %}}

A font is a set of characters with a certain size, color, and design. Aspose.Words allows you to work with fonts using the [Fonts](https://reference.aspose.com/words/cpp/aspose.words.fonts/) namespace and the [Font](https://reference.aspose.com/words/cpp/aspose.words/font/) class.

## Font Formatting

The current font formatting is represented by the **Font** object returned by the [get_Font()](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/get_font/) property. The **Font** class contains a wide variety of font properties, replicating those available in Microsoft Word.

The following code example shows how to set font formatting:

{{< gist "aspose-words-gists" "e00715c52c515394f53a86270bd93368" "set-font-formatting.h" >}}

Fill properties are also available for fonts to set text fill formatting. This makes it possible to change, for example, the foreground color or the transparency of the text fill.

## Getting Font Line Spacing

Font line spacing is the vertical distance between the baselines of two consecutive lines of text. So line spacing includes the blank space between lines along with the height of the character itself.

The [get_LineSpacing()](https://reference.aspose.com/words/cpp/aspose.words/font/get_linespacing/) property was introduced to the **Font** class to obtain this value, as shown in the example below:

{{< gist "aspose-words-gists" "e00715c52c515394f53a86270bd93368" "get-font-line-spacing.h" >}}

## Font EmphasisMark

Some East Asian languages use a special emphasis mark to indicate an emphasis. The **Font** class provides the [get_EmphasisMark()](https://reference.aspose.com/words/cpp/aspose.words/font/get_emphasismark/) property to get or set the [EmphasisMark](https://reference.aspose.com/words/cpp/aspose.words/emphasismark/) enumeration values to be applied when formatting.

The following code example shows how to set the **EmphasisMark** property:

{{< gist "aspose-words-gists" "e00715c52c515394f53a86270bd93368" "set-font-emphasis-mark.h" >}}
