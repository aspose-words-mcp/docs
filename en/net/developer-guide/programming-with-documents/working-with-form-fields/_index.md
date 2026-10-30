---
title: Working with Form Fields in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Form Fields
linktitle: Working with Form Fields
description: "Understanding Form Fields feature, working with Form Fields using C#."
type: docs
weight: 380
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-form-fields/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with form fields such as text inputs and checkboxes.

{{% /alert %}}

A document that contains fill-in blanks (fields) is known as a form. For example, you can create a registration form in Microsoft Word that uses drop-down lists from which users can select entries. The `Form` field is a location where a particular type of data, such as a name or address, is stored. Form fields in Microsoft Word include text input, combobox and checkbox.

You can use form fields in your project to "communicate" with your users. For example, you create a document whose content is protected, but only form fields are editable. The users can enter the data in the form fields and submit the document. Your application that uses Aspose.Words can retrieve data from the form fields and process it.

Placing form fields into the document via code is easy. [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/) has special methods for inserting them, one for each form field type. Each of the methods accepts a string parameter representing the name of the form field. The name can be an empty string. If however you specify a name for the form field, then a bookmark is automatically created with the same name.

## Insert Form Fields

Form fields are a particular case of Word fields that allows "interaction" with the user. Form fields in Microsoft Word include textbox, combo box and checkbox.

**DocumentBuilder** provides special methods to insert each type of form field into the document: [InsertTextInput](https://reference.aspose.com/words/net/aspose.words/documentbuilder/inserttextinput/), [InsertCheckBox](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertcheckbox/), and [InsertComboBox](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertcombobox/). Note that if you specify a name for the form field, then a bookmark is automatically created with the same name.

The following code example shows how to insert a combobox form field into a document:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "insert-form-fields.cs" >}}

### Insert a Text Input

Use the **InsertTextInput** method to insert a textbox into the document.

The following code example shows how to insert a text input form field into a document:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "insert-text-input-form-field.cs" >}}

### Insert a Check Box

Call **InsertCheckBox** to insert a checkbox into the document.

The following code example shows how to insert a checkbox form field into a document:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "insert-check-box-form-field.cs" >}}

### Insert a Combo Box

Call **InsertComboBox** to insert a combobox into the document.

The following code example shows how to insert a Combobox form field into a document:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "insert-combo-box-form-field.cs" >}}

## Obtain Form Fields

A collection of form fields is represented by the [FormFieldCollection](https://reference.aspose.com/words/net/aspose.words.fields/formfieldcollection/) class that can be retrieved using the [FormFields](https://reference.aspose.com/words/net/aspose.words/range/formfields/) property. This means that you can obtain form fields contained in any document node including the document itself.

{{% alert color="primary" %}}

You can download the sample file of the following examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Form%20fields.docx).

{{% /alert %}}

The following code example shows how to get a collection of form fields:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "form-fields-get-form-fields-collection.cs" >}}

You can get a particular form field by its index or name.

The following code example shows how to access form fields:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "form-fields-get-by-name.cs" >}}

The **FormField** properties allow you to work with form field name, type, and result.

The following code example shows how to work with form field name, type, and result:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "form-fields-work-with-properties.cs" >}}

## Format Form Fields

The [Font](https://reference.aspose.com/words/net/aspose.words/inline/font/) property of [FormField](https://reference.aspose.com/words/net/aspose.words.fields/formfield/) allows applying font formatting to the **FormField** as a whole including the field value.

The following code example shows how to apply font formatting to the **FormField**:

{{< gist "aspose-words-gists" "b09907fef4643433271e4e0e912921b0" "form-fields-font-formatting.cs" >}}

## Related APIs

- [FormFieldCollection](https://reference.aspose.com/words/net/aspose.words.fields/formfieldcollection/)
- [FormField](https://reference.aspose.com/words/net/aspose.words.fields/formfield/)
- [DocumentBuilder.InsertTextInput](https://reference.aspose.com/words/net/aspose.words/documentbuilder/inserttextinput/)
- [DocumentBuilder.InsertCheckBox](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertcheckbox/)
- [DocumentBuilder.InsertComboBox](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertcombobox/)
- [Range.FormFields](https://reference.aspose.com/words/net/aspose.words/range/formfields/)

------

## FAQ

1. **Q:** How can I set or change the value of a form field programmatically?  
   **A:** Use the `Result` property of the `FormField` object. After obtaining the field (by name or index), assign the desired string to `FormField.Result`, and then save the document.

2. **Q:** How do I retrieve the current value entered in a form field?  
   **A:** Access the same `Result` property. It returns the text that the user has entered or the default value defined when the field was created.

3. **Q:** I need the document to be editable only through its form fields. How can I protect it accordingly?  
   **A:** Call `Document.Protect(ProtectionType.AllowOnlyFormFields, "password")`. This protects the whole document while still allowing users to fill in the form fields.

4. **Q:** Can I apply font styling (e.g., bold, color) to the text inside a form field?  
   **A:** Yes. The `FormField.Font` property gives access to a `Font` object. Set properties such as `Bold`, `Color`, or `Size` on this object to format the field's content.

5. **Q:** How can I check whether a specific form field exists before accessing it?  
   **A:** Use the `FormFields` collection: `FormField field = document.Range.FormFields["MyField"];` and verify that `field` is not `null` before using it. This prevents exceptions when the field name is misspelled or missing.