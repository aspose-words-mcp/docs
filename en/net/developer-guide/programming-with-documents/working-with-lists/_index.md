---
title: Working with Lists in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Lists
linktitle: Working with Lists
description: "Introduction to numbering formatting feature in Aspose.Words for .NET."
type: docs
weight: 200
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-lists/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with lists, including numbering and formatting.

{{% /alert %}}

A list in a Microsoft Word document is a set of paragraph formatting properties. Lists can be used in documents to structure, arrange, and highlight text. Lists are a great way to organize data in documents in a way that makes it easy for readers to absorb and understand key points.

Each list can have up to 9 levels, and formatting properties such as number style, start value, indentation, tab position, and others are defined separately for each level.

In Aspose.Words, working with lists is represented by the [Lists](https://reference.aspose.com/words/net/aspose.words.lists/) namespace. However, the [List](https://reference.aspose.com/words/net/aspose.words.lists/list/) object always belongs to the [ListCollection](https://reference.aspose.com/words/net/aspose.words.lists/listcollection/).

This article describes programmatically working with lists using Aspose.Words.

## Create Lists by Applying List Formatting

Aspose.Words allows the easy creation of lists by applying list formatting. [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/) provides the [ListFormat](https://reference.aspose.com/words/net/aspose.words/documentbuilder/listformat/) property that returns a **ListFormat** object. This object has several methods to start and end a list and to increase/decrease the indent. There are two general types of lists in Microsoft Word: bulleted and numbered:

- To start a bulleted list, call [ApplyBulletDefault](https://reference.aspose.com/words/net/aspose.words.lists/listformat/applybulletdefault/)
- To start a numbered list, call [ApplyNumberDefault](https://reference.aspose.com/words/net/aspose.words.lists/listformat/applynumberdefault/)

The bullet or number and formatting are added to the current paragraph and all further paragraphs created using **DocumentBuilder** until [RemoveNumbers](https://reference.aspose.com/words/net/aspose.words.lists/listformat/removenumbers/) is called to stop bulleted list formatting.

In Word documents, lists may consist of up to nine levels. List formatting for each level specifies what bullet or number is used, left indent, space between the bullet and text etc. The following methods change the list level and apply the new level's formatting properties:

- To increase the list level of the current paragraph by one level, call [ListIndent](https://reference.aspose.com/words/net/aspose.words.lists/listformat/listindent/)
- To decrease the list level of the current paragraph by one level, call [ListOutdent](https://reference.aspose.com/words/net/aspose.words.lists/listformat/listoutdent/)

You can also use the [ListLevelNumber](https://reference.aspose.com/words/net/aspose.words.lists/listformat/listlevelnumber/) property to get or set the list level for the paragraph.

{{% alert color="primary" %}}

The list levels are numbered 0 to 8.

{{% /alert %}}

The following code example shows how to build a multilevel list:

{{< gist "aspose-words-gists" "a1dfeba1e0480d5b277a61742c8921af" "multilevel-list-formatting.cs" >}}

## Specify Formatting for a List Level

List-level objects are created automatically when a list is created. Use the properties and methods of the [ListLevel](https://reference.aspose.com/words/net/aspose.words.lists/listlevel/) class to control the formatting of individual levels of a list.

## Restart List for each Section

You can restart a list for each section using the [IsRestartAtEachSection](https://reference.aspose.com/words/net/aspose.words.lists/list/isrestartateachsection/) property. Note that this option is supported only in RTF, DOC and DOCX document formats. This option will be written to DOCX only if OoxmlCompliance is higher then Ecma376.

The following code example shows how to create a list and restart it for each section:

{{< gist "aspose-words-gists" "a1dfeba1e0480d5b277a61742c8921af" "restart-list-at-each-section.cs" >}}

------

## FAQ

1. **Q:** How do I start a bulleted list using `DocumentBuilder`?  
   **A:** Call `DocumentBuilder.ListFormat.ApplyBulletDefault()`. This applies the default bullet style to the current paragraph and all subsequent paragraphs until you invoke `RemoveNumbers()`.

2. **Q:** How can I create a multilevel numbered list?  
   **A:** Begin with `ApplyNumberDefault()` to start a numbered list, then use `ListFormat.ListIndent()` to increase the level and `ListFormat.ListOutdent()` to decrease it. You can also set `ListFormat.ListLevelNumber` to jump directly to a specific level.

3. **Q:** How do I customize the bullet or number style for a particular list level?  
   **A:** Retrieve the `List` object from the current paragraph (`DocumentBuilder.CurrentParagraph.ListFormat.List`) and access its `ListLevels` collection. For the desired level, set properties such as `NumberStyle`, `Font.Name`, `Alignment`, or `NumberFormat`.

4. **Q:** How can I restart numbering for each new section in a document?  
   **A:** Set the `IsRestartAtEachSection` property of the `List` to `true`. This works for DOC, DOCX, and RTF formats; for DOCX the document's `OoxmlCompliance` must be higher than `Ecma376` for the setting to be saved.

5. **Q:** How do I stop list formatting and return to normal paragraphs?  
   **A:** Invoke `DocumentBuilder.ListFormat.RemoveNumbers()`. This removes any list formatting from the current paragraph and prevents further paragraphs from inheriting list styles.