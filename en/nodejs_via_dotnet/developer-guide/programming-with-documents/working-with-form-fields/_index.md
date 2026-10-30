---
title: Working with Form Fields in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Form Fields
linktitle: Working with Form Fields
description: "Insert, obtain, or format a form field in a document using Node.js."
type: docs
weight: 380
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-form-fields/
timestamp: 2025-07-09-10-05-05
---

A document that contains fill-in blanks (fields) is known as a form. For example, you can create a registration form in Microsoft Word that uses drop-down lists from which users can select entries. The `Form` field is a location where a particular type of data, such as a name or address, is stored. Form fields in Microsoft Word include text input, combobox and checkbox.

You can use form fields in your project to "communicate" with your users. For example, you create a document whose content is protected, but only form fields are editable. The users can enter the data in the form fields and submit the document. Your application that uses Aspose.Words can retrieve data from the form fields and process it.

Placing form fields into the document via code is easy. [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) has special methods for inserting them, one for each form field type. Each of the methods accepts a string parameter representing the name of the form field. The name can be an empty string. If however you specify a name for the form field, then a bookmark is automatically created with the same name.

## Inserting Form Fields

Form fields are a particular case of Word fields that allows "interaction" with the user. Form fields in Microsoft Word include textbox, combo box and checkbox.

[DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) provides special methods to insert each type of form field into the document: [insertTextInput](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/inserttextinput/), [insertCheckBox](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertcheckbox/), and [insertComboBox](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertcombobox/). Note that if you specify a name for the form field, then a bookmark is automatically created with the same name.

The following code example shows how to insert a combobox form field into a document:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "insert-form-fields.js" >}}

### Insert a Text Input

Use the [insertTextInput](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/inserttextinput/) method to insert a textbox into the document.

The following code example shows how to insert a text input form field into a document:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "insert-text-input-form-field.js" >}}

### Insert a Check Box

Call [insertCheckBox](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertcheckbox/) to insert a checkbox into the document.

The following code example shows how to insert a checkbox form field into a document:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "insert-check-box-form-field.js" >}}

### Insert a Combo Box

Call [insertComboBox](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertcombobox/) to insert a Combobox into the document.

The following code example shows how to insert a Combobox form field into a document:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "insert-combo-box-form-field.js" >}}

## Obtain Form Fields

A collection of form fields is represented by the [FormFieldCollection](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/formfieldcollection/) class that can be retrieved using the [formFields](https://reference.aspose.com/words/nodejs-net/aspose.words/range/formfields/) property. This means that you can obtain form fields contained in any document node including the document itself.

{{% alert color="primary" %}}

You can download the sample file of the following examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Form%20fields.docx).

{{% /alert %}}

The following code example shows how to get a collection of form fields:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "form-fields-get-form-fields-collection.js" >}}

You can get a particular form field by its index or name.

The following code example shows how to access form fields:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "form-fields-get-by-name.js" >}}

The [FormField](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/formfield/) properties allow you to work with form field name, type, and result.

The following code example shows how to work with form field name, type, and result:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "form-fields-work-with-properties.js" >}}

## Format Form Fields

The [font](https://reference.aspose.com/words/nodejs-net/aspose.words/inline/font/) property of [FormField](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/formfield/) allows applying font formatting to the [FormField](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/formfield/) as a whole including the field value.

The following code example shows how to apply font formatting to the **FormField**:

{{< gist "aspose-words-gists" "a317eda2c6381dd30c7eb70510e51d52" "form-fields-font-formatting.js" >}}
