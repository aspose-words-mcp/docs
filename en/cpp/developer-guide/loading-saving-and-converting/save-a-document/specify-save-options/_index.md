---
title: Specify Save Options in C++
second_title: Aspose.Words for C++
articleTitle: Specify Save Options
linktitle: Specify Save Options
description: "More accurately control the save process using C++."
type: docs
weight: 10
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/specify-save-options/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to specify save options for different output formats.

{{% /alert %}}

When saving a document, you can set some advanced properties. Aspose.Words provides you with the [SaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/) class, which allows more precise control of the save process. There are overloads of the **Save** method that accept a **SaveOptions** object – it should be an object of a class derived from the **SaveOptions** class. Each save format has a corresponding class that holds save options for this save format, for example, there is [PdfSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/) for saving to PDF format, [MarkdownSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/) for saving to Markdown format, or [ImageSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/) for saving to an image. This article provides examples of working with some options classes derived from **SaveOptions**.

The following code example shows how to set the save options before saving the document into HTML:

{{< gist "aspose-words-gists" "d143f183bd5dfe07f1f289704e64133c" "export-text-input-form-field-as-text.h" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

The article describes a few properties you can control when saving a document.

## Encrypt a Document With a Password

Use the **Password** property to get or set a password for an encrypted document. Use the **Password** property of the corresponding class to work with the selected document format.

For example, when saving a document to DOC or DOT format, use the [get_Password()](https://reference.aspose.com/words/cpp/aspose.words.saving/docsaveoptions/get_password/) property of the [DocSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/docsaveoptions/) class.

The following code example shows how to set a password to encrypt a document using the RC4 encryption method:

{{< gist "aspose-words-gists" "b4e8a7baa7d3c08127f9a043487de21b" "encrypt-document-with-password.h" >}}

When saving a document to ODT format, use the [get_Password()](https://reference.aspose.com/words/cpp/aspose.words.saving/odtsaveoptions/get_password/) property of the [OdtSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/odtsaveoptions/) class.

The following code example shows how to load and save OpenDocument encrypted with a password:

{{< gist "aspose-words-gists" "b4e8a7baa7d3c08127f9a043487de21b" "load-save-encrypted-document.h" >}}

Not all formats support encryption and the use of **Password** property.

## Show Document Saving Progress Notifications

Aspose.Words provides the ability to use the [get_ProgressCallback()](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/get_progresscallback/) property to get notifications about the progress of document saving.

It is now available when saving to DOCX, FlatOpc, DOCM, DOTM, DOTX, HTML, MHTML, EPUB, XamlFlow, XamlFlowPack, or TXT formats.

## Update the Document Creation Time

Aspose.Words provides an ability to use the [get_CreatedTime()](https://reference.aspose.com/words/cpp/aspose.words.properties/builtindocumentproperties/get_createdtime/) property to get or set the document creation date in UTC. You can also update this value before saving using the [get_UpdateCreatedTimeProperty()](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/get_updatecreatedtimeproperty/) option.

The following code example shows how to update the document creation time:

{{< gist "aspose-words-gists" "d143f183bd5dfe07f1f289704e64133c" "update-last-printed.h" >}}

## Update Last Saved Property

Aspose.Words provides an ability to use the [set_UpdateLastSavedTimeProperty()](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/set_updatelastsavedtimeproperty/) property to get or set a value determining whether the [get_LastSavedTime()](https://reference.aspose.com/words/cpp/aspose.words.properties/builtindocumentproperties/get_lastsavedtime/) property is updated before saving.

The following code example shows how to set this property and save the document:

{{< gist "aspose-words-gists" "d143f183bd5dfe07f1f289704e64133c" "update-last-saved-time.h" >}}

## Control External Resources When Saving a Document into HTML or SVG

To convert HTML or SVG into PDF, simply invoke the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method and specify a file name with the “.PDF” extension. If you want to load images, CSS, etc. from external sources, you can use [IResourceSavingCallback](https://reference.aspose.com/words/cpp/aspose.words.saving/iresourcesavingcallback/).

## Save Black and White Image with One Bit Per Pixel Format

To control image saving options, the **ImageSaveOptions** class is used. For example, you can use the [set_PixelFormat()](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/set_pixelformat/) property to set the pixel format for the generated images. Please note that the pixel format of the output image may differ from the set value because of the work of GDI+.

The following code example shows how to save a black and white image with one bit per pixel format:

{{< gist "aspose-words-gists" "d143f183bd5dfe07f1f289704e64133c" "format1-bpp-indexed.h" >}}

## Related APIs

- [SaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/) — Base class for all save options.
- [PdfSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/) — Save options for PDF output.
- [ImageSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/imagesaveoptions/) — Save options for image output.
- [DocSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/docsaveoptions/) — Save options for DOC/DOT formats.
- [OdtSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/odtsaveoptions/) — Save options for ODT/OTT formats.
- [HtmlSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/) — Save options for HTML/MHTML output.
- [MarkdownSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/) — Save options for Markdown output.
- [XpsSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/xpssaveoptions/) — Save options for XPS output.

## FAQ

1. **Q:** How can I set a password when saving a document to PDF in C++?  
   **A:** Create a `PdfEncryptionDetails` object with the password and assign it to the `get_EncryptionDetails()` property of `PdfSaveOptions`. Then pass the `PdfSaveOptions` instance to `Document::Save`. Example:  

   ```cpp
   auto saveOptions = System::MakeObject<Aspose::Words::Saving::PdfSaveOptions>();
   saveOptions->set_EncryptionDetails(
       System::MakeObject<Aspose::Words::Saving::PdfEncryptionDetails>(u"Secret123", u""));
   doc->Save(u"Encrypted.pdf", saveOptions);
   ```

2. **Q:** Which property lets me receive progress notifications while a document is being saved?  
   **A:** Assign an implementation of `IDocumentSavingCallback` to the `get_ProgressCallback()` property of the appropriate `SaveOptions` class (e.g., `OoxmlSaveOptions`). The callback's `Notify` method is called periodically, and `DocumentSavingArgs::get_EstimatedProgress()` returns the percentage completed. Progress is reported when saving to DOCX, FlatOpc, DOCM, DOTM, DOTX, DOC, DOT, HTML, MHTML, EPUB, XamlFlow, or XamlFlowPack.

3. **Q:** How do I update the document's creation time before saving?  
   **A:** Set the `set_CreatedTime()` property of the document's built‑in properties, then enable `get_UpdateCreatedTimeProperty()` on the `SaveOptions` you use.  

   ```cpp
   doc->get_BuiltInDocumentProperties()->set_CreatedTime(System::DateTime::get_Now());
   auto saveOptions = Aspose::Words::Saving::SaveOptions::CreateSaveOptions(Aspose::Words::SaveFormat::Docx);
   saveOptions->set_UpdateCreatedTimeProperty(true);
   doc->Save(u"output.docx", saveOptions);
   ```

4. **Q:** Can I force the last‑saved timestamp to be refreshed when saving?  
   **A:** Yes. Set `set_UpdateLastSavedTimeProperty()` to `true` on the `SaveOptions` object you pass to `Document::Save`. This makes Aspose.Words write the current UTC time to the `set_LastSavedTime()` property.

5. **Q:** How can I save an image generated from a document as a 1‑bit black‑and‑white PNG?  
   **A:** Use `ImageSaveOptions`, set its `set_PixelFormat()` to `ImagePixelFormat::Format1bppIndexed`, and then save the document page as an image.  

   ```cpp
   auto imgOptions = System::MakeObject<Aspose::Words::Saving::ImageSaveOptions>(Aspose::Words::SaveFormat::Png);
   imgOptions->set_PixelFormat(Aspose::Words::Saving::ImagePixelFormat::Format1bppIndexed);
   doc->Save(u"page.png", imgOptions);
   ```