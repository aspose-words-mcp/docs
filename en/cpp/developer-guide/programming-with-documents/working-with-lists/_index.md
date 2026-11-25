---
title: Working With Lists in C++
second_title: Aspose.Words for C++
articleTitle: Working With Lists
linktitle: Working With Lists
description: "Introduction to numbering formatting feature in Aspose.Words for C++."
type: docs
weight: 200
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-lists/
timestamp: 2024-01-30-16-22-34
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with lists, including numbering and formatting.

{{% /alert %}}

A list in a Microsoft Word document is a set of paragraph formatting properties. Lists can be used in documents to structure, arrange, and highlight text. Lists are a great way to organize data in documents in a way that makes it easy for readers to absorb and understand key points.

Each list can have up to 9 levels, and formatting properties such as number style, start value, indentation, tab position, and others are defined separately for each level.

In Aspose.Words, working with lists is represented by the [Lists](https://reference.aspose.com/words/cpp/aspose.words.lists/) namespace. However, the [List](https://reference.aspose.com/words/cpp/aspose.words.lists/list/) object always belongs to the [ListCollection](https://reference.aspose.com/words/cpp/aspose.words.lists/listcollection/).

This article describes programmatically working with lists using Aspose.Words.

## Create Lists by Applying List Formatting

Aspose.Words allows the easy creation of lists by applying list formatting. [DocumentBuilder](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/) provides the [get_ListFormat()](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/get_listformat/) property that returns a **ListFormat** object. This object has several methods to start and end a list and to increase/decrease the indent. There are two general types of lists in Microsoft Word: bulleted and numbered:

- To start a bulleted list, call [ApplyBulletDefault](https://reference.aspose.com/words/cpp/aspose.words.lists/listformat/applybulletdefault/)
- To start a numbered list, call [ApplyNumberDefault](https://reference.aspose.com/words/cpp/aspose.words.lists/listformat/applynumberdefault/)

The bullet or number and formatting are added to the current paragraph and all further paragraphs created using **DocumentBuilder** until [RemoveNumbers](https://reference.aspose.com/words/cpp/aspose.words.lists/listformat/removenumbers/) is called to stop bulleted list formatting.

In Word documents, lists may consist of up to nine levels. List formatting for each level specifies what bullet or number is used, left indent, space between the bullet and text etc. The following methods change the list level and apply the new level's formatting properties:

- To increase the list level of the current paragraph by one level, call [ListIndent](https://reference.aspose.com/words/cpp/aspose.words.lists/listformat/listindent/)
- To decrease the list level of the current paragraph by one level, call [ListOutdent](https://reference.aspose.com/words/cpp/aspose.words.lists/listformat/listoutdent/)

You can also use the [get_ListLevelNumber()](https://reference.aspose.com/words/cpp/aspose.words.lists/listformat/get_listlevelnumber/) property to get or set the list level for the paragraph.

{{% alert color="primary" %}}

The list levels are numbered 0 to 8.

{{% /alert %}}

The following code example shows how to build a multilevel list:

{{< gist "aspose-words-gists" "3cea17411b8dd8066ca5ceddd7829bde" "multilevel-list-formatting.h" >}}

## Specify Formatting for a List Level

List-level objects are created automatically when a list is created. Use the properties and methods of the [ListLevel](https://reference.aspose.com/words/cpp/aspose.words.lists/listlevel/) class to control the formatting of individual levels of a list.

## Restart List for each Section

You can restart a list for each section using the [get_IsRestartAtEachSection()](https://reference.aspose.com/words/cpp/aspose.words.lists/list/get_isrestartateachsection/) property. Note that this option is supported only in RTF, DOC and DOCX document formats. This option will be written to DOCX only if OoxmlCompliance is higher then Ecma376.

The following code example shows how to create a list and restart it for each section:

{{< gist "aspose-words-gists" "3cea17411b8dd8066ca5ceddd7829bde" "restart-list-at-each-section.h" >}}
