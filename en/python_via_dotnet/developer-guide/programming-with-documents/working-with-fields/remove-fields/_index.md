---
title: Remove Fields using Python
second_title: Aspose.Words for Python via .NET
articleTitle: Remove Fields
linktitle: Remove Fields
description: "Learn how to remove fields in Python. Remove fields programmatically using Python via .NET API."
type: docs
weight: 35
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/remove-fields/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to programmatically remove fields from a Word document using Aspose.Words for Python via .NET, including a code example that utilizes the `Field.remove` method.

{{% /alert %}}

Sometimes it is necessary to remove a field from a document. This may occur when it needs to be replaced with a different field type or when the field is no longer needed in the document. For example the `TOC` field when saving to HTML.

To remove a field inserted into a document using [DocumentBuilder.insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/).[insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/), use the returned [Field](https://reference.aspose.com/words/python-net/aspose.words.fields/field/) object, which provides a convenient [remove](https://reference.aspose.com/words/python-net/aspose.words.fields/field/remove/#default) method for easily removing the field from the document.

The following code example shows how to remove a field from the document:

{{< gist "aspose-words-gists" "157a60b5ef694580567e1020eb19c545" "remove-field.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Various%20fields.docx).

{{% /alert %}}