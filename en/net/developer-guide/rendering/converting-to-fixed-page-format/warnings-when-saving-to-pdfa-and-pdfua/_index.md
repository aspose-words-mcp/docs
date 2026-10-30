---  
title: Warnings When Saving to PDF/A and PDF/UA  
second_title: Aspose.Words for .NET  
articleTitle: Accessibility Issue Warnings When Saving to PDF/A and PDF/UA  
linktitle: Accessibility Issue Warnings When Saving to PDF/A and PDF/UA  
description: "PDF/A and PDF/UA impose accessibility requirements related to document content. When saving to PDF/A or PDF/UA in C# and the issue violates compliance, a warning is issued."  
type: docs  
weight: 29  
ai_search_scope: words_net  
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"  
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"  
url: /net/warnings-when-saving-to-pdfa-and-pdfua/  
timestamp: 2024-01-27-14-07-04  
---  

{{% alert color="grey" %}}

## Purpose Summary

This page explains warnings that may appear when saving to PDF/A or PDF/UA and how to handle them.

{{% /alert %}}

PDF/A and PDF/UA formats impose a number of accessibility requirements related to document content that cannot be fulfilled during automatic conversion from Word to PDF. These requirements are described in the previous article *"Working with PDF/A or PDF/UA"*. Now warnings are issued for some of these problems.

Warnings are issued when saving to one of the PDF/A or PDF/UA formats and the issue violates compliance. For example, the warning about missing document title will be issued when saving to PDF/UA and will not be issued when saving to PDF/A.

All warnings are of [WarningType](https://reference.aspose.com/words/net/aspose.words/warningtype/)**.MinorFormattingLoss** and [WarningSource](https://reference.aspose.com/words/net/aspose.words/warningsource/)**.Pdf**. Here is a list of the new Description warning values:

| Description warning value                                    | PDF/A                  | PDF/UA                 |
| ------------------------------------------------------------ | ---------------------- | ---------------------- |
| "Document title is missing. This violates the compliance requirements. The output document will not be fully compliant." |                        | {{< emoticons/tick >}} |
| "The document contains headings which levels are not consecutive. This violates the compliance requirements. The output document will not be fully compliant." |                        | {{< emoticons/tick >}} |
| "There are shapes without alt text in the document. This violates the compliance requirements. The output document will not be fully compliant." | {{< emoticons/tick >}} | {{< emoticons/tick >}} |
| "There are tables without alt text in the document. This violates the compliance requirements. The output document will not be fully compliant." | {{< emoticons/tick >}} | {{< emoticons/tick >}} |
| "There are hyperlinks without alt text in the document. This violates the compliance requirements. The output document will not be fully compliant." |                        | {{< emoticons/tick >}} |
| "There are tables without header row/column in the document. This violates the compliance requirements. The output document will not be fully compliant." |                        | {{< emoticons/tick >}} |
| "The document contains Unicode PUA characters. This violates the compliance requirements. The output document will not be fully compliant." | {{< emoticons/tick >}} |                        |
| "The document contains .notdef glyphs. This violates the compliance requirements. The output document will not be fully compliant." | {{< emoticons/tick >}} | {{< emoticons/tick >}} |

------

## FAQ

1. **Q:** *What kinds of warnings are generated when saving to PDF/A or PDF/UA?*  
   **A:** Aspose.Words emits warnings of type **WarningType.MinorFormattingLoss** with source **WarningSource.Pdf** for accessibility issues that cannot be automatically fixed. Examples include missing document title (PDF/UA), shapes or tables without alternative text (both PDF/A and PDF/UA), non‑consecutive heading levels (PDF/UA), and presence of Unicode PUA characters (PDF/A).

2. **Q:** *How can I retrieve the list of warnings after saving a document?*  
   **A:** Implement `IWarningCallback` and assign it to `Document.WarningCallback` before saving. The callback receives a `WarningInfo` object for each warning, where you can inspect `WarningInfo.Description`, `WarningInfo.WarningType`, and `WarningInfo.Source`. Example:

   ```csharp
   using Aspose.Words;
   using Aspose.Words.Saving;

   Document doc = new Document("input.docx");
   PdfSaveOptions saveOptions = new PdfSaveOptions();

   doc.WarningCallback = new WarningPrinter();
   doc.Save("output.pdf", saveOptions);

   class WarningPrinter : IWarningCallback
   {
       public void Warning(WarningInfo info)
       {
           Console.WriteLine($"Warning: {info.Description}");
       }
   }
   ```

3. **Q:** *What should I do to fix a “Document title is missing” warning for PDF/UA?*  
   **A:** Add a title to the Word document before conversion. You can set the title programmatically via the built‑in document properties:

   ```csharp
   Document doc = new Document("input.docx");
   doc.BuiltInDocumentProperties.Title = "My Accessible Document";
   doc.Save("output.pdf", SaveFormat.Pdf);
   ```

   After adding the title, the warning will no longer appear when saving to PDF/UA.

4. **Q:** *Is there a way to programmatically check whether a saved PDF complies with PDF/A or PDF/UA?*  
   **A:** Aspose.Words does not perform full compliance validation, but you can examine the warnings collected during saving. If no warnings related to the target standard are reported, the document is likely compliant. For rigorous validation, use a dedicated PDF/A or PDF/UA validator such as Aspose.PDF or third‑party tools.