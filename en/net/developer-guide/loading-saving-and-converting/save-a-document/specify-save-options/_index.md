---
title: Specify Save Options in C#
second_title: Aspose.Words for .NET
articleTitle: Specify Save Options
linktitle: Specify Save Options
description: "More accurately control the save process using C#."
type: docs
weight: 10
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/specify-save-options/
timestamp: 2024-07-09-19-00-42
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to specify save options for different output formats.

{{% /alert %}}

When saving a document, you can set some advanced properties. Aspose.Words provides you with the [SaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/) class, which allows more precise control of the save process. There are overloads of the **Save** method that accept a **SaveOptions** object – it should be an object of a class derived from the **SaveOptions** class. Each save format has a corresponding class that holds save options for this save format, for example, there is [PdfSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/pdfsaveoptions/) for saving to PDF format, [MarkdownSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/markdownsaveoptions/) for saving to Markdown format, or [ImageSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/) for saving to an image. This article provides examples of working with some options classes derived from **SaveOptions**.

The following code example shows how to set the save options before saving the document into HTML:

{{< gist "aspose-words-gists" "83e5c469d0e72b5114fb8a05a1d01977" "export-text-input-form-field-as-text.cs" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

The article describes a few properties you can control when saving a document.

## Encrypt a Document With a Password

Use the **Password** property to get or set a password for an encrypted document. Use the **Password** property of the corresponding class to work with the selected document format.

For example, when saving a document to DOC or DOT format, use the [Password](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/password/) property of the [DocSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/) class.

The following code example shows how to set a password to encrypt a document using the RC4 encryption method:

{{< gist "aspose-words-gists" "af95c7a408187bb25cf9137465fe5ce6" "encrypt-document-with-password.cs" >}}

When saving a document to Odt format, use the [Password](https://reference.aspose.com/words/net/aspose.words.saving/odtsaveoptions/password/) property of the [OdtSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/odtsaveoptions/) class.

The following code example shows how to load and save OpenDocument encrypted with a password:

{{< gist "aspose-words-gists" "af95c7a408187bb25cf9137465fe5ce6" "load-save-encrypted-document.cs" >}}

Not all formats support encryption and the use of **Password** property.

## Show Document Saving Progress Notifications

Aspose.Words provides the ability to use the [ProgressCallback](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/progresscallback/) property to get notifications about the progress of document saving.

It is now available when saving to DOCX, FlatOpc, DOCM, DOTM, DOTX, HTML, MHTML, EPUB, XamlFlow, XamlFlowPack, or TXT formats.

## Update the Document Creation Time

Aspose.Words provides an ability to use the [CreatedTime](https://reference.aspose.com/words/net/aspose.words.properties/builtindocumentproperties/createdtime/) property to get or set the document creation date in UTC. You can also update this value before saving using the [UpdateCreatedTimeProperty](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/updatecreatedtimeproperty/) option.

The following code example shows how to update the document creation time:

{{< gist "aspose-words-gists" "83e5c469d0e72b5114fb8a05a1d01977" "update-last-printed.cs" >}}

## Update Last Saved Property

Aspose.Words provides an ability to use the [UpdateLastSavedTimeProperty](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/) property to get or set a value determining whether the [LastSavedTime](https://reference.aspose.com/words/net/aspose.words.properties/builtindocumentproperties/lastsavedtime/) property is updated before saving.

The following code example shows how to set this property and save the document:

{{< gist "aspose-words-gists" "83e5c469d0e72b5114fb8a05a1d01977" "update-last-saved-time.cs" >}}

## Control External Resources When Saving a Document into HTML or SVG

To convert HTML or SVG into PDF, simply invoke the [Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save/) method and specify a file name with the “.PDF” extension. If you want to load images, CSS, etc. from external sources, you can use [IResourceSavingCallback](https://reference.aspose.com/words/net/aspose.words.saving/iresourcesavingcallback/).

## Save Black and White Image with One Bit Per Pixel Format

To control image saving options, the **ImageSaveOptions** class is used. For example, you can use the [PixelFormat](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/pixelformat/) property to set the pixel format for the generated images. Please note that the pixel format of the output image may differ from the set value because of the work of GDI+.

The following code example shows how to save a black and white image with one bit per pixel format:

{{< gist "aspose-words-gists" "83e5c469d0e72b5114fb8a05a1d01977" "format1-bpp-indexed.cs" >}}

## Related APIs

- [SaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/) — Base class for all save options.
- [PdfSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/pdfsaveoptions/) — Save options for PDF output.
- [ImageSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/imagesaveoptions/) — Save options for image output.
- [DocSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/) — Save options for DOC/DOT formats.
- [OdtSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/odtsaveoptions/) — Save options for ODT/OTT formats.
- [HtmlSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/) — Save options for HTML, MHTML and EPUB output.
- [MarkdownSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/markdownsaveoptions/) — Save options for Markdown output.
- [XpsSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/xpssaveoptions/) — Save options for XPS output.

## FAQ

1. **Q:** How can I encrypt a document with a password when saving it?  
   **A:** Use the password option of the specific `SaveOptions` class for the target format (e.g., `PdfSaveOptions.EncryptionDetails` for PDF, `DocSaveOptions.Password` or `OoxmlSaveOptions.Password` for Word formats). Create the options object, set the password, and pass it to `Document.Save`. Example:  

   ```csharp
   Document doc = new Document("input.docx");
   PdfSaveOptions options = new PdfSaveOptions();
   options.EncryptionDetails = new PdfEncryptionDetails("MySecret", string.Empty);
   doc.Save("output.pdf", options);
   ```

2. **Q:** How do I receive progress notifications while a large document is being saved?  
   **A:** Implement the `IDocumentSavingCallback` interface and assign it to the `ProgressCallback` property of the save options. Its `Notify` method receives `DocumentSavingArgs`, whose `EstimatedProgress` property gives the percentage completed. Progress is reported when saving to DOCX, FlatOpc, DOCM, DOTM, DOTX, DOC, DOT, HTML, MHTML, EPUB, XamlFlow, and XamlFlowPack; it is not reported for other formats such as PDF. Example:  

   ```csharp
   Document doc = new Document("large.docx");
   OoxmlSaveOptions options = new OoxmlSaveOptions();
   options.ProgressCallback = new SavingProgressPrinter();
   doc.Save("large-copy.docx", options);

   class SavingProgressPrinter : IDocumentSavingCallback
   {
       public void Notify(DocumentSavingArgs args)
       {
           Console.WriteLine($"Saving progress: {args.EstimatedProgress:F0}%");
       }
   }
   ```

3. **Q:** How can I set the PDF compliance level (e.g., PDF/A‑1b) when saving to PDF?  
   **A:** Use the `Compliance` property of `PdfSaveOptions`. Choose a value from the `PdfCompliance` enumeration such as `PdfCompliance.PdfA1b`. Example:  

   ```csharp
   Document doc = new Document("report.docx");
   PdfSaveOptions options = new PdfSaveOptions();
   options.Compliance = PdfCompliance.PdfA1b;
   doc.Save("report.pdf", options);
   ```

4. **Q:** How do I control the pixel format of images generated when saving a document as an image?  
   **A:** Set the `PixelFormat` property of `ImageSaveOptions` to the desired `ImagePixelFormat` value (e.g., `ImagePixelFormat.Format1bppIndexed` for black‑and‑white). Example:  

   ```csharp
   Document doc = new Document("diagram.docx");
   ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
   options.PixelFormat = ImagePixelFormat.Format1bppIndexed;
   doc.Save("diagram.png", options);
   ```