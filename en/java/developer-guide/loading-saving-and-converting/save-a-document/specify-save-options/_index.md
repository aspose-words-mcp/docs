---
title: Specify Save Options in Java
second_title: Aspose.Words for Java
articleTitle: Specify Save Options
linktitle: Specify Save Options
description: "Set advanced properties when saving a document using Java to provide more precise control over the process."
aliases:
    - /java/working-with-saveoptions/
    - /java/working-with-ooxml/
type: docs
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/specify-save-options/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to specify save options for different output formats.

{{% /alert %}}

When saving a document, you can set some advanced properties. Aspose.Words provides you with the [SaveOptions](https://reference.aspose.com/words/java/com.aspose.words/saveoptions/) class, which allows more precise control of the save process. There are overloads of the **Save** method that accept a **SaveOptions** object – it should be an object of a class derived from the **SaveOptions** class. Each save format has a corresponding class that holds save options for this save format, for example, there is [PdfSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/pdfsaveoptions/) for saving to PDF format, [MarkdownSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/markdownsaveoptions/) for saving to Markdown format, or [ImageSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/) for saving to an image. This article provides examples of working with some options classes derived from **SaveOptions**.

The following code example shows how to set the save options before saving the document into HTML:

{{< gist "aspose-words-gists" "a6f7799aa265589fb56915bb1e401b05" "export-text-input-form-field-as-text.java" >}}


{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

The article describes a few properties you can control when saving a document.

## Encrypt a Document With a Password

Use the **Password** property to get or set a password for an encrypted document. Use the **Password** property of the corresponding class to work with the selected document format.

For example, when saving a document to DOC or DOT format, use the [getPassword()](https://reference.aspose.com/words/java/com.aspose.words/docsaveoptions/#getPassword) property of the [DocSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/docsaveoptions/) class.

The following code example shows how to set a password to encrypt a document using the RC4 encryption method:

{{< gist "aspose-words-gists" "821ff3a1df0c75b2af641299b393fb60" "encrypt-document-with-password.java" >}}

When saving a document to ODT format, use the [getPassword()](https://reference.aspose.com/words/java/com.aspose.words/odtsaveoptions/#getPassword) property of the [OdtSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/odtsaveoptions/) class.

The following code example shows how to load and save OpenDocument encrypted with a password:

{{< gist "aspose-words-gists" "821ff3a1df0c75b2af641299b393fb60" "load-save-encrypted-document.java" >}}

Not all formats support encryption and the use of **Password** property.

## Show Document Saving Progress Notifications

Aspose.Words provides the ability to use the [getProgressCallback()](https://reference.aspose.com/words/java/com.aspose.words/saveoptions/#getProgressCallback) property to get notifications about the progress of document saving.

It is now available when saving to DOCX, FlatOpc, DOCM, DOTM, DOTX, HTML, MHTML, EPUB, XamlFlow, XamlFlowPack, or TXT formats.

## Update the Document Creation Time

Aspose.Words provides an ability to use the [getCreatedTime()](https://reference.aspose.com/words/java/com.aspose.words/builtindocumentproperties/#getCreatedTime) property to get or set the document creation date in UTC. You can also update this value before saving using the [getUpdateCreatedTimeProperty()](https://reference.aspose.com/words/java/com.aspose.words/saveoptions/#getUpdateCreatedTimeProperty) option.

The following code example shows how to update the document creation time:

{{< gist "aspose-words-gists" "a6f7799aa265589fb56915bb1e401b05" "update-last-printed.java" >}}

## Update Last Saved Property

Aspose.Words provides an ability to use the [getUpdateLastSavedTimeProperty()](https://reference.aspose.com/words/java/com.aspose.words/saveoptions/#getUpdateLastSavedTimeProperty) property to get or set a value determining whether the [getLastSavedTime()](https://reference.aspose.com/words/java/com.aspose.words/builtindocumentproperties/#getLastSavedTime) property is updated before saving.

The following code example shows how to set this property and save the document:

{{< gist "aspose-words-gists" "a6f7799aa265589fb56915bb1e401b05" "update-last-saved-time.java" >}}

## Control External Resources When Saving a Document into HTML or SVG

To convert HTML or SVG into PDF, simply invoke the [save()](https://reference.aspose.com/words/java/com.aspose.words/document/#save-java.lang.String) method and specify a file name with the “.PDF” extension. If you want to load images, CSS, etc. from external sources, you can use [IResourceSavingCallback](https://reference.aspose.com/words/java/com.aspose.words/iresourcesavingcallback/).

## Save Black and White Image with One Bit Per Pixel Format

To control image saving options, the **ImageSaveOptions** class is used. For example, you can use the [getPixelFormat()](https://reference.aspose.com/words/java/com.aspose.words/imagesaveoptions/#getPixelFormat) property to set the pixel format for the generated images. Please note that the pixel format of the output image may differ from the set value because of the work of GDI+.

The following code example shows how to save a black and white image with one bit per pixel format:

{{< gist "aspose-words-gists" "a6f7799aa265589fb56915bb1e401b05" "format1-bpp-indexed.java" >}}

------ 

## FAQ

1. **Q:** How can I encrypt a saved document with a password in Java?  
   **A:** Use the save options class of the target format: call `setPassword(String)` on `DocSaveOptions`, `OoxmlSaveOptions`, or `OdtSaveOptions`; for PDF, call `PdfSaveOptions.setEncryptionDetails(new PdfEncryptionDetails(userPassword, ownerPassword))`. Then pass the options object to `Document.save(String, SaveOptions)`. The encryption method (RC4, AES) is chosen automatically based on the format.

2. **Q:** Is there a way to receive progress updates while a large document is being saved?  
   **A:** Yes, for some formats. Implement the `IDocumentSavingCallback` interface and pass an instance to `setProgressCallback` of the `SaveOptions`. Aspose.Words calls its `notify(DocumentSavingArgs args)` method during saving, and `args.getEstimatedProgress()` returns the percentage completed. Progress is reported when saving to DOCX, FLAT_OPC, DOCM, DOTM, DOTX, DOC, DOT, HTML, MHTML, EPUB, XAML_FLOW, and XAML_FLOW_PACK, but not to PDF.

3. **Q:** How do I change the document's creation time before saving?  
   **A:** Set the `getCreatedTime()` property of the `BuiltInDocumentProperties` object (`document.getBuiltInDocumentProperties().setCreatedTime(Date)`). To make the saved file reflect this value, enable `setUpdateCreatedTimeProperty(true)` on the `SaveOptions`.

4. **Q:** Can I prevent the `getLastSavedTime()` property from being updated when I save a document?  
   **A:** Yes. Set `setUpdateLastSavedTimeProperty(false)` on the `SaveOptions` you pass to `Document.save`. This tells Aspose.Words to keep the existing `getLastSavedTime()` value.

5. **Q:** How can I save images generated from a document as black‑and‑white (1‑bit) PNGs?  
   **A:** Use `ImageSaveOptions` and call `setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED)`. Then call `document.save("output.png", imageSaveOptions)`. The resulting PNG will be a 1‑bit per pixel black‑and‑white image.