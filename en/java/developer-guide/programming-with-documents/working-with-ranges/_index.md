---
title: Working with Ranges in Java
second_title: Aspose.Words for Java
articleTitle: Working with Ranges
linktitle: Working with Ranges
description: "Introduction to Range feature in Aspose.Words for Java."
type: docs
weight: 130
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-ranges/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with ranges to manipulate spans of content.

{{% /alert %}}

{{% alert color="primary" %}}

In Aspose.Words, a Range is a “flat window” into an otherwise tree-like model of the document.

{{% /alert %}}

If you have worked with Microsoft Word Automation, you probably know that one of the main tools to examine and modify document content is the **Range** object. **Range** is like a "window" into the document content and formatting.

Aspose.Words also has the [Range](https://reference.aspose.com/words/java/com.aspose.words/range/) class and it is designed to look and act similarly to **Range** in Microsoft Word. Although **Range** cannot cover an arbitrary portion of a document and does not have a **Start** and **End**, you can access the range covered by any document node including the [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) itself. In other words, each node has its own range. The **Range** object allows you to access and modify text, bookmarks and form fields within the range.

## Retrieve Plain Text

Use the [getText()](https://reference.aspose.com/words/java/com.aspose.words/range/#getText) property to retrieve plain, unformatted text of the range.

The following code example shows how to get a plain, unformatted text of a range:

{{< gist "aspose-words-gists" "f3b385f86a13b93093c214b1e7a981bf" "ranges-get-text.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

## Delete Text

Range allows the deletion of all characters of the range by calling [delete](https://reference.aspose.com/words/java/com.aspose.words/range/#delete).

The following code example shows how to delete all characters of a range:

{{< gist "aspose-words-gists" "f3b385f86a13b93093c214b1e7a981bf" "ranges-delete-text.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Document.docx).

{{% /alert %}}
