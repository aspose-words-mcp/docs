---
title: Working with Form Fields in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Form Fields
linktitle: Working with Form Fields
description: "Insert, obtain, or format a form field in a document using Python."
type: docs
weight: 380
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-form-fields/
aliases: [/python/working-with-form-fields/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to insert, retrieve, and format form fields in a Word document using Aspose.Words for Python via .NET. It includes examples for inserting text input, check box, and combo box fields, accessing them via the FormFieldCollection, and applying font formatting.

{{% /alert %}}

A document that contains fill-in blanks (fields) is known as a form. For example, you can create a registration form in Microsoft Word that uses drop-down lists from which users can select entries. The `Form` field is a location where a particular type of data, such as a name or address, is stored. Form fields in Microsoft Word include text input, combobox and checkbox.

You can use form fields in your project to "communicate" with your users. For example, you create a document whose content is protected, but only form fields are editable. The users can enter the data in the form fields and submit the document. Your application that uses Aspose.Words can retrieve data from the form fields and process it.

Placing form fields into the document via code is easy. [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) has special methods for inserting them, one for each form field type. Each of the methods accepts a string parameter representing the name of the form field. The name can be an empty string. If however you specify a name for the form field, then a bookmark is automatically created with the same name.

## Insert Form Fields

Form fields are a particular case of Word fields that allows "interaction" with the user. Form fields in Microsoft Word include textbox, combo box and checkbox.

**DocumentBuilder** provides special methods to insert each type of form field into the document: [insert_text_input](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_text_input/) , [insert_check_box](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_check_box/), and [insert_combo_box](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_combo_box/). Note that if you specify a name for the form field, then a bookmark is automatically created with the same name.

The following code example shows how to insert a combobox form field into a document:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "insert-form-fields.py" >}}

### Insert a Text Input

Use the **insert_text_input** method to insert a textbox into the document.

The following code example shows how to insert a text input form field into a document:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "insert-text-input-form-field.py" >}}

### Insert a Check Box

Call **insert_check_box** to insert a checkbox into the document.

The following code example shows how to insert a checkbox form field into a document:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "insert-check-box-form-field.py" >}}

### Insert a Combo Box

Call **insert_combo_box** to insert a combobox into the document.

The following code example shows how to insert a Combobox form field into a document:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "insert-combo-box-form-field.py" >}}

## Obtain Form Fields

A collection of form fields is represented by the [FormFieldCollection](https://reference.aspose.com/words/python-net/aspose.words.fields/formfieldcollection/) class that can be retrieved using the [form_fields](https://reference.aspose.com/words/python-net/aspose.words/range/form_fields/) property. This means that you can obtain form fields contained in any document node including the document itself.

{{% alert color="primary" %}}

You can download the sample file of the following examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Form%20fields.docx).

{{% /alert %}}

The following code example shows how to get a collection of form fields:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "form-fields-get-form-fields-collection.py" >}}

You can get a particular form field by its index or name.

The following code example shows how to access form fields:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "form-fields-get-by-name.py" >}}

The **FormField** properties allow you to work with form field name, type, and result.

The following code example shows how to work with form field name, type, and result:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "form-fields-work-with-properties.py" >}}

## Format Form Fields

The [font](https://reference.aspose.com/words/python-net/aspose.words/inline/font/) property of [FormField](https://reference.aspose.com/words/python-net/aspose.words.fields/formfield/) allows applying font formatting to the **FormField** as a whole including the field value.

The following code example shows how to apply font formatting to the **FormField**:

{{< gist "aspose-words-gists" "8711210cb6f2a5d46bbbb10dd9982c58" "form-fields-font-formatting.py" >}}

## Related APIs

- [FormFieldCollection](https://reference.aspose.com/words/python-net/aspose.words.fields/formfieldcollection/)
- [FormField](https://reference.aspose.com/words/python-net/aspose.words.fields/formfield/)
- [DocumentBuilder.insert_text_input](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_text_input/)
- [DocumentBuilder.insert_check_box](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_check_box/)
- [DocumentBuilder.insert_combo_box](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_combo_box/)
- [Range.form_fields](https://reference.aspose.com/words/python-net/aspose.words/range/form_fields/)