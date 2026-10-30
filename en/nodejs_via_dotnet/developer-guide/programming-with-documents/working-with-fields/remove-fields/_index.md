---
title: Remove Fields using Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Remove Fields
linktitle: Remove Fields
description: "Learn how to remove fields in Node.js. Remove fields programmatically using Node.js via .NET API."
type: docs
weight: 35
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/remove-fields/
timestamp: 2025-07-09-10-05-05
---

Sometimes it is necessary to remove a field from the document. This may occur when it is to be replaced with a different field type or when the field is no longer needed in the document. For example a `TOC` field when saving to HTML.

To remove a field inserted into a document using [DocumentBuilder.insertField](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertfield/), use the returned [Field](https://reference.aspose.com/words/nodejs-net/aspose.words/field/) object, which provides the convenient [remove](https://reference.aspose.com/words/nodejs-net/aspose.words/field/remove/) method to easily remove the field from the document.

The following code example shows how to remove a field from the document:

{{< gist "aspose-words-gists" "87f60ea5f7e177ac68f6daae9ff2e883" "remove-field.js" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Various%20fields.docx).

{{% /alert %}}

------ 

## FAQ

1. **Q:** How can I remove a specific field type (e.g., a TOC) from a document?  
   **A:** Locate the field by iterating through `document.range.fields` and checking `field.type`. When the desired type is found, call `field.remove()`. This removes the field node while preserving the surrounding document structure.

2. **Q:** Is there a way to remove all fields from a document in one step?  
   **A:** Yes. Retrieve the collection of fields with `let fields = document.range.fields;` and loop backwards (from `fields.count - 1` to `0`) calling `fields.at(i).remove();`. Looping backwards prevents index shifting as fields are deleted.

3. **Q:** Does calling `Field.remove()` also delete the field result text that is displayed in the document?  
   **A:** `Field.remove()` deletes the entire field node, including its result text. If you need to keep the result text, read `field.result` before removal and insert it back as a plain run.

4. **Q:** Can I remove a field that was inserted with `DocumentBuilder.insertField` without using the returned `Field` object?  
   **A:** Yes. After insertion, you can retrieve the field via `document.range.fields.at(document.range.fields.count - 1)` (the last field) and then call `remove()`. However, keeping the reference returned by `insertField` is more efficient.

5. **Q:** What happens to bookmarks or hyperlinks that reference a field I have removed?  
   **A:** Removing a field does not automatically update bookmarks or hyperlinks that point to the field's start or end positions. After removal, you may need to adjust those references manually or recreate them if required.