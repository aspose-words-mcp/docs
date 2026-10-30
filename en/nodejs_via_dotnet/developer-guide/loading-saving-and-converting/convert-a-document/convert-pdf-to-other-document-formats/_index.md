---
title: Convert PDF to Other Document Formats
second_title: Aspose.Words for Node.js via .NET
articleTitle: Convert PDF to Other Document Formats
linktitle: Convert PDF to Other Document Formats
type: docs
description: "Convert PDF to Word formats such as DOCX, DOC, image formats such as JPG or PNG, or any other formats supported by Aspose using `Node.js`."
keywords: convert pdf to other formats Node.js
weight: 45
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/convert-pdf-to-other-document-formats/
aliases: [/nodejs/convert-pdf-to-other-document-formats/]
timestamp: 2025-04-21-14-07-04
---

Aspose.Words can load even such a complex format as PDF. This opens up new opportunities: it is possible to convert PDF to Word or other formats that bring users far ahead in solving many applied problems.

## Convert PDF to Other Formats {#convert-pdf-to-other-formats}

The most popular conversion from PDF is conversion to Microsoft Word formats such as DOCX, DOC, as well as image formats such as JPG or PNG. With that said, converting a document from one format to another performs in a familiar way.

The following code example shows how to convert a document from PDF to DOCX:

{{< gist "aspose-words-gists" "a0d52b62c1643faa76a465a41537edfc" "pdf-to-docx.js" >}}

## Specify Load Options when Importing PDF {#specify-load-options-when-importing-pdf}

Aspose.Words provides you with the [PdfLoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/pdfloadoptions/) class, which allows more precise control over how PDF documents are loaded.

Most properties inherit or overload properties that already exist in the [LoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/) class. In addition to them, a number of properties are specified for PDF format. For example, you can use the [pageCount](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/pdfloadoptions/pagecount/) and [pageIndex](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/pdfloadoptions/pageindex/) properties to define the page range to be loaded from a PDF document, and the [skipPdfImages](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/pdfloadoptions/skippdfimages/) properties to control whether images should be skipped when loading PDF. Another supported parameter is the [password](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/password/), which must be provided for password-protected documents.

## Supported PDF Content {#supported-pdf-content}

PDF2Word currently supports the following data types:

* Text paragraphs
* Images
* Tables
* Lists
* Headers and footers
* Footnotes
* Page numbers
* Right-to-left text (with some limitations)
* Searchable PDFs (front images will be removed in favor of background text)

## Planned Features {#planned-features}

Some features are still in early development or included in the development roadmap:

* Table of Contents
* OCR for Searchable and Non-Searchable PDFs
* Progress report
* Multicolumn text
* Math formulas
* More automatic fields (besides `PAGE` and NUMPAGES)

## PDF Load Exceptions

During a PDF document conversion, one of the following exceptions might happen:

| Exception | Description                                                  |
| -------------------------------- | ------------------------------------------------------------ |
| *FileLoadException*              | A PDF file cannot be processed for some reason.<br />{{% alert color="primary" %}}You can report the issue to the development team for a detailed investigation using the [technical support](/words/nodejs-net/technical-support/).{{% /alert %}} |
| *DrmProtectedFileException*      | A PDF file is protected by Adobe DRM and cannot be decoded by Pdf2Word. |
| *PasswordProtectedFileException* | The correct password must be provided for a password‑protected PDF. |

------ 

## Troubleshoot

1. **Problem:** *FileLoadException* is thrown when loading a PDF.  
   **Solution:** Verify that the file path is correct and the file is not corrupted. Ensure the PDF version is supported by Aspose.Words. If the file is large, increase the memory limit for the Node.js process or load the document in smaller page ranges using `PdfLoadOptions.pageIndex` and `PdfLoadOptions.pageCount`.

2. **Problem:** *DrmProtectedFileException* occurs during conversion.  
   **Solution:** Aspose.Words does not support Adobe DRM‑protected PDFs. Remove DRM protection with a tool that can legally decrypt the file before loading it with Aspose.Words, or obtain an unprotected version of the PDF.

3. **Problem:** *PasswordProtectedFileException* is raised for a password‑protected PDF.  
   **Solution:** Supply the password through `PdfLoadOptions`. Example:  

   ```javascript
   const aspose = require("aspose.words");
   const loadOptions = new aspose.words.loading.PdfLoadOptions();
   loadOptions.password = "MySecretPassword";
   const doc = new aspose.words.Document("protected.pdf", loadOptions);
   doc.save("output.docx");
   ```

4. **Problem:** Images are missing in the converted Word document.  
   **Solution:** Ensure that `PdfLoadOptions.skipPdfImages` is set to `false` (the default). If it has been changed, reset it:  

   ```javascript
   const loadOptions = new aspose.words.loading.PdfLoadOptions();
   loadOptions.skipPdfImages = false; // keep images
   const doc = new aspose.words.Document("source.pdf", loadOptions);
   ```

5. **Problem:** Only a subset of pages is converted or the output is empty.  
   **Solution:** Check the values of `PdfLoadOptions.pageIndex` and `PdfLoadOptions.pageCount`. Setting `pageIndex` to `0` and `pageCount` to a value greater than the total pages loads the entire document. Example:  

   ```javascript
   const loadOptions = new aspose.words.loading.PdfLoadOptions();
   loadOptions.pageIndex = 0;   // start from the first page
   loadOptions.pageCount = 0;   // 0 means all pages
   const doc = new aspose.words.Document("source.pdf", loadOptions);
   doc.save("full_output.docx");
   ```