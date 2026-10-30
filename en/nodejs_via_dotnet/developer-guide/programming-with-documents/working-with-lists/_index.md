---
title: Working with Lists in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Lists
linktitle: Working with Lists
description: "Create, specify formatting and restart lists in a document using Node.js."
type: docs
weight: 200
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-lists/
timestamp: 2025-07-09-10-05-05
---

A list in a Microsoft Word document is a set of list formatting properties. Lists can be used in your documents to format, arrange, and emphasize text. Lists are a great way to organize data in documents, and they make it easier for readers to understand key points.

Each list can have up to 9 levels and formatting properties, such as number style, start value, indent, tab position etc are defined separately for each level.

In Aspose.Words, working with lists is represented by the [Lists](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/) module. However, the [List](https://reference.aspose.com/words/nodejs-net/aspose.words/list/) object always belongs to the [ListCollection](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listcollection/) collection.

This topic describes how to work programmatically with lists using Aspose.Words. 

## Creating Lists by Applying List Formatting

Aspose.Words allows the easy creation of lists by applying list formatting. [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) provides the [DocumentBuilder.listFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/listformat/) property that returns a [ListFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/) object. This object has several methods to start and end a list and to increase/decrease the indent. There are two general types of lists in Microsoft Word: bulleted and numbered.

- To start a bulleted list, call [ListFormat.applyBulletDefault](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/applyBulletDefault/).
- To start a numbered list, call [ListFormat.applyNumberDefault](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/applynumberdefault/).

The bullet or number and formatting are added to the current paragraph and all further paragraphs created using [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) until [ListFormat.removeNumbers](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/removenumbers/) is called to stop bulleted list formatting.

In Word documents, lists may consist of up to nine levels. List formatting for each level specifies what bullet or number is used, left indent, space between the bullet and text etc. The following methods change the list level and apply the new level's formatting properties:

- To increase the list level of the current paragraph by one level, call [ListFormat.listIndent](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/listindent/)
- To decrease the list level of the current paragraph by one level, call [ListFormat.listOutdent](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/listoutdent/)

The methods change the list level and apply the formatting properties of the new level.

{{% alert color="primary" %}}

You can also use the [ListFormat.listLevelNumber](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listformat/listlevelnumber/) property to get or set the list level for the paragraph. The list levels are numbered 0 to 8.

{{% /alert %}}

Below example shows how to build a multilevel list.

{{< gist "aspose-words-gists" "d8326242115a099a83c0072f78763ca2" "multilevel-list-formatting.js" >}}

## Specify Formatting for a List Level

List-level objects are created automatically when a list is created. Use the properties and methods of the [ListLevel](https://reference.aspose.com/words/nodejs-net/aspose.words.lists/listlevel/) class to control the formatting of individual levels of a list.

## Restart List for each Section

You can restart a list for each section using the [isRestartAtEachSection](https://reference.aspose.com/words/nodejs-net/aspose.words/list/isrestartateachsection/) property. Note that this option is supported only in RTF, DOC and DOCX document formats. This option will be written to DOCX only if OoxmlCompliance is higher then Ecma376.

The following code example shows how to create a list and restart it for each section:

{{< gist "aspose-words-gists" "d8326242115a099a83c0072f78763ca2" "restart-list-at-each-section.js" >}}
