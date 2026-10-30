---
title: Inserting Fields in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Insert Fields
linktitle: Insert Fields
description: "Insert fields into a document in Node.js in different ways: using `DocumentBuilder` or DOM (Document Object Model)."
type: docs
weight: 20
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/inserting-fields/
timestamp: 2024-09-25-11-08-55
---

There are several different ways to insert fields into a document:

- using [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/)
- using [FieldBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldbuilder/)
- using [Aspose.Words Document Object Model (DOM)](/words/nodejs-net/aspose-words-document-object-model/)

In this article, we will look at each way in more detail and analyze how to insert certain fields using these options.

## Inserting Fields into a Document using DocumentBuilder

In Aspose.Words the [insertField](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertField/) method is used to insert new fields into a document. The first parameter accepts the full field code of the field to be inserted. The second parameter is optional and allows the field result of the field to be set manually. If this is not supplied then the field is updated automatically. You can pass null or empty to this parameter to insert a field with an empty field value. If you are not sure about the particular field code syntax, create the field in Microsoft Word first and switch to see its field code.

{{% alert color="primary" %}}

If your field code has a parameter containing a space then it must be enclosed within speech marks. Otherwise the field in both Microsoft Word and Aspose.Words may not work as expected as the parameter is treated by both as being truncated.

{{% /alert %}}

The following code example shows how to inserts a merge field into a document using **DocumentBuilder**:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-field.js" >}}

The same technique is used to insert fields nested within other fields.

The following code example shows how to insert fields nested within another field using **DocumentBuilder**:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-nested-fields.js" >}}

### Specify Locale at Field Level

A language identifier is a standard international numeric abbreviation for the language in a country or geographical region. With Aspose.Words, you can specify Locale at field level. The [localeId](https://reference.aspose.com/words/nodejs-net/aspose.words/field/localeid/) property gets or sets the locale ID of the field.

The following code example shows how to make use of this option:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "specify-locale-at-field-level.js" >}}

### Insert Untyped/Empty Field

If you want to insert untyped/empty fields ({}) just like Microsoft Word allows, you can use the [insertField](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertField/) method with the [FieldType.FieldNone](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldtype/) parameter. To insert a field into a Word document, you can press “Ctrl + F9” key combination.

The following code example shows how to insert an empty field into the document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-field-none.js" >}}

## Inserting Fields into a Document using FieldBuilder

The alternative way to insert fields in Aspose.Words is the [FieldBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldbuilder/) class. It provides fluent interface to specify field switches and argument values as text, nodes or even nested fields.

The following code example shows how to insert a field into a document using **FieldBuilder**:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-field-using-field-builder.js" >}}

## Inserting Fields using DOM

You can also insert various types of fields using [Aspose.Words Document Object Model (DOM)](/words/nodejs-net/aspose-words-document-object-model/). In this section, we will look at a few examples.

### Inserting Merge Field into a Document using DOM

The `MERGEFIELD` field in Word document can be represented by the [FieldMergeField](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldmergefield/) class. You can use [FieldMergeField](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldmergefield/) class to perform the following operations:

- specify the name of merge field
- specify the formatting of merge field
- specify the text that is between the field separator and field end of merge field
- specify the text to be inserted after the merge field if the field is not blank
- specify the text to be inserted before the merge field if the field is not blank

The following code example shows how to add a `Merge` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-merge-field-using-dom.js" >}}

### Inserting Mail Merge `ADDRESSBLOCK` field into a Document using DOM

The `ADDRESSBLOCK` field is used to insert a Mail Merge address block in Word document. `ADDRESSBLOCK` field in Word document can be represented by the [FieldAddressBlock](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldaddressblock/) class. You can use [FieldAddressBlock](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldaddressblock/) class to perform the following operations:

- specify whether to include the name of the country/region in the field
- specify whether to format the address according to the country/region of the recipient as defined by POST*CODE (Universal Postal Union 2006)
- specify the excluded country/region name
- specify the name and address format
- specify the language ID used to format the address

The following code example shows how to add the Mail Merge `ADDRESSBLOCK` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-address-block-field-using-dom.js" >}}

### Inserting `ADVANCE` field into a Document without using DocumentBuilder

The `ADVANCE` field is used to offset subsequent text within a line to the left, right, up or down. The `ADVANCE` field in Word document can be represented by the [FieldAdvance](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldadvance/) class. You can use the [FieldAdvance](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldadvance/) class to perform the following operations:

- specify the number of points by which the text that follows the field should be moved vertically from the top edge of the page
- specify the number of points by which the text that follows the field should be moved horizontally from the left edge of the column, frame, or text box
- specify the number of points by which the text that follows the field should be moved left, right, up or down

The following code example shows how to add the `ADVANCE` Field using DOM to a paragraph in a document.

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-advance-field-without-document-builder.js" >}}

### Inserting `ASK` field into a Document without using DocumentBuilder

The `ASK` field is used to prompt the user for text to assign to a Bookmark in Word document. `ASK` field in Word document can be represented by the [FieldAsk](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldask/) class. You can use the **FieldAsk** class to perform the following operations:

- specify the name of the bookmark
- specify default user response (initial value contained in the prompt window)
- specify whether the user response should be received once per a Mail Merge operation
- specify the prompt text (the title of the prompt window)

The following code example shows how to add the `ASK` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-ask-field-without-document-builder.js" >}}

### Inserting `AUTHOR` field into a Document without using DocumentBuilder

The `AUTHOR` field is used to specify the name of Document's author from the `Document` properties. The `AUTHOR` field in Word document can be represented by the [FieldAuthor](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldauthor/) class. You can use the **FieldAuthor** class to perform the following operations:

- specify the document author's name

The following code example shows how to add the `AUTHOR` Field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-author-field.js" >}}

### Inserting `INCLUDETEXT` field into a Document without using DocumentBuilder

The `INCLUDETEXT` field inserts the text and graphics contained in the document named in the field code. You can insert the entire document or a portion of the document referred to by a bookmark. This field in Word document is represented by INCLUDETEXT. You can use [FieldIncludeText](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldincludetext/) class to perform the following operations:

- specify the bookmark's name of the included document
- specify the location of the document

The following code example shows how to add the `INCLUDETEXT` field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-field-include-text-without-document-builder.js" >}}

### Inserting `TOA` field into a Document without using DocumentBuilder

The `TOA` (*Table of Authorities*) field builds and inserts a table of authorities. The `TOA` field collects entries marked by `TA` (*Table of Authorities Entry*) fields. Microsoft Office Word inserts the `TOA` field when you click *Insert Table of Authorities* in the **Table of Authorities** group on the **References** tab. When you view the `TOA` field in your document, the syntax looks like this:

{ `TOA` [Switches ] }

You can use the [FieldToa](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldtoa/) class to perform the operations with the `TOA` field.

The following code example shows how to add the `TOA` field using DOM to a paragraph in a document:

{{< gist "aspose-words-gists" "045f68a3af8a7ef327733a8b74034ec5" "insert-toa-field-without-document-builder.js" >}}

------ 

## FAQ

1. **Q:** How do I insert a field using `DocumentBuilder` in Node.js?  
   **A:** Create a `DocumentBuilder` instance for your document and call `insertField(fieldCode)`. The `fieldCode` is the full Word field code (e.g., `"MERGEFIELD  CustomerName"`); the field result is updated immediately. Use `insertField(fieldCode, fieldValue)` to insert the field with your own result text without updating it.

2. **Q:** How can I insert nested fields or fields whose parameters contain spaces?  
   **A:** Enclose parameters that contain spaces in double quotes inside the field code. For nested fields, use `FieldBuilder`: pass the builder of the inner field to `addArgument` of the outer one, then call `buildAndInsert`. Braces typed in an `insertField` string are inserted as plain text, not as a nested field.

3. **Q:** How do I insert an empty (untyped) field such as `{}`?  
   **A:** Use `insertField` with `FieldType.FieldNone`. Example:  
   ```javascript
   let builder = new aw.DocumentBuilder(doc);
   builder.insertField(aw.Fields.FieldType.FieldNone, false);
   ```  
   This creates a placeholder field that can later be edited manually in Word.

4. **Q:** What are the differences between `DocumentBuilder`, `FieldBuilder`, and the DOM for inserting fields?  
   **A:** `DocumentBuilder` inserts fields directly at the current cursor position and is simple for one‑off insertions. `FieldBuilder` provides a fluent API to construct complex field codes, set switches, and nest fields before insertion. The DOM approach creates field objects (e.g., `FieldMergeField`) that can be added to any node in the document tree, giving full control over placement and allowing manipulation of field properties after creation.

5. **Q:** How can I set the locale for a field to control its formatting (e.g., dates, numbers)?  
   **A:** After inserting the field, set its `localeId` property to the desired LCID. Example:  
   ```javascript
   let builder = new aw.DocumentBuilder(doc);
   let field = builder.insertField('MERGEFIELD  OrderDate \\@ "MM/dd/yyyy"', null);
   field.localeId = 1033; // English - United States
   ```  
   The specified locale determines how the field formats dates, numbers, and currency.