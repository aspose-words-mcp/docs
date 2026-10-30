---
title: Conversion to PDF/A and PDF/UA
second_title: Aspose.Words for C++
articleTitle: Learn Features of Conversion to PDF/A and PDF/UA
linktitle: Learn Features of Conversion to PDF/A and PDF/UA
description: "Convert to PDF/A-1, PDF/A-2, PDF/A-4 and PDF/UA using C++. Choose the best PDF standard to convert a document using C++."
type: docs
weight: 35
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/learn-features-of-conversion-to-pdf-a-pdf-ua/
aliases: [/cpp/learn-features-of-conversion-to-pdf-a/]
timestamp: 2024-01-31-14-23-37
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how Aspose.Words converts documents to PDF/A and PDF/UA formats, outlining supported compliance levels and conversion specifics.

{{% /alert %}}

PDF is a fixed page format that is very popular among users and is widely supported by various applications, as a PDF document looks the same on any device. For this reason, converting to PDF is an important feature of Aspose.Words.

PDF is a complex format by itself, as it has a specific file structure, graphical model, font embedding, and some complex output functionality such as document structure tags, encryption, digital signatures, and editable forms. In addition, converting a document to PDF requires several calculation stages, which are complex and time-consuming.

In the following articles, we will consider the main problems that may arise when working with documents in various PDF standards and describe options for solving them.

## Which PDF Standard Aspose.Words Supports

Aspose.Words now allows users to work with PDF/A-1, PDF/A-2 and PDF/A-4 formats, as well as PDF/UA-1:

* PDF/A-1 has serious limitations such as transparency and some compression options are prohibited
* PDF/A-2 eliminates some of the limitations of PDF/A-1, such as support of transparency and layer effects or embedding of OpenType fonts
* PDF/A-4 assumes revised conformance levels: regular PDF/A-4 conformance is equivalent to previous versions' level U conformance, and the level A conformance is removed
* PDF/UA-1 content should be tagged and standardized according to ISO 32000-1: 2008

PDF/A is an ISO-standardized version of PDF intended for use in archiving and long‑term storage of electronic documents. At the same time, PDF/UA is another ISO standardized version of PDF designed to ensure accessibility for people with disabilities who use assistive technology. To specify the level of compliance with PDF standards, use the [get_Compliance()](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/get_compliance/) property. Due to storage conditions, PDF/A document must embed all fonts and disable encryption, while PDF/UA must only embed all fonts.

In this section, we will take a closer look at working with PDF/A or PDF/UA-1 documents.

## Relevant ISO for PDF Standards

To learn more about the different PDF standards, check the following ISOs:

* PDF 1.7 = ISO-32000-1: 2008
* PDF 2.0 = ISO-32000-2: 2020
* PDF/A-1 = ISO-19005-1: 2005
* PDF/A-2 = ISO-19005-2: 2011
* PDF/A-4 = ISO-19005-4: 2020
* PDF/UA-1 = ISO-14289: 2014  

## See Also

* [Convert a Document to PDF](/words/cpp/convert-a-document-to-pdf/)
* [How to edit document structure tags in Adobe Acrobat](https://helpx.adobe.com/acrobat/using/editing-document-structure-content-tags.html)
* [How to check or edit text language in Microsoft Word](https://support.microsoft.com/en-us/word/check-spelling-and-grammar-in-a-different-language)
* [How to change text language in Adobe Acrobat](https://helpx.adobe.com/acrobat/using/editing-document-structure-content-tags.html#add_alternate_text_and_supplementary_information_to_tags)
* [How to add alternative text to a shape, picture, chart, SmartArt graphic, or other object in Microsoft Word](https://support.microsoft.com/en-us/accessibility/office-accessibility/add-alternative-text-to-a-shape-picture-chart-smartart-graphic-or-other-object)
* [How to add alternate text and supplementary information to tags](https://helpx.adobe.com/acrobat/using/create-verify-pdf-accessibility.html) (or read the same information in the [Adobe Acrobat User Guide](https://helpx.adobe.com/acrobat/using/editing-document-structure-content-tags.html#add_alternate_text_and_supplementary_information_to_tags))
* [How to set up ActualText entry for text](https://helpx.adobe.com/acrobat/using/create-verify-pdf-accessibility.html), the “Add Actual Text for an Abbreviated Term, Formula, or Non-Unicode Symbol” section
* [Unicode mapping for common Windows symbolic fonts](http://www.alanwood.net/demos/webdings.html)

## Related APIs

- [PdfSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/)
- [PdfCompliance](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfcompliance/)    

## FAQ

1. **Q:** How do I set the PDF/A or PDF/UA compliance level when saving a document with Aspose.Words for C++?
   **A:** Create a `PdfSaveOptions` object, set its `Compliance` property to the desired `PdfCompliance` value (for example, `PdfCompliance::PdfA1b`, `PdfCompliance::PdfA2u`, `PdfCompliance::PdfA4`, or `PdfCompliance::PdfUa1`), and pass the options to the `Document::Save` method. Example:

   ```cpp
   System::SharedPtr<Aspose::Words::Document> doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   System::SharedPtr<Aspose::Words::Saving::PdfSaveOptions> options = System::MakeObject<Aspose::Words::Saving::PdfSaveOptions>();
   options->set_Compliance(Aspose::Words::Saving::PdfCompliance::PdfA2u);
   doc->Save(u"output.pdf", options);
   ```

2. **Q:** Do I need to embed all fonts manually for PDF/A compliance?
   **A:** No. When you set a PDF/A compliance level, Aspose.Words automatically embeds all fonts used in the document. You can control font substitution via `FontSettings` if required, but explicit embedding is not necessary.

3. **Q:** Can I encrypt a PDF/A document? What happens if I try?
   **A:** PDF/A specifications prohibit encryption. If you set a PDF/A compliance level and also enable encryption (e.g., `options->set_EncryptionDetails(...)`), Aspose.Words will ignore the encryption settings and generate an unencrypted PDF/A file, ensuring the document remains compliant.

4. **Q:** How can I verify that the generated PDF meets the selected PDF/A or PDF/UA standard?
   **A:** After saving, you can use a PDF validation tool (such as Adobe Acrobat Preflight or the open‑source VeraPDF) to check conformance. Aspose.Words does not perform post‑save validation, so an external validator is required for certification.

5. **Q:** What are the main differences between PDF/A‑1, PDF/A‑2, and PDF/A‑4 regarding transparency and conformance levels?
   **A:**
   * **PDF/A‑1** has serious limitations: transparency and some compression options are prohibited.
   * **PDF/A‑2** eliminates some of these limitations: it supports transparency and layer effects, and allows embedding of OpenType fonts.
   * **PDF/A‑4** revises the conformance levels: regular PDF/A‑4 conformance is equivalent to level U conformance of previous versions, and level A conformance is removed.
   All PDF/A versions require all fonts to be embedded.