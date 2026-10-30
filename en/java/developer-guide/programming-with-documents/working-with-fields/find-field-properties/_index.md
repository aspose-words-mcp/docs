---
title: How to Find Field Properties in Java
second_title: Aspose.Words for Java
articleTitle: Find Field Properties
linktitle: Find Field Properties
description: "How to find some field properties like field code and field result in Java"
type: docs
weight: 25
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/find-field-properties/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to locate field properties in a document programmatically.

{{% /alert %}}

A field that is inserted using [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/).[insertField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertField-int-boolean) returns a [Field](https://reference.aspose.com/words/java/com.aspose.words/field/) object. This is a facade class that provides useful methods to quickly find some properties of a field.

The following code example shows how to find the field code and field result:

{{< gist "aspose-words-gists" "75e4246a1d11ac29064f36124af0accc" "field-code.java" >}}

Note if you are only looking for the names of merge fields in a document, then you can instead use the built-in [getFieldNames()](https://reference.aspose.com/words/java/com.aspose.words/mailmerge/#getFieldNames) method.

The following code example shows how to get names of all merge fields in a document:

{{< gist "aspose-words-gists" "7d267f5905ac7f3d5144e8d4126a0d6d" "get-field-names.java" >}}

## FAQ

1. **Q:** How can I retrieve the field code of a field in Aspose.Words for Java?  
   **A:** After obtaining a `Field` object (e.g., via `DocumentBuilder.insertField` or by iterating through the document), call `field.getFieldCode()`. This method returns the complete field code string, including the field type and its arguments.

2. **Q:** How do I get the evaluated result (display text) of a field?  
   **A:** Use the `field.getResult()` method on the `Field` instance. It returns the current result of the field after evaluation, which is the text that would appear in the document.

3. **Q:** How can I list all merge field names in a document?  
   **A:** Call `document.getMailMerge().getFieldNames()`. This method returns a `String[]` containing the names of every MERGEFIELD present in the document, making it easy to enumerate them.

4. **Q:** How can I determine the type of a field (e.g., MERGEFIELD, REF) while iterating?  
   **A:** Inspect the field code returned by `field.getFieldCode()`; the first word indicates the field type. Alternatively, you can use `field.getType()` which returns a `FieldType` enum value representing the specific field type.

5. **Q:** Can I retrieve field properties from fields located in headers or footers?  
   **A:** Yes. Access the header/footer nodes via `section.getHeadersFooters()`, then iterate their child nodes to locate `Field` objects. Once you have the `Field`, `getFieldCode()` and `getResult()` work the same way as for body fields.