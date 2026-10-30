---
title: Find Field Properties in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Find Field Properties
linktitle: Find Field Properties
description: "How to find some field properties like field code and field result in Node.js."
type: docs
weight: 25
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/find-field-properties/
timestamp: 2025-07-09-10-05-05
---

A field that is inserted using [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/).[insertField](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertField/) returns a [Field](https://reference.aspose.com/words/nodejs-net/aspose.words/field/) object. This is a facade class that provides useful methods to quickly find some properties of a field.

The following code example shows how to find the field code and field result:

{{< gist "aspose-words-gists" "56db351e3569b23ecfe91a2ef9339fa7" "field-code.js" >}}

------ 

## FAQ

1. **Q:** How can I retrieve the field code of a field in Aspose.Words for Node.js?  
   **A:** Use the `field.getFieldCode()` method on the `Field` object. The returned string contains the complete field code, including the field type and any switches.

2. **Q:** How do I obtain the displayed result (field result) of a field?  
   **A:** Read the `field.result` property. This returns the text that Word shows after the field is evaluated, such as the merged value of a MERGEFIELD.

3. **Q:** Can I differentiate between the field code and the field result while iterating through all fields in a document?  
   **A:** Yes. When looping through `document.range.fields`, call `field.getFieldCode()` for the definition and read `field.result` for the current output. This lets you process each part separately.

4. **Q:** Is it possible to get the type of a field (e.g., MERGEFIELD, PAGE) programmatically?  
   **A:** Yes. Read the `field.type` property: it returns a `FieldType` value, such as `FieldType.FieldMergeField` or `FieldType.FieldPage`.

5. **Q:** Are there other useful properties of a `Field` object I can access?  
   **A:** Besides `getFieldCode()` and `result`, you can use the `field.isLocked` property to check if the field is locked, `field.update()` to force an update, and `field.remove()` to delete the field from the document.