---
title: Replace Fields Python
second_title: Aspose.Words for Python via .NET
articleTitle: Replace Fields with Static Text
linktitle: Replace Fields with Static Text
description: "Learn how to replace fields with text in Python. Replace fields with static data using the Python via .NET API."
type: docs
weight: 37
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/replace-fields/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page explains how to use Aspose.Words for Python via .NET to convert document fields to static text, including method usage, limitations for certain fields, and code examples.

{{% /alert %}}

Replacing fields is often required when you wish to save your document as a static copy. For example, when sending as an attachment in an e-mail. Converting fields such as `DATE` or `TIME` to static text will allow the document to display the same date as when it was sent. Also, in some situations, you may need to remove the conditional `IF` fields from your document and replace them with the most recent text result instead. For example, converting the result of the `IF` field to static text so it will no longer dynamically change its value when fields in the document are updated.

The diagram below shows how the `IF` field is stored in a document:

* the text is surrounded by the special field nodes – [FieldStart](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldstart/) and [FieldEnd](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldend/)
* the [FieldSeparator](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldseparator/) node separates the text within the field into the field code and field result
* the field code defines the general behavior of the field, while the field result retains the most recent result when this field is updated using Microsoft Word or Aspose.Words
* the field result is what is stored in the field and displayed in the document when viewed

![update-remove-a-field-aspose-words](updating-and-removing-a-field-1.png)

The structure can also be seen below in hierarchical form using the [demo project *“DocumentExplorer”*](https://github.com/aspose-words/Aspose.Words-for-.NET/tree/master/Examples/DocsExamples/DocumentExplorer)*.*

![update-remove-a-field-aspose-words-2](updating-and-removing-a-field-2.png)

## Fields That Cannot be Replaced by Text

Replacing a field with static text does not work properly for some fields in a header or footer.

For example, trying to convert the `PAGE` field in a header or footer to static text will result in the same value being displayed on all pages. This is because headers and footers are repeated across multiple pages, and when they remain as fields, they are handled especially so they display the correct result for each page.

However, in the header, the `PAGE` field translates well to static run of text. This run of text will be evaluated as if it were the last page in the section, which will cause any `PAGE` field in the header to display the last page over all pages.

The following code example shows how to replace the field with its most recent result:

{{< gist "aspose-words-gists" "e36d72df7a15934d02a89f614188a967" "unlink-fields.py" >}}

## Convert Certain Field Types in Specific Document Parts

Since the **convert_fields_to_static_text** method accepts two parameters – the [CompositeNode](https://reference.aspose.com/words/python-net/aspose.words/compositenode/) properties and the [FieldType](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldtype/) enumeration, it is possible to pass any composite node to this method. This allows fields to be converted to static text only in specific parts of the document.

For example, you can pass a [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) object and convert fields of the specified type from the entire document to static text, or you can pass a [Body](https://reference.aspose.com/words/python-net/aspose.words/body/) object of a section and only convert the fields found in that body.

{{% alert color="primary" %}}

When passing a block-level node such as a [Paragraph](https://reference.aspose.com/words/python-net/aspose.words/paragraph/), be aware that in some cases, fields can span across multiple paragraphs. If this happens it is recommended to pass the parent of the composite instead to avoid this.

{{% /alert %}}

The [FieldType](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldtype/) enumeration passed to the **convert_fields_to_static_text** method specifies what type of fields should be convert to static text. Any other field type found in the document will remain unchanged.

The following code example shows how to select fields of a specific type – *targetFieldType* in a specific node – *compositeNode* and then convert them to static text:

{{< gist "aspose-words-gists" "e36d72df7a15934d02a89f614188a967" "convert-fields-to-static-text.py" >}}

The following code example shows how to convert all `IF` fields in a document to static text:

{{< gist "aspose-words-gists" "e36d72df7a15934d02a89f614188a967" "unlink-fields-in-document.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Linked%20fields.docx).

{{% /alert %}}

The following code  example shows how to convert all `PAGE` fields in a Body of a document to static text:

{{< gist "aspose-words-gists" "e36d72df7a15934d02a89f614188a967" "unlink-fields-in-body.py" >}}

The following code  example shows how to convert all `IF` fields in the last paragraph to static text:

{{< gist "aspose-words-gists" "e36d72df7a15934d02a89f614188a967" "unlink-fields-in-paragraph.py" >}}

## Related APIs

- [FieldStart](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldstart/)
- [FieldEnd](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldend/)
- [FieldSeparator](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldseparator/)
- [FieldType](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldtype/)

## FAQ


1. **Q:** How can I replace all fields in a document with their current results?  
   **A:** Call `doc.unlink_fields()`. This walks the entire document and replaces every field with its most recently calculated result. To convert only fields of a certain type, use the `convert_fields_to_static_text` method shown above.

2. **Q:** How can I convert only specific field types, such as `IF` fields?  
   **A:** Pass the target `CompositeNode` (e.g., `Document`, `Body`, or `Section`) and the desired `FieldType` enumeration value (e.g., `FieldType.FIELD_IF`) to `FieldsHelper.convert_fields_to_static_text()`. Only fields matching the specified type will be converted; all others remain unchanged.

3. **Q:** Fields span multiple paragraphs, and conversion fails when I pass a `Paragraph` node. Why?  
   **A:** When a field spans multiple paragraphs, passing a `Paragraph` node will not process the entire field. To ensure full conversion, pass the parent composite node (e.g., `Body` or `Section`) instead, which contains the complete field structure.

4. **Q:** Why do all pages show the same page number after converting `PAGE` fields in headers or footers?  
   **A:** Converting `PAGE` fields in headers/footers replaces them with static text reflecting the last page number of the section. This is a limitation of static conversion: repeated content (headers/footers) loses dynamic context. To preserve dynamic behavior, avoid converting `PAGE` fields in headers/footers.

5. **Q:** Can I convert fields only in a specific section or body?  
   **A:** Yes. Retrieve the target `Section` object and pass its `Body` (or the `Section` itself, depending on node scope) to `FieldsHelper.convert_fields_to_static_text()`. Only fields contained within that node hierarchy will be processed.


