---
title: Convert Word to PDF in C#
second_title: Aspose.Words for .NET
articleTitle: Convert a Document to PDF
linktitle: Convert a Document to PDF
description: "Convert Word to PDF in C#. Easy code examples for DOCX to PDF conversion. Supports all Word and image formats."
type: docs
weight: 10
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/convert-a-document-to-pdf/
timestamp: 2024-09-25-11-08-55
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

1. Load your document into a [Document](https://reference.aspose.com/words/net/aspose.words/document/) object using one of its constructors by specifying the document name with its format extension.
1. Invoke one of the [Document.Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save/) methods on the **Document** object and specify the desired output format as PDF by entering a file name with the “.PDF” extension.

The following code example shows how to convert a document from DOCX into PDF using the [Save](https://reference.aspose.com/words/net/aspose.words/document/save/) method:

{{< gist "aspose-words-gists" "a53bdaad548845275c1b9556ee21ae65" "docx-to-pdf.cs" >}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Rendering.docx).

{{% alert color="primary" %}}

Sometimes it is necessary to specify additional options, which can affect the result of saving a document as a PDF. These options can be specified using the [PdfSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/pdfsaveoptions/) class, containing properties that determine how the PDF output will be displayed.

Note that with the same technique, you can convert any flow-layout format document to PDF format.

{{% /alert %}}

### Convert to Different PDF Standards

Aspose.Words provides the [PdfCompliance](https://reference.aspose.com/words/net/aspose.words.saving/pdfcompliance/) enumeration to support the conversion of DOC or DOCX into various PDF format standards (such as PDF 1.7, PDF 2.0, etc.).

The following code example demonstrates how to convert a document to PDF 1.7 using [PdfSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/pdfsaveoptions/) with compliance to PDF17:

{{< gist "aspose-words-gists" "a53bdaad548845275c1b9556ee21ae65" "conversion-to-pdf17.cs" >}}

## Convert Images to PDF

Converting to PDF is not restricted by Microsoft Word document formats. Any format supported by Aspose.Words, including programmatically created, can also be converted to PDF. For example, we can convert single-page images, such as JPEG, PNG, BMP, EMF, or WMF, as well as multi-page images, such as TIFF and GIF, to PDF.

The following code example shows how to convert JPEG and TIFF images to PDF:

{{< gist "aspose-words-gists" "a53bdaad548845275c1b9556ee21ae65" "image-to-pdf.cs" >}}

{{< gist "aspose-words-gists" "a53bdaad548845275c1b9556ee21ae65" "convert-image-to-pdf.cs" >}}

To make this code work, you need to add references to Aspose.Words and `System.Drawing` to your project.

## Reduce PDF Output Size

When saving to PDF, you can specify whether you want to optimize the output. To do this, you need to set the [OptimizeOutput](https://reference.aspose.com/words/net/aspose.words.saving/fixedpagesaveoptions/optimizeoutput/) flag to true, and then redundant nested canvases and empty canvases will be removed, neighbor glyphs with the same formatting will be concatenated.

The following code example shows how to optimize the output:

{{< gist "aspose-words-gists" "a53bdaad548845275c1b9556ee21ae65" "optimize-output.cs" >}}

{{% alert color="primary" %}}

Using the **OptimizeOutput** property may affect the accuracy of content display.

{{% /alert %}}

## See Also

- The article [Rendering](/words/net/rendering/) for more information on the fixed-page and flow-layout formats
- The article [Converting to Fixed-page Format](/words/net/converting-to-fixed-page-format/#what-is-a-page-layout) for more information on the page layout
- The article [Specify Rendering Options When Converting to PDF](/words/net/specify-rendering-options-when-converting-to-pdf/) for more information on using the `PdfSaveOptions` class
- The article [Learn Features of Conversion to PDF/A and PDF/UA](/words/net/learn-features-of-conversion-to-pdf-a-pdf-ua/) describing which PDF standard and the relevant ISO for PDF standards support Aspose.Words
- The article [Which PDF Standard Is Better to Choose](/words/net/which-pdf-standard-is-better-to-choose/) to determine which PDF standards make sense for which cases

- The article [Working with PDF/A or PDF/UA](/words/net/working-with-pdfa-or-pdfua/) describes the requirements for the document content in PDF/A and PDF/UA formats – mainly the requirements for the structure and fonts

- The article [Accessibility Issue Warnings When Saving to PDF/A and PDF/UA](/words/net/warnings-when-saving-to-pdfa-and-pdfua/) describes what content accessibility requirements PDF/A and PDF/UA impose

## Limitations and Considerations

- Converting large or complex documents to PDF may be time- and memory-intensive.
- Rendering fidelity depends on the availability of fonts — missing fonts are substituted based on system settings.
- PDF/A and PDF/UA compliance imposes additional requirements: all fonts must be embedded, color spaces must be valid, and content must meet accessibility standards.
- Using `OptimizeOutput` may slightly affect visual fidelity by merging glyphs or removing empty canvases.
- Some advanced Word features (e.g., certain drawing objects, complex table layouts, or field codes) may not render identically to Microsoft Word.

## Related APIs

- [PdfSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/pdfsaveoptions/) class
- [PdfCompliance](https://reference.aspose.com/words/net/aspose.words.saving/pdfcompliance/) enumeration
- [Document.Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save()) method
- [OptimizeOutput](https://reference.aspose.com/words/net/aspose.words.saving/fixedpagesaveoptions/optimizeoutput/) property

------

## FAQ

1. **Q:** How do I convert a DOCX file to PDF using C#?  
   **A:** Load the DOCX into an `Aspose.Words.Document` object and call its `Save` method with a filename that has a `.pdf` extension. Example:  

   ```csharp
   Document doc = new Document("input.docx");
   doc.Save("output.pdf");
   ```

2. **Q:** How can I set a specific PDF compliance level (e.g., PDF/A‑1b, PDF 1.7) when saving?  
   **A:** Use `PdfSaveOptions` and set its `Compliance` property to the desired `PdfCompliance` enum value, then pass the options to `Document.Save`. Example:  

   ```csharp
   PdfSaveOptions options = new PdfSaveOptions();
   options.Compliance = PdfCompliance.PdfA1b;   // or PdfCompliance.Pdf17, etc.
   Document doc = new Document("input.docx");
   doc.Save("output.pdf", options);
   ```

3. **Q:** What can I do to reduce the size of the generated PDF?  
   **A:** Enable output optimization by setting `OptimizeOutput` to `true` in `PdfSaveOptions`. This removes redundant canvases and merges identical glyphs, which often reduces file size. Example:  

   ```csharp
   PdfSaveOptions options = new PdfSaveOptions();
   options.OptimizeOutput = true;
   Document doc = new Document("input.docx");
   doc.Save("output.pdf", options);
   ```

4. **Q:** Can I convert images such as JPEG or TIFF directly to PDF with Aspose.Words?  
   **A:** Yes. Create a new `Document`, insert the image(s) using a `DocumentBuilder`, and then save the document as PDF. Example for a TIFF with multiple pages:  

   ```csharp
   Document doc = new Document();
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.InsertImage("image.tiff");
   doc.Save("output.pdf");
   ```

5. **Q:** Do I need a license to use the PDF conversion features of Aspose.Words?  
   **A:** A license is not required for basic functionality, but without a license the generated PDFs will contain a watermark and evaluation messages. Applying a valid Aspose.Words license removes these restrictions and enables full‑featured performance.  

------