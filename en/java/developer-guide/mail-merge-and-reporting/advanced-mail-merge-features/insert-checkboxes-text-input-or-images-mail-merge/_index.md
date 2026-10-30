---
title: Insert Checkboxes, Text Input or Images during Mail Merge
second_title: Aspose.Words for Java
articleTitle: Insert Checkboxes, Text Input, or Images
linktitle: Insert Checkboxes, Text Input, or Images
description: "Insert checkboxes or text input fields during Mail Merge using Java. Also insert images from a Database during Mail Merge in Java."
type: docs
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/insert-checkboxes-text-input-or-images-mail-merge/
aliases: [/java/insert-checkboxes-html-or-images-during-mail-merge/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to insert checkboxes, text inputs, or images during mail merge.

{{% /alert %}}

The merge engine takes a document as input, looks for `MERGEFIELD` fields in it, and replaces them with the data obtained from the data source. Typically, plain text and HTML are inserted, but Aspose.Words users can also generate a document that handles more unusual scenarios for Mail Merge fields.

Powerful Aspose.Words functionality allows you to extend the Mail Merge process:

- insert checkboxes and text input form fields into the document during a mail merge
- insert images from any custom storage (files, BLOB fields, etc.)

## Insert Checkboxes and Text Input during Mail Merge

Sometimes it is necessary to perform a Mail Merge operation so that not text is substituted in the merge field, but a checkbox or text input field. Even though this is not the most common scenario, it is very handy for some tasks.

The following screenshot of a Word document shows a template with merge fields:

<img src="insert-checkboxes-html-or-images-during-mail-merge-1.jpeg" alt="insert-checkboxes-or-images-mail-merge-aspose-words-java" style="width:600px"/>

This screenshot of the Word document below shows the already generated document:

<img src="insert-checkboxes-html-or-images-during-mail-merge-2.png" alt="insert-checkboxes-html-or-images-mail-merge-aspose-words-java" style="width:600px"/>

{{% alert color="primary" %}}

Note that some fields were replaced with plain text, some fields were replaced with checkbox form fields, and the `Subject` field was replaced with a text input field.

{{% /alert %}}

The following code example shows how to insert checkboxes and input text fields into a document during a mail merge:

{{< gist "aspose-words-gists" "5088a3aa54a6cb4f6dc8ee8a4e19da52" "mail-merge-form-fields.java" >}}

{{< gist "aspose-words-gists" "1aaa54a374c2ea8cda06bae3d084108e" "handle-merge-field.java" >}}

## Insert Images during Mail Merge

When performing a Mail Merge operation, you can insert images from the database into the document using special image Mail Merge fields. The image Mail Merge field is a merge field named Image:MyFieldName.

### Insert Images from a Database

During a mail merge, when an image Mail Merge field is encountered in a document, the [getFieldMergingCallback()](https://reference.aspose.com/words/java/com.aspose.words/mailmerge/#getFieldMergingCallback) event is fired. You can respond to this event to return a filename, stream, or image object to the Mail Merge engine so it can be inserted into the document.

The following code example shows how to insert images stored in a database BLOB field into a report:

{{< gist "aspose-words-gists" "1aaa54a374c2ea8cda06bae3d084108e" "mail-merge-image-from-blob.java" >}}

{{< gist "aspose-words-gists" "1aaa54a374c2ea8cda06bae3d084108e" "handle-merge-image-field-from-blob.java" >}}

### Set Image Properties during Mail Merge

While merging an image merge field, you may sometimes need to control various image properties, such as [WrapType](https://reference.aspose.com/words/java/com.aspose.words/wraptype/).

Currently, using [ImageFieldMergingArgs](https://reference.aspose.com/words/java/com.aspose.words/imagefieldmergingargs/) you can only set image width or height properties, respectively. To overcome this issue, Aspose.Words provides the [getShape()](https://reference.aspose.com/words/java/com.aspose.words/imagefieldmergingargs/#getShape) property, which facilitates to get full control over the inserted image or any other shape.

The following code example shows how to set various image properties:

{{< gist "aspose-words-gists" "1aaa54a374c2ea8cda06bae3d084108e" "mail-merge-image-field.java" >}}

{{< gist "aspose-words-gists" "1aaa54a374c2ea8cda06bae3d084108e" "image-field-merging-handler.java" >}}

{{< gist "aspose-words-gists" "1aaa54a374c2ea8cda06bae3d084108e" "data-source-root.java" >}}

------  

## FAQ

1. **Q:** How can I insert a checkbox form field during a mail merge?  
   **A:** Implement `IFieldMergingCallback` and, in the `fieldMerging` method, detect the target merge field name. Move a `DocumentBuilder` to the field with `builder.moveToMergeField(args.getFieldName())` and insert the check box with `builder.insertCheckBox(...)`. The check box replaces the merge field.

2. **Q:** How do I add a text input form field using mail merge?  
   **A:** In the same `fieldMerging` callback, move the `DocumentBuilder` to the merge field with `builder.moveToMergeField(args.getFieldName())` and call `builder.insertTextInput(...)` with the form field name, a `TextFormFieldType` value, the default text, and the maximum length. The text input form field replaces the merge field.

3. **Q:** How can I insert images that are stored in a database BLOB during mail merge?  
   **A:** Use an image merge field (`Image:MyField`) in the template. In the `imageFieldMerging` callback, retrieve the BLOB as a `byte[]` or `InputStream` and pass it to `ImageFieldMergingArgs.setImageStream` (wrap a `byte[]` in a `ByteArrayInputStream`) to supply the image data to the engine.

4. **Q:** How can I control the size, rotation, or wrap type of an inserted image?  
   **A:** Inside the `imageFieldMerging` callback, create a `Shape` with the image, set properties such as `setWidth`, `setHeight`, `setWrapType`, and `setRotation`, and pass it to `ImageFieldMergingArgs.setShape`. The engine then inserts this shape instead of the image data. To set only the size, use `setImageWidth` and `setImageHeight`.

5. **Q:** Do I need a licensed version of Aspose.Words to use form fields or image insertion in mail merge?  
   **A:** Not to use the feature. Without a license, Aspose.Words for Java works in evaluation mode with full functionality, but it adds an evaluation watermark and limits the document size to a few hundred paragraphs. To remove these limitations, apply a license: `License license = new License(); license.setLicense("Aspose.Words.Java.lic");`.