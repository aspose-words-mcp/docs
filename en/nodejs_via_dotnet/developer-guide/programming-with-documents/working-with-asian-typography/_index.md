---
title: Asian Typography in Node.js
second_title: Aspose.Words for Node.js
articleTitle: Working with Asian Typography
linktitle: Working with Asian Typography
description: "Work with Asian typography using Node.js. Adjust Space between Asian and Latin text in Node.js."
type: docs
weight: 240
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-asian-typography/
timestamp: 2024-02-01-16-17-05
---

Asian Typography is a set of options for text paragraphs in documents written in Asian languages.

Aspose.Words supports Asian Typography using the [ParagraphFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/) class and some of its properties.

## Automatically Adjust Space between Asian and Latin Text or Numbers

If you are designing a template with both East Asian and Latin text and  want to enhance the appearance of your form template by controlling the spaces between both types of text, you can configure your form template to automatically adjust the spaces between these two types of text. To achieve this, you can use [addSpaceBetweenFarEastAndAlpha](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/addspacebetweenfareastandalpha/) and [addSpaceBetweenFarEastAndDigit](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/addspacebetweenfareastanddigit/) properties of the `ParagraphFormat` class.

The following code example shows how to use **addSpaceBetweenFarEastAndAlpha** and **addSpaceBetweenFarEastAndDigit** properties:

{{< gist "aspose-words-gists" "a7a098b26ccfd16de13a8e6efba00217" "space-between-asian-and-latin-text.js" >}}

## Set Line Break Options

The Asian Typography tab of the paragraph properties dialog box in Microsoft Word has line break group. The options of this group can be set using the [farEastLineBreakControl](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/fareastlinebreakcontrol/), [wordWrap](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/wordwrap/), [hangingPunctuation](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/hangingpunctuation/) properties of the **ParagraphFormat** class.

The following code example shows how to use these properties:

{{< gist "aspose-words-gists" "a7a098b26ccfd16de13a8e6efba00217" "asian-typography-line-break-group.js" >}}