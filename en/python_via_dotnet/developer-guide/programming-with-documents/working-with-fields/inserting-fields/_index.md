---
title: Inserting Fields in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Insert Fields
linktitle: Insert Fields
description: "Insert fields into a document in Python in different ways: using `DocumentBuilder` or DOM (Document Object Model)."
type: docs
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/inserting-fields/
aliases: [/python/inserting-fields/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to insert various types of fields into a Word document using Aspose.Words for Python via .NET, covering methods with DocumentBuilder, FieldBuilder, and the Document Object Model (DOM), each illustrated with code examples.
{{% /alert %}}

There are several different ways to insert fields into a document:

* using [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/)
* using [FieldBuilder](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldbuilder/)
* using [Aspose.Words Document Object Model (DOM)](/words/python-net/aspose-words-document-object-model/)

In this article, we will look at each way in more detail and analyze how to insert certain fields using these options.

## Inserting Fields into a Document using DocumentBuilder

In Aspose.Words the [insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/) method is used to insert new fields into a document. The first parameter accepts the full field code of the field to be inserted. The second parameter is optional and allows the field result of the field to be set manually. If this is not supplied then the field is updated automatically. You can pass None or empty to this parameter to insert a field with an empty field value. If you are not sure about the particular field code syntax, create the field in Microsoft Word first and switch to see its field code.

{{% alert color="primary" %}}

If your field code has a parameter containing a space then it must be enclosed within speech marks. Otherwise the field in both Microsoft Word and Aspose.Words may not work as expected as the parameter is treated by both as being truncated.

{{% /alert %}}

The following code example shows how to inserts a merge field into a document using **DocumentBuilder**:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-field.py" >}}

The same technique is used to insert fields nested within other fields.

The following code example shows how to insert fields nested within another field using **DocumentBuilder**:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-nested-fields.py" >}}

### Specify Locale at Field Level

A language identifier is a standard international numeric abbreviation for the language in a country or geographical region. With Aspose.Words, you can specify the Locale at the field level using the [locale_id](https://reference.aspose.com/words/python-net/aspose.words.fields/field/locale_id/) property, which gets or sets the field's locale ID.

The following code example shows how to use this option:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "specify-locale-at-field-level.py" >}}

### Insert Untyped/Empty Field

If you want to insert untyped/empty fields ({}) just like Microsoft Word allows, you can use the [insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/) method with the [FieldType.FIELD_NONE](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldtype/#field_none) parameter. To insert a field into a Word document, you can press “Ctrl + F9” key combination.

The following code example shows how to insert an empty field into the document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-field-none.py" >}}

## Inserting Fields into a Document using FieldBuilder

The alternative way to insert fields in Aspose.Words is the [FieldBuilder](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldbuilder/) class. It provides fluent interface to specify field switches and argument values as text, nodes or even nested fields.

The following code example shows how to insert a field into a document using **FieldBuilder**:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-field-using-field-builder.py" >}}

## Inserting Fields using DOM

You can also insert various types of fields using [Aspose.Words Document Object Model (DOM)](/words/python-net/aspose-words-document-object-model/). In this section, we will look at a few examples.

### Inserting Merge Field into a Document using DOM

The `MERGEFIELD` field in Word document can be represented by the [FieldMergeField](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldmergefield/) class. You can use the **FieldMergeField** class to perform the following operations:

- specify the name of merge field
- specify the formatting of merge field
- specify the text that is between the field separator and field end of merge field
- specify the text to be inserted after the merge field if the field is not blank
- specify the text to be inserted before the merge field if the field is not blank

{{% alert color="primary" %}}

For more details, see the [FieldMergeField](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldmergefield/) class API.

{{% /alert %}}

The following code example shows how to add the `MERGE` field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-merge-field-using-dom.py" >}}

### Inserting Mail Merge `ADDRESSBLOCK` field into a Document using DOM

The `ADDRESSBLOCK` field is used to insert a Mail Merge address block in Word document. `ADDRESSBLOCK` field in Word document can be represented by the [FieldAddressBlock](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldaddressblock/) class. You can use the **FieldAddressBlock** class to perform the following operations:

- specify whether to include the name of the country/region in the field
- specify whether to format the address according to the country/region of the recipient as defined by POST*CODE (Universal Postal Union 2006)
- specify the excluded country/region name
- specify the name and address format
- specify the language ID used to format the address

{{% alert color="primary" %}}

For more details, see the [FieldAddressBlock](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldaddressblock/) class API.

{{% /alert %}}

The following code example shows how to add the Mail Merge `ADDRESSBLOCK` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-address-block-field-using-dom.py" >}}

### Inserting `ADVANCE` field into a Document without using DocumentBuilder

The `ADVANCE` field is used to offset subsequent text within a line to the left, right, up or down. The `ADVANCE` field in Word document can be represented by the [FieldAdvance](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldadvance/) class. You can use the **FieldAdvance** class to perform the following operations:

- specify the number of points by which the text that follows the field should be moved vertically from the top edge of the page
- specify the number of points by which the text that follows the field should be moved horizontally from the left edge of the column, frame, or text box
- specify the number of points by which the text that follows the field should be moved left, right, up or down

{{% alert color="primary" %}}

For more details, see the [FieldAdvance](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldadvance/) class API.

{{% /alert %}}

The following code example shows how to add the `ADVANCE` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-advance-field-without-document-builder.py" >}}

### Inserting `ASK` field into a Document without using DocumentBuilder

The `ASK` field is used to prompt the user for text to assign to a Bookmark in Word document. `ASK` field in Word document can be represented by the [FieldAsk](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldask/) class. You can use the **FieldAsk** class to perform the following operations:

- specify the name of the bookmark
- specify default user response (initial value contained in the prompt window)
- specify whether the user response should be received once per a Mail Merge operation
- specify the prompt text (the title of the prompt window)

{{% alert color="primary" %}}

For more details, see the [FieldAsk](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldask/) class API.

{{% /alert %}}

The following code example shows how to add the `ASK` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-ask-field-without-document-builder.py" >}}

### Inserting `AUTHOR` field into a Document without using DocumentBuilder

The `AUTHOR` field is used to specify the name of Document's author from the `Document` properties. The `AUTHOR` field in Word document can be represented by the [FieldAuthor](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldauthor/) class. You can use the **FieldAuthor** class to perform the following operations:

- specify the document author's name

{{% alert color="primary" %}}

For more details, see the [FieldAuthor](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldauthor/) class API.

{{% /alert %}}

The following code example shows how to add the `AUTHOR` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-author-field.py" >}}

### Inserting `INCLUDETEXT` field into a Document without using DocumentBuilder

The `INCLUDETEXT` field inserts the text and graphics contained in the document named in the field code. You can insert the entire document or a portion of the document referred to by a bookmark. This field in Word document is represented by INCLUDETEXT. You can use the [FieldIncludeText](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldincludetext/) class to perform the following operations:

- specify the bookmark's name of the included document
- specify the location of the document

{{% alert color="primary" %}}

For more details, see the [FieldIncludeText](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldincludetext/) class API.

{{% /alert %}}

The following code example shows how to add the `INCLUDETEXT` field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-field-include-text-without-document-builder.py" >}}

### Inserting `TOA` field into a Document without using DocumentBuilder

The `TOA` (*Table of Authorities*) field builds and inserts a table of authorities. The `TOA` field collects entries marked by `TA` (*Table of Authorities Entry*) fields. Microsoft Office Word inserts the `TOA` field when you click *Insert Table of Authorities* in the **Table of Authorities** group on the **References** tab. When you view the `TOA` field in your document, the syntax looks like this:

{ `TOA` [Switches ] }

{{% alert color="primary" %}}

For more details, see the [FieldToa](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldtoa/) class API.

{{% /alert %}}

The following code example shows how to add the `TOA` field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "3432f1bcba1f8c7ab8ea6d7c0badfdf2" "insert-toa-field-without-document-builder.py" >}}

## Related APIs

- [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/)
- [FieldBuilder](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldbuilder/)
- [FieldMergeField](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldmergefield/)
- [FieldAddressBlock](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldaddressblock/)
- [FieldAdvance](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldadvance/)
- [FieldAsk](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldask/)
- [FieldAuthor](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldauthor/)
- [FieldIncludeText](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldincludetext/)
- [FieldToa](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldtoa/) 

## FAQ

1. **Q:** How can I insert a Table of Contents (TOC) field using Aspose.Words for Python?  
   **A:** Use `DocumentBuilder.insert_field("TOC \\o \"1-3\" \\h \\z \\u")` to add a TOC field with default switches. After inserting, call `document.update_fields()` to populate the TOC. You can also use `FieldToc` via the DOM for more granular control.

2. **Q:** Can I insert fields into headers or footers?  
   **A:** Yes. Move a `DocumentBuilder` to the header/footer with `builder.move_to_header_footer(aw.HeaderFooterType.HEADER_PRIMARY)` (or a FOOTER type) and then call `builder.insert_field(...)`. The field will be stored in the header/footer section of the document.

3. **Q:** How do I retrieve all field nodes of a specific type, for example all MERGEFIELD fields?  
   **A:** Iterate `doc.range.fields` to get all fields, then filter by `field.type == aw.fields.FieldType.FIELD_MERGE_FIELD`. This works for any field type supported by Aspose.Words.

4. **Q:** What is the correct way to insert an empty (untyped) field?  
   **A:** Use `builder.insert_field(aw.fields.FieldType.FIELD_NONE, False)` or pass an empty string as the field code. This creates a pair of braces `{}` that can later be edited manually in Word.

5. **Q:** How can I set a specific locale for a field when inserting it?  
   **A:** After creating the field (e.g., via `FieldMergeField` or `DocumentBuilder.insert_field`), set its `locale_id` property, e.g., `field.locale_id = 1033` for English (US). This ensures the field formats numbers, dates, etc., according to the specified locale.