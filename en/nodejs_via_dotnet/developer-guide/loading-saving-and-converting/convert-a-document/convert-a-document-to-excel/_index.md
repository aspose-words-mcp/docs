---
title: Convert Word to Excel in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Convert a Document to Excel
linktitle: Convert a Document to Excel
description: "Convert PDF to Excel, XML to Excel, DOCX to Excel Node.js. Save a document in various formats to XLSX using Node.js."
type: docs
weight: 15
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/convert-a-document-to-excel/
timestamp: 2025-04-21-14-23-37
---

Converting documents from one format to another is the flagship feature of Aspose.Words. You can convert documents in any available [load format](https://reference.aspose.com/words/nodejs-net/aspose.words/loadformat/) also to XLSX format.

## Convert a Document to XLSX

Converting a document to XLSX is a rather complicated process. To save your document to XLSX format using Aspose.Words, use the [XlsxSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/xlsxsaveoptions/) class and the new `Xlsx` element in the [SaveFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/) enumeration. As mentioned above, you can save the document in any load format supported by Aspose.Words to XLSX.

The following code example shows how to save PDF to XLSX:

{{< highlight js >}}
const aw = require('@aspose/words');

var doc = new aw.Document("Pdf Document.pdf");

doc.save("BaseConversions.PdfToXlsx.xlsx");
{{< /highlight >}}

{{% alert color="primary" %}}

Sometimes it is necessary to specify additional options, which can affect the result of saving a document as a XLSX. These options can be specified using the [XlsxSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/xlsxsaveoptions/) class, containing properties that determine how the XLSX output will be displayed.

{{% /alert %}}

## Find and Replace When Saving to XLSX

Also using Aspose.Words, you can find a specific string or regular expression in your document and replace it with the matching one you need. Then you can also save the result to XLSX format.

The following code example shows how to perform find and replace operation and save result to XLSX:

{{< highlight js >}}
const aw = require('@aspose/words');

var doc = new aw.Document();

var builder = new aw.DocumentBuilder(doc);
builder.writeln("Ruby bought a ruby necklace.");

// We can use a "FindReplaceOptions" object to modify the find - and -replace process.
var options = new aw.Replacing.FindReplaceOptions();

// Set the "matchCase" flag to "true" to apply case sensitivity while finding strings to replace.
// Set the "matchCase" flag to "false" to ignore character case while searching for text to replace.
options.matchCase = true;

doc.range.replace("Ruby", "Jade", options);
doc.save("BaseConversions.FindReplaceXlsx.xlsx");
{{< /highlight >}}

## Specify Compression Level When Saving to XLSX

You can also specify the compression level when saving using the [compressionLevel](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/xlsxsaveoptions/compressionlevel/) property.

The following code example shows how to specify the compression level when saving to XLSX format:

{{< highlight js >}}
const aw = require('@aspose/words');

var doc = new aw.Document("Document.docx");

var saveOptions = new aw.Saving.XlsxSaveOptions();
saveOptions.compressionLevel = aw.Saving.CompressionLevel.Maximum;

doc.save("BaseConversions.CompressXlsx.xlsx", saveOptions);
{{< /highlight >}}

## See Also

- Documentation section [Protect or Encrypt a Document](/words/nodejs-net/protect-or-encrypt-a-document/) for more information about protecting and encrypting a document
- The article [Find and Replace](/words/nodejs-net/find-and-replace/) for more information about finding and replacing the content you want

------ 

## FAQ

1. **Q:** Which document formats can be converted to Excel using Aspose.Words for Node.js?  
   **A:** Any format that Aspose.Words can load can be saved as XLSX. This includes DOC, DOCX, RTF, HTML, PDF, ODT, and many others. Load the source file with `new aw.Document("source.ext")` and then call `save` with an `.xlsx` filename or use `XlsxSaveOptions`.

2. **Q:** How do I convert a PDF file to an XLSX file in Node.js?  
   **A:** Load the PDF with `new aw.Document("input.pdf")` and call `save` specifying an XLSX filename, e.g., `doc.save("output.xlsx");`. No additional options are required unless you need custom formatting.

3. **Q:** Can I perform find‑and‑replace before saving a document as XLSX?  
   **A:** Yes. Use the `doc.range.replace(oldText, newText, options)` method (optionally configuring `FindReplaceOptions` for case‑sensitivity, regex, etc.) and then save the document to XLSX. The replacement is reflected in the resulting spreadsheet.

4. **Q:** How can I control the compression level of the generated XLSX file?  
   **A:** Create an instance of `aw.Saving.XlsxSaveOptions`, set its `compressionLevel` property (e.g., `CompressionLevel.Maximum`), and pass the options to `doc.save`, like `doc.save("output.xlsx", saveOptions);`. This reduces file size at the cost of longer processing time.