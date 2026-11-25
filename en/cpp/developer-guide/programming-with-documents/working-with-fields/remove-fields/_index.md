---
title: Remove Fields C++
second_title: Aspose.Words for C++
articleTitle: Remove Fields
linktitle: Remove Fields
description: "Learn how to remove fields in C++. Remove fields programmatically using C++ API."
type: docs
weight: 35
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/remove-fields/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to remove fields from a Word document using Aspose.Words.

{{% /alert %}}

Sometimes it is necessary to remove a field from a document. This may occur when it needs to be replaced with a different field type or when the field is no longer needed in the document. For example the `TOC` field when saving to HTML.

To remove a field inserted into a document using [DocumentBuilder](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/).[InsertField](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertfield/), use the returned [Field](https://reference.aspose.com/words/cpp/aspose.words.fields/field/) object, which provides a convenient [Remove](https://reference.aspose.com/words/cpp/aspose.words.fields/field/remove/) method for easily removing the field from the document.

The following code example shows how to remove a field from the document:

{{< gist "aspose-words-gists" "d0181a03b1d0bad288c2c5de69ed54e6" "remove-field.h" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Various%20fields.docx).

{{% /alert %}}
