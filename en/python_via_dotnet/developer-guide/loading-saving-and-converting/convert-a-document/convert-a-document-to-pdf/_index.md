---
title: Convert a Document to PDF in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Convert a Document to PDF
linktitle: Convert a Document to PDF
description: "Convert a document to PDF using Python. Various input formats are supported, including Word, OpenOffice, Image and eBook formats."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/convert-a-document-to-pdf/
aliases: [/python/convert-a-document-to-pdf/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to convert various document types—including Word files, images, and other supported formats—to PDF, covering basic conversion, PDF compliance options, and output size optimization.

{{% /alert %}}

The ability to easily and reliably convert documents from one format to another is a key feature of Aspose.Words. One of the most popular formats for converting is PDF – a fixed-layout format, which preserves the original appearance of a document during its rendering on various platforms. The "rendering" term is used in Aspose.Words to describe the process of converting a document into a file format that is paginated or has the concept of pages.

## Convert a Word Document to PDF

Conversion from Word to PDF is a rather complex process that requires several stages of calculation. Aspose.Words layout engine mimics the way Microsoft Word’s page layout engine works, making PDF output documents look as close as possible to what you can see in Microsoft Word.

With Aspose.Words you can programmatically convert a document from Word formats, such as DOC or DOCX, to PDF without using Microsoft Office. This article explains how to perform this conversion.

{{% alert color="primary" %}}

Note that the number of pages in a document affects the conversion time.

{{% /alert %}}

### Convert DOCX or DOC to PDF

Converting from the DOC or DOCX document format into the PDF format in Aspose.Words is very easy and can be accomplished with just two lines of code that:

1. Load your document into a [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) object using one of its constructors by specifying the document name with its format extension.
1. Invoke one of the [Document.save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) methods on the **Document** object and specify the desired output format as PDF by entering a file name with the “.PDF” extension.

The following code example shows how to convert a document from DOCX into PDF using the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/#str) method:

{{< gist "aspose-words-gists" "36a49a29062268dc5e6d3134163f8d99" "docx-to-pdf.py" >}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Rendering.docx).

{{% alert color="primary" %}}

Sometimes it is necessary to specify additional options, which can affect the result of saving a document as a PDF. These options can be specified using the [PdfSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/) class, containing properties that determine how the PDF output will be displayed.

Note that with the same technique, you can convert any flow-layout format document to PDF format.

{{% /alert %}}

### Convert to Different PDF Standards

Aspose.Words provides the [PdfCompliance](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfcompliance/) enumeration to support the conversion of DOC or DOCX into various PDF format standards (such as PDF 1.7, PDF 1.5, etc.).

The following code example demonstrates how to convert a document to PDF 1.7 using [PdfSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/) with compliance to PDF17:

{{< gist "aspose-words-gists" "36a49a29062268dc5e6d3134163f8d99" "conversion-to-pdf17.py" >}}

## Convert Images to PDF

Converting to PDF is not restricted by Microsoft Word document formats. Any format supported by Aspose.Words, including programmatically created, can also be converted to PDF. For example, we can convert single-page images, such as JPEG, PNG, BMP, EMF, or WMF, as well as multi-page images, such as TIFF and GIF, to PDF.

The following code example shows how to convert JPEG and TIFF images to PDF:

{{< gist "aspose-words-gists" "36a49a29062268dc5e6d3134163f8d99" "image-to-pdf.py" >}}

{{< gist "aspose-words-gists" "36a49a29062268dc5e6d3134163f8d99" "convert-image-to-pdf.py" >}}

To make this code work, you need to add references to Aspose.Words and `aspose.pydrawing` to your project.

## Reduce PDF Output Size

When saving to PDF, you can specify whether you want to optimize the output. To do this, you need to set the [optimize_output](https://reference.aspose.com/words/python-net/aspose.words.saving/fixedpagesaveoptions/optimize_output/) flag to true, and then redundant nested canvases and empty canvases will be removed, neighbor glyphs with the same formatting will be concatenated.

The following code example shows how to optimize the output:

{{< gist "aspose-words-gists" "36a49a29062268dc5e6d3134163f8d99" "optimize-output.py" >}}

{{% alert color="primary" %}}

Using the **optimize_output** property may affect the accuracy of content display.

{{% /alert %}}

## See Also

- The article [Rendering](/words/python-net/rendering/) for more information on the fixed-page and flow-layout formats
- The article [Converting to Fixed-page Format](/words/python-net/converting-to-fixed-page-format/#what-is-a-page-layout) for more information on the page layout
- The article [Specify Rendering Options When Converting to PDF](/words/python-net/specify-rendering-options-when-converting-to-pdf/) for more information on using the `PdfSaveOptions` class
- The article [Learn Features of Conversion to PDF/A and PDF/UA](/words/python-net/learn-features-of-conversion-to-pdf-a/) describing which PDF standard and the relevant ISO for PDF standards support Aspose.Words
- The article [Which PDF Standard Is Better to Choose](/words/python-net/which-pdf-standard-is-better-to-choose/) to determine which PDF standards make sense for which cases

- The article [Working with PDF/A or PDF/UA](/words/python-net/working-with-pdfa-or-pdfua/) describes the requirements for the document content in PDF/A and PDF/UA formats – mainly the requirements for the structure and fonts

- The article [Accessibility Issue Warnings When Saving to PDF/A and PDF/UA](/words/python-net/warnings-when-saving-to-pdfa-and-pdfua/) describes what content accessibility requirements PDF/A and PDF/UA impose

## Limitations and Considerations

- Converting large or complex documents to PDF may be time- and memory-intensive.
- Rendering fidelity depends on the availability of fonts — missing fonts are substituted based on system settings.
- PDF/A and PDF/UA compliance imposes additional requirements: all fonts must be embedded, color spaces must be valid, and content must meet accessibility standards.
- Using `optimize_output` may slightly affect visual fidelity by merging glyphs or removing empty canvases.
- Some advanced Word features (e.g., certain drawing objects, complex table layouts, or field codes) may not render identically to Microsoft Word.

## Related APIs

- [PdfSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/) class
- [PdfCompliance](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfcompliance/) enumeration
- [Document.save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method
- [optimize_output](https://reference.aspose.com/words/python-net/aspose.words.saving/fixedpagesaveoptions/optimize_output/) property  

## FAQ

1. **Q:** How do I convert a DOCX file to PDF using Aspose.Words for Python via .NET?  
   **A:** Load the DOCX into a `Document` object and call its `save` method with a filename that ends with `.pdf`. Example:  
   ```python
   from aspose.words import Document
   doc = Document("input.docx")
   doc.save("output.pdf")
   ```

2. **Q:** How can I create a PDF that complies with a specific PDF standard (e.g., PDF 1.7)?  
   **A:** Use `PdfSaveOptions` and set its `compliance` property to the desired `PdfCompliance` value before saving. Example:  
   ```python
   doc = aw.Document("input.docx")
   options = aw.saving.PdfSaveOptions()
   options.compliance = aw.saving.PdfCompliance.PDF17
   doc.save("output.pdf", options)
   ```

3. **Q:** What is the recommended way to reduce the size of the generated PDF?  
   **A:** Enable the `optimize_output` flag in `FixedPageSaveOptions` (or `PdfSaveOptions`). This removes redundant canvases and merges identical glyphs. Example:  
   ```python
   doc = aw.Document("input.docx")
   options = aw.saving.PdfSaveOptions()
   options.optimize_output = True
   doc.save("output.pdf", options)
   ```

4. **Q:** Can I convert image files such as JPEG, PNG, or multi‑page TIFF to PDF?  
   **A:** Yes. Load the image using `Document` and save it as PDF. Example for a JPEG:  
   ```python
   doc = aw.Document("photo.jpg")
   doc.save("photo.pdf")
   ```

5. **Q:** Is it possible to convert multiple images (e.g., a set of PNG files) into a single PDF document?  
   **A:** Create a new `Document`, insert each image as a separate section or page using `DocumentBuilder`, then save the document as PDF. Example:  
   ```python
   pdf_doc = aw.Document()
   builder = aw.DocumentBuilder(pdf_doc)
   for image_path in ["page1.png", "page2.png"]:
       builder.insert_image(image_path)
       builder.insert_break(aw.BreakType.PAGE_BREAK)
   pdf_doc.save("combined.pdf")
   ```