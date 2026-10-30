---
title: Replace Fields C++
second_title: Aspose.Words for C++
articleTitle: Replace Fields with Static Text
linktitle: Replace Fields with Static Text
description: "Learn how to replace fields with text in C++. Replace fields with static data using the C++ API."
type: docs
weight: 37
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/replace-fields/
timestamp: 2024-01-27-14-07-04
---

Replacing fields is often required when you wish to save your document as a static copy. For example, when sending as an attachment in an e‑mail. Converting fields such as `DATE` or `TIME` to static text will allow the document to display the same date as when it was sent. Also, in some situations, you may need to remove the conditional `IF` fields from your document and replace them with the most recent text result instead. For example, converting the result of the `IF` field to static text so it will no longer dynamically change its value when fields in the document are updated.

The diagram below shows how the `IF` field is stored in a document:

* the text is surrounded by the special field nodes – [get_FieldStart()](https://reference.aspose.com/words/cpp/aspose.words.fields/field/get_fieldstart/) and [get_FieldEnd()](https://reference.aspose.com/words/cpp/aspose.words.fields/field/get_fieldend/)
* the [FieldSeparator](https://reference.aspose.com/words/cpp/aspose.words.fields/field/get_separator/) node separates the text within the field into the field code and field result
* the field code defines the general behavior of the field, while the field result retains the most recent result when this field is updated using Microsoft Word or Aspose.Words
* the field result is what is stored in the field and displayed in the document when viewed

![update-remove-a-field-aspose-words](updating-and-removing-a-field-1.png)

The structure can also be seen below in hierarchical form using the demo project *“DocumentExplorer”*.

![update-remove-a-field-aspose-words-2](updating-and-removing-a-field-2.png)

## Fields That Cannot be Replaced by Text

Replacing a field with static text does not work properly for some fields in a header or footer.

For example, trying to convert the `PAGE` field in a header or footer to static text will result in the same value being displayed on all pages. This is because headers and footers are repeated across multiple pages, and when they remain as fields, they are handled especially so they display the correct result for each page.

However, in the header, the `PAGE` field translates well to static run of text. This run of text will be evaluated as if it were the last page in the section, which will cause any `PAGE` field in the header to display the last page over all pages.

The following code example shows how to replace the field with its most recent result:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-UnlinkFields.cpp" >}}

## Convert Certain Field Types in Specific Document Parts

Since the **ConvertFieldsToStaticText** method accepts two parameters – the [CompositeNode](https://reference.aspose.com/words/cpp/aspose.words/compositenode/) properties and the [FieldType](https://reference.aspose.com/words/cpp/aspose.words.fields/fieldtype/) enumeration, it is possible to pass any composite node to this method. This allows fields to be converted to static text only in specific parts of the document.

For example, you can pass a [Document](https://reference.aspose.com/words/cpp/aspose.words/document/) object and convert fields of the specified type from the entire document to static text, or you can pass a [Body](https://reference.aspose.com/words/cpp/aspose.words/body/) object of a section and only convert the fields found in that body.

{{% alert color="primary" %}}

When passing a block‑level node such as a [Paragraph](https://reference.aspose.com/words/cpp/aspose.words/paragraph/), be aware that in some cases, fields can span across multiple paragraphs. If this happens it is recommended to pass the parent of the composite instead to avoid this.

{{% /alert %}}

The [FieldType](https://reference.aspose.com/words/cpp/aspose.words.fields/fieldtype/) enumeration passed to the **ConvertFieldsToStaticText** method specifies what type of fields should be convert to static text. Any other field type found in the document will remain unchanged.

The following code example shows how to select fields of a specific type – *targetFieldType* in a specific node – *compositeNode* and then convert them to static text:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-FieldsHelper-FieldsHelper.cpp" >}}

The following code example shows how to convert all `IF` fields in a document to static text:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-ConvertFieldsInDocument-ConvertFieldsInDocument.cpp" >}}

The following code  example shows how to convert all `PAGE` fields in a Body of a document to static text:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-ConvertFieldsInDocument-ConvertFieldsInDocument.cpp" >}}

The following code  example shows how to convert all `IF` fields in the last paragraph to static text:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Fields-ConvertFieldsInDocument-ConvertFieldsInDocument.cpp" >}}

------ 

## FAQ

1. **Q:** How can I replace a specific field type (e.g., `DATE`, `IF`) with its current result using C++?  
   **A:** Use the `FieldsHelper::ConvertFieldsToStaticText` helper method from the example above (it is part of the example code, not of the Aspose.Words API). Pass the document (or a specific `CompositeNode`) as the first argument and the desired `FieldType` enumeration value (e.g., `FieldType::FieldDate`, `FieldType::FieldIf`) as the second argument. The method replaces each matching field with the text stored in its field result node.

2. **Q:** Why does converting a `PAGE` field in a header to static text show the same page number on every page?  
   **A:** Header and footer sections are shared across pages. When a `PAGE` field is converted to static text, the field result is evaluated once (using the page number of the last page in the section) and the same text is placed in every header instance. To keep per‑page numbers, leave the `PAGE` field as a field or replace it only in the body where page numbers are not needed.

3. **Q:** Can I replace fields only in a particular part of the document, such as a single section or body?  
   **A:** Yes. Pass the specific node you want to process (e.g., `Section::get_Body()`, a `Paragraph`, or any `CompositeNode`) to `ConvertFieldsToStaticText`. Only fields that are descendants of that node will be converted, leaving the rest of the document untouched.

4. **Q:** What should I do if a field spans multiple paragraphs when using `ConvertFieldsToStaticText`?  
   **A:** A field can span several paragraphs: its field start and field end are then in different paragraphs. To ensure the whole field is replaced correctly, pass the parent node that contains all involved paragraphs (for example, the `Section` or the `Body`) instead of a single `Paragraph`. This way the method can locate the complete field structure.

5. **Q:** How do I replace **all** fields in a document with static text in a single call?  
   **A:** Call `Document::UnlinkFields()` (or `Range::UnlinkFields()` for a part of the document). It replaces every field with its current result text.