---
title: How to Find Field Properties
second_title: Aspose.Words for C++
articleTitle: Find Field Properties
linktitle: Find Field Properties
description: "How to find some field properties like field code and field result in C++."
type: docs
weight: 25
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/find-field-properties/
timestamp: 2024-01-27-14-07-04
---

A field that is inserted using [DocumentBuilder](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/).[InsertField](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertfield/) returns a [Field](https://reference.aspose.com/words/cpp/aspose.words.fields/field/) object. This is a facade class that provides useful methods to quickly find some properties of a field.

The following code example shows how to find the field code and field result:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-FieldsCode.cpp" >}}

Note if you are only looking for the names of merge fields in a document, then you can instead use the built-in [GetFieldNames](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/mailmerge/getfieldnames/) method.

The following code example shows how to get names of all merge fields in a document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-GetFieldNames-GetFieldNames.cpp" >}}

------  

## FAQ  

1. **Q:** How can I retrieve the field code of a field using Aspose.Words for C++?  
   **A:** After inserting or locating a field, call the `GetFieldCode()` method on the `Field` object. The method returns a `String` containing the complete field code (e.g., `MERGEFIELD  CustomerName  \* MERGEFORMAT`).  

2. **Q:** How do I obtain the result (display text) of a field?  
   **A:** Use the `Field::get_Result()` method. It returns the evaluated result of the field as a `String`. For fields that have not been updated, you may need to call `Field::Update()` first to ensure the result is current.  

3. **Q:** How can I list all merge field names in a document?  
   **A:** Call `doc->get_MailMerge()->GetFieldNames()`, which returns a `System::ArrayPtr<System::String>` with the names of all merge fields. This method is faster than iterating over each `Field` object when you only need the names.  

4. **Q:** What is the difference between using `GetFieldNames` and accessing `Field` objects directly?  
   **A:** `GetFieldNames` returns only the names of merge fields and is optimized for that purpose, while accessing `Field` objects gives you the full field object, allowing you to read properties such as the field code, result, type, and to modify or remove the field. Use `GetFieldNames` for quick name extraction; use `Field` objects when you need detailed information or manipulation.