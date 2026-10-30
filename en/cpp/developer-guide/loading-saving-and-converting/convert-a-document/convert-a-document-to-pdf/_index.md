---
title: Convert a Document to PDF in C++
second_title: Aspose.Words for C++
articleTitle: Convert a Document to PDF
linktitle: Convert a Document to PDF
description: "Convert a document to PDF using C++. Various input formats are supported, including Word, OpenOffice, Image and eBook formats."
type: docs
weight: 10
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/convert-a-document-to-pdf/
timestamp: 2024-10-21-08-52-03
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert Word documents to PDF and details the rendering options that affect fonts, pagination, and visual fidelity.

{{% /alert %}}

The ability to easily and reliably convert documents from one format to another is a key feature of Aspose.Words. One of the most popular formats for converting is PDF – a fixed-layout format, which preserves the original appearance of a document during its rendering on various platforms. The "rendering" term is used in Aspose.Words to describe the process of converting a document into a file format that is paginated or has the concept of pages.

## Convert a Word Document to PDF

Conversion from Word to PDF is a rather complex process that requires several stages of calculation. Aspose.Words layout engine mimics the way Microsoft Word's page layout engine works, making PDF output documents look as close as possible to what you can see in Microsoft Word.

With Aspose.Words you can programmatically convert a document from Word formats, such as DOC or DOCX, to PDF without using Microsoft Office. This article explains how to perform this conversion.

{{% alert color="primary" %}}

Note that the number of pages in a document affects the conversion time.

{{% /alert %}}

### Convert DOCX or DOC to PDF

Converting from the DOC or DOCX document format into the PDF format in Aspose.Words is very easy and can be accomplished with just two lines of code that:

1. Load your document into a [Document](https://reference.aspose.com/words/cpp/aspose.words/document/) object using one of its constructors by specifying the document name with its format extension.
1. Invoke one of the [Document::Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) methods on the **Document** object and specify the desired output format as PDF by entering a file name with the “.PDF” extension.

The following code example shows how to convert a document from DOCX into PDF using the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method:

{{< gist "aspose-words-gists" "b9784b73e288805e08fba6e3fc5ae2af" "docx-to-pdf.h" >}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Rendering.docx).

{{% alert color="primary" %}}

Sometimes it is necessary to specify additional options, which can affect the result of saving a document as a PDF. These options can be specified using the [PdfSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/) class, containing properties that determine how the PDF output will be displayed.

Note that with the same technique, you can convert any flow-layout format document to PDF format.

{{% /alert %}}

### Convert to Different PDF Standards

Aspose.Words provides the [PdfCompliance](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/get_compliance/) enumeration to support the conversion of DOC or DOCX into various PDF format standards (such as PDF 1.7, PDF 2.0, etc.).

The following code example demonstrates how to convert a document to PDF 1.7 using [PdfSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/) with compliance to PDF17:

{{< gist "aspose-words-gists" "b9784b73e288805e08fba6e3fc5ae2af" "conversion-to-pdf17.h" >}}

## Convert Images to PDF

Converting to PDF is not restricted by Microsoft Word document formats. Any format supported by Aspose.Words, including programmatically created, can also be converted to PDF. For example, we can convert single-page images, such as JPEG, PNG, BMP, EMF, or WMF, as well as multi-page images, such as TIFF and GIF, to PDF.

The following code example shows how to convert JPEG and TIFF images to PDF:

{{< gist "aspose-words-gists" "b9784b73e288805e08fba6e3fc5ae2af" "image-to-pdf.h" >}}

{{< gist "aspose-words-gists" "b9784b73e288805e08fba6e3fc5ae2af" "convert-image-to-pdf.h" >}}

## Reduce PDF Output Size

When saving to PDF, you can specify whether you want to optimize the output. To do this, you need to set the [get_OptimizeOutput()](https://reference.aspose.com/words/cpp/aspose.words.saving/fixedpagesaveoptions/get_optimizeoutput/) flag to true, and then redundant nested canvases and empty canvases will be removed, neighbor glyphs with the same formatting will be concatenated.

The following code example shows how to optimize the output:

{{< gist "aspose-words-gists" "b9784b73e288805e08fba6e3fc5ae2af" "optimize-output.h" >}}

{{% alert color="primary" %}}

Using the **get_OptimizeOutput()** property may affect the accuracy of content display.

{{% /alert %}}

## See Also

- The article [Rendering](/words/cpp/rendering/) for more information on the fixed-page and flow-layout formats
- The article [Converting to Fixed‑page Format](/words/cpp/converting-to-fixed-page-format/#what-is-a-page-layout) for more information on the page layout
- The article [Specify Rendering Options When Converting to PDF](/words/cpp/specify-rendering-options-when-converting-to-pdf/) for more information on using the `PdfSaveOptions` class
- The article [Learn Features of Conversion to PDF/A and PDF/UA](/words/cpp/learn-features-of-conversion-to-pdf-a-pdf-ua/) describing which PDF standard and the relevant ISO for PDF standards support Aspose.Words
- The article [Which PDF Standard Is Better to Choose](/words/cpp/which-pdf-standard-is-better-to-choose/) to determine which PDF standards make sense for which cases

- The article [Working with PDF/A or PDF/UA](/words/cpp/working-with-pdfa-or-pdfua/) describes the requirements for the document content in PDF/A and PDF/UA formats – mainly the requirements for the structure and fonts

- The article [Accessibility Issue Warnings When Saving to PDF/A and PDF/UA](/words/cpp/warnings-when-saving-to-pdfa-and-pdfua/) describes what content accessibility requirements PDF/A and PDF/UA impose

## Limitations and Considerations

- Converting large or complex documents to PDF may be time- and memory-intensive.
- Rendering fidelity depends on the availability of fonts — missing fonts are substituted based on system settings.
- PDF/A and PDF/UA compliance imposes additional requirements: all fonts must be embedded, color spaces must be valid, and content must meet accessibility standards.
- Using `get_OptimizeOutput()` may slightly affect visual fidelity by merging glyphs or removing empty canvases.
- Some advanced Word features (e.g., certain drawing objects, complex table layouts, or field codes) may not render identically to Microsoft Word.

## Related APIs

- [PdfSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/) class
- [PdfCompliance](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfcompliance/) enumeration
- [Document::Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method
- [get_OptimizeOutput()](https://reference.aspose.com/words/cpp/aspose.words.saving/fixedpagesaveoptions/get_optimizeoutput/) property

------ 

## FAQ

1. **Q:** How do I convert a DOCX file to PDF using Aspose.Words for C++?  
   **A:** Load the DOCX into an `Aspose::Words::Document` object and call its `Save` method with a file name ending in “.pdf”. Example:  

   ```cpp
   auto doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   doc->Save(u"output.pdf");
   ```

2. **Q:** How can I create a PDF that complies with a specific standard such as PDF/A‑1b or PDF/UA‑1?  
   **A:** Use `Aspose::Words::Saving::PdfSaveOptions` and set its `Compliance` property to the desired `PdfCompliance` value, then pass the options to `Document::Save`. Example:  

   ```cpp
   auto options = System::MakeObject<Aspose::Words::Saving::PdfSaveOptions>();
   options->set_Compliance(Aspose::Words::Saving::PdfCompliance::PdfA1b);
   doc->Save(u"output_pdfa.pdf", options);
   ```

3. **Q:** How can I protect the generated PDF with a password?  
   **A:** Create a `PdfEncryptionDetails` object with a user password (and optionally an owner password), assign it to the `get_EncryptionDetails()` property of `PdfSaveOptions`, and save the document with those options. Example:  

   ```cpp
   auto options = System::MakeObject<Aspose::Words::Saving::PdfSaveOptions>();
   options->set_EncryptionDetails(
       System::MakeObject<Aspose::Words::Saving::PdfEncryptionDetails>(u"myPassword", u""));
   doc->Save(u"protected.pdf", options);
   ```

4. **Q:** How can I control image quality or compression when converting images to PDF?  
   **A:** Set `set_ImageCompression()` (e.g., `PdfImageCompression::Jpeg`) and `get_JpegQuality()` (0‑100) on `PdfSaveOptions`. This reduces file size while preserving visual quality. Example:  

   ```cpp
   auto options = System::MakeObject<Aspose::Words::Saving::PdfSaveOptions>();
   options->set_ImageCompression(Aspose::Words::Saving::PdfImageCompression::Jpeg);
   options->set_JpegQuality(80);
   doc->Save(u"images.pdf", options);
   ```

5. **Q:** How do I combine several images (e.g., scanned JPEG pages) into a single PDF document?  
   **A:** Create an empty `Document` and insert each image with `DocumentBuilder::InsertImage`, adding a page break between images. Finally, save the document as PDF. Example:  

   ```cpp
   auto doc = System::MakeObject<Aspose::Words::Document>();
   auto builder = System::MakeObject<Aspose::Words::DocumentBuilder>(doc);
   builder->InsertImage(u"page1.jpg");
   builder->InsertBreak(Aspose::Words::BreakType::PageBreak);
   builder->InsertImage(u"page2.jpg");
   // repeat for additional pages...
   doc->Save(u"combined.pdf");
   ```