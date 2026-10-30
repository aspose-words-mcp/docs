---
title: Working with Form Fields in Java
second_title: Aspose.Words for Java
articleTitle: Working with Form Fields
linktitle: Working with Form Fields
description: "Understanding Form Fields feature, working with Form Fields using Java."
type: docs
weight: 380
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-form-fields/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with form fields such as text inputs and checkboxes.

{{% /alert %}}

A document that contains fill-in blanks (fields) is known as a form. For example, you can create a registration form in Microsoft Word that uses drop-down lists from which users can select entries. The `Form` field is a location where a particular type of data, such as a name or address, is stored. Form fields in Microsoft Word include text input, combobox and checkbox.

You can use form fields in your project to "communicate" with your users. For example, you create a document whose content is protected, but only form fields are editable. The users can enter the data in the form fields and submit the document. Your application that uses Aspose.Words can retrieve data from the form fields and process it.

Placing form fields into the document via code is easy. [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) has special methods for inserting them, one for each form field type. Each of the methods accepts a string parameter representing the name of the form field. The name can be an empty string. If however you specify a name for the form field, then a bookmark is automatically created with the same name.

## Insert Form Fields

Form fields are a particular case of Word fields that allows "interaction" with the user. Form fields in Microsoft Word include textbox, combo box and checkbox.

**DocumentBuilder** provides special methods to insert each type of form field into the document: [insertTextInput](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertCheckBox-java.lang.String-boolean-boolean-int), [insertCheckBox](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertCheckBox-java.lang.String-boolean-boolean-int), and [insertComboBox](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertCheckBox-java.lang.String-boolean-int). Note that if you specify a name for the form field, then a bookmark is automatically created with the same name.

The following code example shows how to insert a combobox form field into a document:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "insert-form-fields.java" >}}

### Insert a Text Input

Use the **insertTextInput()** method to insert a textbox into the document.

The following code example shows how to insert a text input form field into a document:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "insert-text-input-form-field.java" >}}

### Insert a Check Box

Call **insertCheckBox()** to insert a checkbox into the document.

The following code example shows how to insert a checkbox form field into a document:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "insert-check-box-form-field.java" >}}

### Insert a Combo Box

Call **InsertComboBox** to insert a combobox into the document.

The following code example shows how to insert a Combobox form field into a document:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "insert-combo-box-form-field.java" >}}

## Obtain Form Fields

A collection of form fields is represented by the [FormFieldCollection](https://reference.aspose.com/words/java/com.aspose.words/formfieldcollection/) class that can be retrieved using the [Range.getFormFields](https://reference.aspose.com/words/java/com.aspose.words/range/#getFormFields) property. This means that you can obtain form fields contained in any document node including the document itself.

{{% alert color="primary" %}}

You can download the sample file of the following examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Form%20fields.docx).

{{% /alert %}}

The following code example shows how to get a collection of form fields:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "form-fields-get-form-fields-collection.java" >}}

You can get a particular form field by its index or name.

The following code example shows how to access form fields:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "form-fields-get-by-name.java" >}}

The **FormField** properties allow you to work with form field name, type, and result.

The following code example shows how to work with form field name, type, and result:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "form-fields-work-with-properties.java" >}}

## Format Form Fields

The [getFont()](https://reference.aspose.com/words/java/com.aspose.words/inline/#getFont) property of [FormField](https://reference.aspose.com/words/java/com.aspose.words/formfield/) allows applying font formatting to the **FormField** as a whole including the field value.

The following code example shows how to apply font formatting to the **FormField**:

{{< gist "aspose-words-gists" "1d9d7d13906d89380213310f7a0dffdc" "form-fields-font-formatting.java" >}}

## Related APIs

- [FormFieldCollection](https://reference.aspose.com/words/java/com.aspose.words/formfieldcollection/)
- [FormField](https://reference.aspose.com/words/java/com.aspose.words/formfield/)
- [DocumentBuilder.insertTextInput](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertTextInput-java.lang.String-int-java.lang.String-java.lang.String-int)
- [DocumentBuilder.insertCheckBox](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertCheckBox-java.lang.String-boolean-boolean-int)
- [DocumentBuilder.insertComboBox](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertComboBox-java.lang.String-java.lang.String---int)
- [Range.getFormFields()](https://reference.aspose.com/words/java/com.aspose.words/range/#getFormFields)
