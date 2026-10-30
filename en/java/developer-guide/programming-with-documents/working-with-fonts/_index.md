---
title: Working with Fonts in Java
second_title: Aspose.Words for Java
articleTitle: Working with Fonts
linktitle: Working with Fonts
description: "Font formatting in details using Java. Emphasis mark in Java. Get font line spacing using Java."
type: docs
weight: 230
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-fonts/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with fonts, including substitution rules and embedding.

{{% /alert %}}

A font is a set of characters with a certain size, color, and design. Aspose.Words allows you to work with fonts using the [Font](https://reference.aspose.com/words/java/com.aspose.words/font/) namespace and the [Font](https://reference.aspose.com/words/java/com.aspose.words/font/) class.

## Font Formatting

The current font formatting is represented by the **Font** object returned by the [getFont()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getFont) property. The **Font** class contains a wide variety of font properties, replicating those available in Microsoft Word.

The following code example shows how to set font formatting:

{{< gist "aspose-words-gists" "28f3c389a64ddf0eb53893ec121575c2" "set-font-formatting.java" >}}

Fill properties are also available for fonts to set text fill formatting. This makes it possible to change, for example, the foreground color or the transparency of the text fill.

## Getting Font Line Spacing

Font line spacing is the vertical distance between the baselines of two consecutive lines of text. So line spacing includes the blank space between lines along with the height of the character itself.

The [getLineSpacing()](https://reference.aspose.com/words/java/com.aspose.words/font/#getLineSpacing) property was introduced to the **Font** class to obtain this value, as shown in the example below:

{{< gist "aspose-words-gists" "28f3c389a64ddf0eb53893ec121575c2" "get-font-line-spacing.java" >}}

## Font EmphasisMark

Some East Asian languages use a special emphasis mark to indicate an emphasis. The **Font** class provides the [getEmphasisMark()](https://reference.aspose.com/words/java/com.aspose.words/font/#getEmphasisMark) property to get or set the [getEmphasisMark()](https://reference.aspose.com/words/java/com.aspose.words/emphasismark/) enumeration values to be applied when formatting.

The following code example shows how to set the **EphasisMark** property:

{{< gist "aspose-words-gists" "28f3c389a64ddf0eb53893ec121575c2" "set-font-emphasis-mark.java" >}}
