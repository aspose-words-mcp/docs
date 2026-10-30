---
title: Working with Fonts in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Fonts
linktitle: Working with Fonts
description: "Customize font settings using Node.js."
type: docs
weight: 230
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-fonts/
timestamp: 2025-07-09-10-05-05
---

A font is a set of characters with a certain size, color, and design. Aspose.Words allows you to work with fonts using the [Aspose.Words.Fonts](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/) module and the [Font](https://reference.aspose.com/words/nodejs-net/aspose.words/font/) class.

## Font Formatting

The current font formatting is represented by the **Font** object returned by the [font](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/font/) property. The **Font** class contains a wide variety of font properties, replicating those available in Microsoft Word.

The following code example shows how to set font formatting:

{{< gist "aspose-words-gists" "4977e1370d5e0deaf48bfa1197bcae98" "set-font-formatting.js" >}}

Fill properties now are also available for fonts to set fill formatting of text. It gives an ability to change, for example, the foreground color or transparency of text fill.

## Getting Font Line Spacing

Font line spacing is the vertical distance between the baselines of two consecutive lines of text. So line spacing includes the blank space between lines along with the height of the character itself.

The [lineSpacing](https://reference.aspose.com/words/nodejs-net/aspose.words/font/linespacing/) property was introduced in the [Font](https://reference.aspose.com/words/nodejs-net/aspose.words/font/) class to obtain this value as shown in the example given below:

{{< gist "aspose-words-gists" "4977e1370d5e0deaf48bfa1197bcae98" "get-font-line-spacing.js" >}}

## Font EmphasisMark

Some East Asian languages use a special emphasis mark to indicate an emphasis. The **Font** class provides the [emphasisMark](https://reference.aspose.com/words/nodejs-net/aspose.words/font/emphasismark/) property to get or set [EmphasisMark](https://reference.aspose.com/words/nodejs-net/aspose.words/emphasismark/) enumeration values to be applied in the formatting.

The following code example shows how to set the **emphasisMark** property:

{{< gist "aspose-words-gists" "4977e1370d5e0deaf48bfa1197bcae98" "set-font-emphasis-mark.js" >}}
