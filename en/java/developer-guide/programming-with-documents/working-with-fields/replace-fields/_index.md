---
title: Replace Fields Java
second_title: Aspose.Words for Java
articleTitle: Replace Fields with Static Text
linktitle: Replace Fields with Static Text
description: "Learn how to replace fields with text in Java. Replace fields with static data using the Java API."
type: docs
weight: 37
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/replace-fields/
aliases: [/java/how-to-replace-or-modify-hyperlinks-and-replace-fields-with-static-text/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to replace fields in a document programmatically.

{{% /alert %}}

Replacing fields is often required when you wish to save your document as a static copy. For example, when sending as an attachment in an e-mail. Converting fields such as `DATE` or `TIME` to static text will allow the document to display the same date as when it was sent. Also, in some situations, you may need to remove the conditional `IF` fields from your document and replace them with the most recent text result instead. For example, converting the result of the `IF` field to static text so it will no longer dynamically change its value when fields in the document are updated.

The diagram below shows how the `IF` field is stored in a document:

* the text is surrounded by the special field nodes – [FieldStart](https://reference.aspose.com/words/java/com.aspose.words/fieldstart/) and [FieldEnd](https://reference.aspose.com/words/java/com.aspose.words/fieldend/)
* the [FieldSeparator](https://reference.aspose.com/words/java/com.aspose.words/fieldseparator/) node separates the text within the field into the field code and field result
* the field code defines the general behavior of the field, while the field result retains the most recent result when this field is updated using Microsoft Word or Aspose.Words
* the field result is what is stored in the field and displayed in the document when viewed

![update-remove-a-field-aspose-words](updating-and-removing-a-field-1.png)

The structure can also be seen below in hierarchical form using the [demo project *“DocumentExplorer”*](https://github.com/aspose-words/Aspose.Words-for-Java/tree/master/Examples/DocsExamples/Java/src/main/java/DocsExamples/Document_explorer)*.*

![update-remove-a-field-aspose-words-2](updating-and-removing-a-field-2.png)

## Fields That Cannot be Replaced by Text

Replacing a field with static text does not work properly for some fields in a header or footer.

For example, trying to convert the `PAGE` field in a header or footer to static text will result in the same value being displayed on all pages. This is because headers and footers are repeated across multiple pages, and when they remain as fields, they are handled especially so they display the correct result for each page.

However, in the header, the `PAGE` field translates well to static run of text. This run of text will be evaluated as if it were the last page in the section, which will cause any `PAGE` field in the header to display the last page over all pages.

The following code example shows how to replace the field with its most recent result:

{{< gist "aspose-words-gists" "13297c901241a5a87660303fbcdd8a92" "unlink-fields.java" >}}

## Convert Certain Field Types in Specific Document Parts

Since the **ConvertFieldsToStaticText** method accepts two parameters – the [CompositeNode](https://reference.aspose.com/words/java/com.aspose.words/compositenode/) properties and the [FieldType](https://reference.aspose.com/words/java/com.aspose.words/fieldtype/) enumeration, it is possible to pass any composite node to this method. This allows fields to be converted to static text only in specific parts of the document.

For example, you can pass a [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) object and convert fields of the specified type from the entire document to static text, or you can pass a [Body](https://reference.aspose.com/words/java/com.aspose.words/body/) object of a section and only convert the fields found in that body.

{{% alert color="primary" %}}

When passing a block-level node such as a [Paragraph](https://reference.aspose.com/words/java/com.aspose.words/paragraph/), be aware that in some cases, fields can span across multiple paragraphs. If this happens it is recommended to pass the parent of the composite instead to avoid this.

{{% /alert %}}

The [FieldType](https://reference.aspose.com/words/java/com.aspose.words/fieldtype/) enumeration passed to the **ConvertFieldsToStaticText** method specifies what type of fields should be convert to static text. Any other field type found in the document will remain unchanged.

The following code example shows how to select fields of a specific type – *targetFieldType* in a specific node – *compositeNode* and then convert them to static text:

{{< gist "aspose-words-gists" "13297c901241a5a87660303fbcdd8a92" "convert-fields-to-static-text.java" >}}

The following code example shows how to convert all `IF` fields in a document to static text:

{{< gist "aspose-words-gists" "13297c901241a5a87660303fbcdd8a92" "unlink-fields-in-document.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Linked%20fields.docx).

{{% /alert %}}

The following code  example shows how to convert all `PAGE` fields in a Body of a document to static text:

{{< gist "aspose-words-gists" "13297c901241a5a87660303fbcdd8a92" "unlink-fields-in-body.java" >}}

The following code  example shows how to convert all `IF` fields in the last paragraph to static text:

{{< gist "aspose-words-gists" "13297c901241a5a87660303fbcdd8a92" "unlink-fields-in-paragraph.java" >}}

## Related APIs

- [FieldStart](https://reference.aspose.com/words/java/com.aspose.words/fieldstart/)
- [FieldEnd](https://reference.aspose.com/words/java/com.aspose.words/fieldend/)
- [FieldSeparator](https://reference.aspose.com/words/java/com.aspose.words/fieldseparator/)
- [FieldType](https://reference.aspose.com/words/java/com.aspose.words/fieldtype/)

## FAQ

1. **Q:** How can I replace a field with its current result as static text?  
   **A:** Call `doc.unlinkFields()` to replace every field with its last result. To convert only fields of a certain type, use the `convertFieldsToStaticText` method shown above, passing the node that contains the fields (e.g., `Document`, `Body`, or `Paragraph`) and the `FieldType`. It replaces each matching field with its last evaluated result, leaving plain text in the document.

2. **Q:** Which field types should not be replaced with static text in headers or footers?  
   **A:** Fields that depend on page context, such as `PAGE`, `NUMPAGES`, and other pagination‑related fields, should be avoided in headers/footers because converting them to static text will cause the same value to appear on every page.

3. **Q:** How do I replace fields only in a particular part of the document, like a single section body?  
   **A:** Retrieve the desired `CompositeNode` (for example, `Section.getBody()`) and pass it to `convertFieldsToStaticText`. This limits the conversion to that node and its descendants, leaving the rest of the document untouched.

4. **Q:** What if a field spans multiple paragraphs—will the conversion still work?  
   **A:** When a field crosses paragraph boundaries, pass the parent node that contains the whole field (e.g., the `Section` or `Document`) instead of an individual `Paragraph`. This ensures the method can locate the complete field structure and replace it correctly.

5. **Q:** How can I safely replace `PAGE` fields in a header without breaking page numbering?  
   **A:** Instead of converting the `PAGE` field to static text, copy its current result into a plain `Run` node and then remove the original field. This preserves the displayed page number for the current state while preventing further automatic updates.