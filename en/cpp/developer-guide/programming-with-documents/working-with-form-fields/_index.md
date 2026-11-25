---
title: Working with Form Fields in C++
second_title: Aspose.Words for C++
articleTitle: Working with Form Fields
linktitle: Working with Form Fields
description: "Understanding Form Fields feature, working with Form Fields using C++."
type: docs
weight: 380
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-form-fields/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with form fields such as text inputs and checkboxes.

{{% /alert %}}

A document that contains fill-in blanks (fields) is known as a form. For example, you can create a registration form in Microsoft Word that uses drop-down lists from which users can select entries. The `Form` field is a location where a particular type of data, such as a name or address, is stored. Form fields in Microsoft Word include text input, combobox and checkbox.

You can use form fields in your project to "communicate" with your users. For example, you create a document whose content is protected, but only form fields are editable. The users can enter the data in the form fields and submit the document. Your application that uses Aspose.Words can retrieve data from the form fields and process it.

Placing form fields into the document via code is easy. [DocumentBuilder](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/) has special methods for inserting them, one for each form field type. Each of the methods accepts a string parameter representing the name of the form field. The name can be an empty string. If however you specify a name for the form field, then a bookmark is automatically created with the same name.

## Insert Form Fields

Form fields are a particular case of Word fields that allows "interaction" with the user. Form fields in Microsoft Word include textbox, combo box and checkbox.

**DocumentBuilder** provides special methods to insert each type of form field into the document: [InsertTextInput](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/inserttextinput/), [InsertCheckBox](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertcheckbox/), and [InsertComboBox](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertcombobox/). Note that if you specify a name for the form field, then a bookmark is automatically created with the same name.

The following code example shows how to insert a combobox form field into a document:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "insert-form-fields.h" >}}

### Insert a Text Input

Use the **InsertTextInput** method to insert a textbox into the document.

The following code example shows how to insert a text input form field into a document:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "insert-text-input-form-field.h" >}}

### Insert a Check Box

Call **InsertCheckBox** to insert a checkbox into the document.

The following code example shows how to insert a checkbox form field into a document:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "insert-check-box-form-field.h" >}}

### Insert a Combo Box

Call **InsertComboBox** to insert a combobox into the document.

The following code example shows how to insert a Combobox form field into a document:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "insert-combo-box-form-field.h" >}}

## Obtain Form Fields

A collection of form fields is represented by the [FormFieldCollection](https://reference.aspose.com/words/cpp/aspose.words.fields/formfieldcollection/) class that can be retrieved using the [get_FormFields()](https://reference.aspose.com/words/cpp/aspose.words/range/get_formfields/) property. This means that you can obtain form fields contained in any document node including the document itself.

{{% alert color="primary" %}}

You can download the sample file of the following examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Form%20fields.docx).

{{% /alert %}}

The following code example shows how to get a collection of form fields:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "form-fields-get-form-fields-collection.h" >}}

You can get a particular form field by its index or name.

The following code example shows how to access form fields:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "form-fields-get-by-name.h" >}}

The **FormField** properties allow you to work with form field name, type, and result.

The following code example shows how to work with form field name, type, and result:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "form-fields-work-with-properties.h" >}}

## Format Form Fields

The [get_Font()](https://reference.aspose.com/words/cpp/aspose.words/inline/get_font/) property of [FormField](https://reference.aspose.com/words/cpp/aspose.words.fields/formfield/) allows applying font formatting to the **FormField** as a whole including the field value.

The following code example shows how to apply font formatting to the **FormField**:

{{< gist "aspose-words-gists" "b0f2e2ef2b8f321b68cd22b92f8f549b" "form-fields-font-formatting.h" >}}

## Related APIs

- [FormFieldCollection](https://reference.aspose.com/words/cpp/aspose.words.fields/formfieldcollection/)
- [FormField](https://reference.aspose.com/words/cpp/aspose.words.fields/formfield/)
- [DocumentBuilder::InsertTextInput](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/inserttextinput/)
- [DocumentBuilder::InsertCheckBox](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertcheckbox/)
- [DocumentBuilder::InsertComboBox](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertcombobox/)
- [Range::get_FormFields()](https://reference.aspose.com/words/cpp/aspose.words/range/get_formfields/)
