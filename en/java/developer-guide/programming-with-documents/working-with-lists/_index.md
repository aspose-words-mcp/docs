---
title: Working with Lists in Java
second_title: Aspose.Words for Java
articleTitle: Working with Lists
linktitle: Working with Lists
description: "Introduction to numbering formatting feature in Aspose.Words for Java."
type: docs
weight: 200
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-lists/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with lists, including numbering and formatting.

{{% /alert %}}

A list in a Microsoft Word document is a set of paragraph formatting properties. Lists can be used in documents to structure, arrange, and highlight text. Lists are a great way to organize data in documents in a way that makes it easy for readers to absorb and understand key points.

Each list can have up to 9 levels, and formatting properties such as number style, start value, indentation, tab position, and others are defined separately for each level.

In Aspose.Words, lists are represented by the [List](https://reference.aspose.com/words/java/com.aspose.words/list/) class. A [List](https://reference.aspose.com/words/java/com.aspose.words/list/) object always belongs to the [ListCollection](https://reference.aspose.com/words/java/com.aspose.words/listcollection/).

This article describes programmatically working with lists using Aspose.Words.

## Create Lists by Applying List Formatting

Aspose.Words allows the easy creation of lists by applying list formatting. [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) provides the [getListFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getListFormat) property that returns a **ListFormat** object. This object has several methods to start and end a list and to increase/decrease the indent. There are two general types of lists in Microsoft Word: bulleted and numbered:

- To start a bulleted list, call [ListFormat.applyBulletDefault](https://reference.aspose.com/words/java/com.aspose.words/listformat/#applyBulletDefault)
- To start a numbered list, call [ListFormat.applyNumberDefault](https://reference.aspose.com/words/java/com.aspose.words/listformat/#applyNumberDefault)

The bullet or number and formatting are added to the current paragraph and all further paragraphs created using **DocumentBuilder** until [removeNumbers()](https://reference.aspose.com/words/java/com.aspose.words/listformat/#removeNumbers) is called to stop bulleted list formatting.

In Word documents, lists may consist of up to nine levels. List formatting for each level specifies what bullet or number is used, left indent, space between the bullet and text etc. The following methods change the list level and apply the new level's formatting properties:

- To increase the list level of the current paragraph by one level, call [ListFormat.listIndent](https://reference.aspose.com/words/java/com.aspose.words/listformat/#listIndent)
- To decrease the list level of the current paragraph by one level, call [ListFormat.listOutdent](https://reference.aspose.com/words/java/com.aspose.words/listformat/#listOutdent)

You can also use the [setListLevelNumber()](https://reference.aspose.com/words/java/com.aspose.words/listformat/#setListLevelNumber-int) property to get or set the list level for the paragraph.

{{% alert color="primary" %}}

The list levels are numbered 0 to 8.

{{% /alert %}}

The following code example shows how to build a multilevel list:

{{< gist "aspose-words-gists" "bcc8db50f6937463ef0f1acd71da30a8" "multilevel-list-formatting.java" >}}

## Specify Formatting for a List Level

List-level objects are created automatically when a list is created. Use the properties and methods of the [ListLevel](https://reference.aspose.com/words/java/com.aspose.words/listlevel/) class to control the formatting of individual levels of a list.

## Restart List for each Section

You can restart a list for each section using the [isRestartAtEachSection()](https://reference.aspose.com/words/java/com.aspose.words/list/#isRestartAtEachSection) property. Note that this option is supported only in RTF, DOC and DOCX document formats. This option will be written to DOCX only if OoxmlCompliance is higher then Ecma376.

The following code example shows how to create a list and restart it for each section:

{{< gist "aspose-words-gists" "bcc8db50f6937463ef0f1acd71da30a8" "restart-list-at-each-section.java" >}}

## FAQ

1. **Q:** How do I start a bulleted list using Aspose.Words for Java?  
   **A:** Use the `DocumentBuilder` object, access its `ListFormat` property, and call `applyBulletDefault()`. The bullet formatting will be applied to the current paragraph and all subsequent paragraphs until `removeNumbers()` is called.

2. **Q:** How can I create a multilevel numbered list and control each level's appearance?  
   **A:** After starting a list with `applyNumberDefault()`, use `ListLevel` objects (available via `builder.getListFormat().getList().getListLevels()`) to set properties such as `numberStyle`, `font`, `alignment`, and `tabPosition` for each level (0‑8). Adjust the level with `listIndent()` and `listOutdent()` as needed.

3. **Q:** Is it possible to restart numbering for each new section in a document?  
   **A:** Yes. Set the `IsRestartAtEachSection` property of the `List` object to `true`. This works for RTF, DOC, and DOCX formats and is written to DOCX only when the document's `OoxmlCompliance` is higher than `Ecma376`.

4. **Q:** How do I retrieve or change the current list level of a paragraph?  
   **A:** Use the `getListLevelNumber()` method of `ListFormat` to read the level, and `setListLevelNumber(int level)` to change it. Levels are zero‑based, ranging from 0 to 8.