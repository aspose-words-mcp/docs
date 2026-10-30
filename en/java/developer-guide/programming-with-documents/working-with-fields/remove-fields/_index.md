---
title: Remove Fields in Java
second_title: Aspose.Words for Java
articleTitle: Remove Fields
linktitle: Remove Fields
description: "Learn how to remove fields in Java. Remove fields programmatically using Java API."
type: docs
weight: 35
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/remove-fields/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to remove fields from a Word document using Aspose.Words.

{{% /alert %}}

Sometimes it is necessary to remove a field from a document. This may occur when it needs to be replaced with a different field type or when the field is no longer needed in the document. For example the `TOC` field when saving to HTML.

To remove a field inserted into a document using [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/).[insertField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertField-int-boolean), use the returned [Field](https://reference.aspose.com/words/java/com.aspose.words/field/) object, which provides a convenient [remove()](https://reference.aspose.com/words/java/com.aspose.words/field/#remove) method for easily removing the field from the document.

The following code example shows how to remove a field from the document:

{{< gist "aspose-words-gists" "a91d9deeec5a712c459cee506e7e7fc0" "remove-field.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Various%20fields.docx).

{{% /alert %}}
