---
title: Specify Save Options in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Specify Save Options
linktitle: Specify Save Options
description: "More accurately control the save process using Python."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/specify-save-options/
aliases: [/python/specify-save-options/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words SaveOptions classes in Python via .NET to control various aspects of document saving, such as format‑specific options, encryption, timestamps, and image pixel format, with code examples.

{{% /alert %}}

When saving a document, you can set some advanced properties. Aspose.Words provides you with the [SaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/) class, which allows more precise control of the save process. There are overloads of the **Save** method that accept a **SaveOptions** object – it should be an object of a class derived from the **SaveOptions** class. Each save format has a corresponding class that holds save options for this save format, for example, there is [PdfSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/) for saving to PDF format, [SaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/) for saving to Markdown format, or [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/) for saving to an image. This article provides examples of working with some options classes derived from **SaveOptions**.

The following code example shows how to set the save options before saving the document into HTML:

{{< gist "aspose-words-gists" "b05f6fe5e272263ce37254e9e36a5ae0" "export-text-input-form-field-as-text.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

The article describes a few properties you can control when saving a document.

## Encrypt a Document With a Password

Use the **password** property to get or set a password for an encrypted document. Use the **password** property of the corresponding class to work with the selected document format.

For example, when saving a document to DOC or DOT format, use the [password](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/password/) property of the [DocSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/) class.

The following code example shows how to set a password to encrypt a document using the RC4 encryption method:

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "encrypt-document-with-password.py" >}}

When saving a document to Odt format, use the [password](https://reference.aspose.com/words/python-net/aspose.words.saving/ooxmlsaveoptions/password/) property of the [OoxmlSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/ooxmlsaveoptions/) class.

The following code example shows how to load and save OpenDocument encrypted with a password:

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "load-save-encrypted-document.py" >}}

Not all formats support encryption and the use of **password** property.

## Show Document Saving Progress Notifications

Aspose.Words provides the ability to use the [progress_callback](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/progress_callback/) property to get notifications about the progress of document saving.

It is now available when saving to DOCX, FlatOpc, DOCM, DOTM, DOTX, HTML, MHTML, EPUB, XamlFlow, XamlFlowPack, or TXT formats.

## Update the Document Creation Time

Aspose.Words provides an ability to use the [created_time](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/created_time/) property to get or set the document creation date in UTC. You can also update this value before saving using the [update_created_time_property](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/update_created_time_property/) option.

The following code example shows how to update the document creation time:

{{< gist "aspose-words-gists" "b05f6fe5e272263ce37254e9e36a5ae0" "update-last-printed.py" >}}

## Update Last Saved Property

Aspose.Words provides an ability to use the [update_last_saved_time_property](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/update_last_saved_time_property/) property to get or set a value determining whether the [last_saved_time](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/last_saved_time/) property is updated before saving.

The following code example shows how to set this property and save the document:

{{< gist "aspose-words-gists" "b05f6fe5e272263ce37254e9e36a5ae0" "update-last-saved-time.py" >}}

## Control External Resources When Saving a Document into HTML or SVG

To convert HTML or SVG into PDF, simply invoke the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method and specify a file name with the “.PDF” extension. If you want to load images, CSS, etc. from external sources, you can use [IResourceSavingCallback](https://reference.aspose.com/words/python-net/aspose.words.saving/iresourcesavingcallback/).

## Save Black and White Image with One Bit Per Pixel Format

To control image saving options, the [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/) class is used. For example, you can use the [pixel_format](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/pixel_format/) property to set the pixel format for the generated images. Please note that the pixel format of the output image may differ from the set value because of the work of skia.

The following code example shows how to save a black and white image with one bit per pixel format:

{{< gist "aspose-words-gists" "b05f6fe5e272263ce37254e9e36a5ae0" "format1-bpp-indexed.py" >}}

## Related APIs

- [SaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/) — Base class for all save options.
- [PdfSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/) — Save options for PDF output.
- [ImageSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/imagesaveoptions/) — Save options for image output.
- [DocSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/) — Save options for DOC/DOT formats.
- [OdtSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/odtsaveoptions/) — Save options for ODT/OTT formats.
- [HtmlSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/) — Save options for HTML, MHTML and EPUB output.
- [MarkdownSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/) — Save options for Markdown output.
- [XpsSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/xpssaveoptions/) — Save options for XPS output.

## FAQ

1. **Q:** How can I set a password to encrypt a document when saving?  
   **A:** Use the SaveOptions class that corresponds to the target format (e.g., `DocSaveOptions` for DOC/DOT, `OoxmlSaveOptions` for DOCX) and assign the desired password to its `password` property. Then pass this options object to `Document.save`.  

   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   options = aw.saving.DocSaveOptions()
   options.password = "Secret123"
   doc.save("output.doc", options)
   ```

2. **Q:** How do I update the document creation time before saving?  
   **A:** Set the `created_time` property of the document’s built‑in properties, or enable `update_created_time_property` on the SaveOptions object. The updated time will be written to the file when you call `save`.  

   ```python
   import aspose.words as aw
   from datetime import datetime, timezone

   doc = aw.Document("input.docx")
   doc.built_in_document_properties.created_time = datetime(2023, 5, 1, tzinfo=timezone.utc)

   options = aw.saving.PdfSaveOptions()
   options.update_created_time_property = True
   doc.save("output.pdf", options)
   ```

3. **Q:** How can I prevent the **last_saved_time** property from being changed on save?  
   **A:** Set the `update_last_saved_time_property` of the appropriate SaveOptions object to `False` before calling `save`. This tells Aspose.Words to leave the existing value untouched.  

   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   options = aw.saving.OoxmlSaveOptions()
   options.update_last_saved_time_property = False
   doc.save("output.docx", options)
   ```

4. **Q:** How do I control the pixel format of images generated during saving?  
   **A:** Use `ImageSaveOptions.pixel_format` and assign a value from the `ImagePixelFormat` enumeration (e.g., `ImagePixelFormat.FORMAT_32BPP_ARGB` for 32-bit color with transparency, or `ImagePixelFormat.FORMAT_1BPP_INDEXED` for a black‑and‑white image). The option is applied when saving to an image format.  

   ```python
   import aspose.words as aw
   from aspose.words.saving import ImagePixelFormat

   doc = aw.Document("input.docx")
   options = aw.saving.ImageSaveOptions(aw.SaveFormat.PNG)
   options.pixel_format = ImagePixelFormat.FORMAT_32BPP_ARGB
   doc.save("output.png", options)
   ```

5. **Q:** Which SaveOptions class should I use for a specific output format?  
   **A:** Each output format has its own derived SaveOptions class: `PdfSaveOptions` for PDF, `HtmlSaveOptions` for HTML, MHTML and EPUB, `DocSaveOptions` for DOC/DOT, `OoxmlSaveOptions` for DOCX/DOCM, `ImageSaveOptions` for PNG/JPEG/BMP, etc. Instantiate the class that matches the desired format and configure its properties before saving.  