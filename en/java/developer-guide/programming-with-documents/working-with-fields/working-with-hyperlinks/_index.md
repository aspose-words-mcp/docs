---
title: Working with Hyperlinks in Java
second_title: Aspose.Words for Java
articleTitle: Add or Modify Hyperlinks
linktitle: Add or Modify Hyperlinks
description: "How to add a hyperlink into your document in Java using Aspose.Words for Java."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-hyperlinks/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with hyperlinks inside Word documents.

{{% /alert %}}

A hyperlink in Microsoft Word documents is the `HYPERLINK` field. In Aspose.Words, hyperlinks are implemented through the [FieldHyperlink](https://reference.aspose.com/words/java/com.aspose.words/fieldhyperlink/) class.

## Insert a Hyperlink

Use the [insertHyperlink()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHyperlink-java.lang.String-java.lang.String-boolean) method to insert a hyperlink into the document. This method accepts three parameters:

1. Text of the link to be displayed in the document
2. Link destination (URL or a name of a bookmark inside the document)
3. Boolean parameter that should be true if the `URL` is a name of a bookmark inside a document

The **insertHyperlink()** method always adds apostrophes at the beginning and end of the URL. 

{{% alert color="primary" %}}

Note that you need to specify font formatting for the hyperlink display text explicitly using the `Font` property.

{{% /alert %}}

The following code example shows how to insert a hyperlink into a document using [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/):

{{< gist "aspose-words-gists" "d94085c26baf5235d4e7ab5483980108" "insert-hyperlink.java" >}}

## Replace or Modify Hyperlinks

Hyperlink in Microsoft Word documents is a field. A field in a Word document, as we said earlier, is a complex structure consisting of multiple nodes that include field start, field code, field separator, field result and field end. Fields can be nested, contain rich content and span multiple paragraphs or sections in a document.

To replace or modify hyperlinks, it is need to find the hyperlinks in the document and replace either their text, URLs, or both.

The following code example shows how to find all hyperlinks in Word document and changes their `URL` and display name:

{{< gist "aspose-words-gists" "d94085c26baf5235d4e7ab5483980108" "replace-hyperlinks.java" >}}

## Related APIs

- [FieldHyperlink](https://reference.aspose.com/words/java/com.aspose.words/fieldhyperlink/)
- [DocumentBuilder.insertHyperlink](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHyperlink-java.lang.String-java.lang.String-boolean)
