---
title: How to Find Field Properties in C#
second_title: Aspose.Words for .NET
articleTitle: Find Field Properties
linktitle: Find Field Properties
description: "How to find some field properties like field code and field result in C#."
type: docs
weight: 25
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/find-field-properties/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to locate field properties in a document programmatically.

{{% /alert %}}

A field that is inserted using [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/).[InsertField](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertfield/) returns a [Field](https://reference.aspose.com/words/net/aspose.words.fields/field/) object. This is a facade class that provides useful methods to quickly find some properties of a field.

The following code example shows how to find the field code and field result:

{{< gist "aspose-words-gists" "7c2b7b650a88375b1d438746f78f0d64" "field-code.cs" >}}

Note if you are only looking for the names of merge fields in a document, then you can instead use the built-in [GetFieldNames](https://reference.aspose.com/words/net/aspose.words.mailmerging/mailmerge/getfieldnames/) method.

The following code example shows how to get names of all merge fields in a document:

{{< gist "aspose-words-gists" "b4bab1bf22437a86d8062e91cf154494" "get-field-names.cs" >}}
