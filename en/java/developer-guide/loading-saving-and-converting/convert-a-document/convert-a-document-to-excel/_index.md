---
title: Convert Word to Excel in Java
second_title: Aspose.Words for Java
articleTitle: Convert a Document to Excel
linktitle: Convert a Document to Excel
description: "Convert XML to Excel, Word to Excel (including DOCX to Excel) in Java. Save a document in various formats to XLSX using Java."
type: docs
weight: 15
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/convert-a-document-to-excel/
timestamp: 2024-01-31-14-23-37
---

{{% alert color="grey" %}}

## Purpose Summary

This page outlines how to convert a Word document to Excel format (XLS/XLSX) using Aspose.Words.

{{% /alert %}}

Converting documents from one format to another is the flagship feature of Aspose.Words. You can convert documents in any available [load format](https://reference.aspose.com/words/java/com.aspose.words/loadformat/) also to XLSX format.

## Convert a Document to XLSX

Converting a document to XLSX is a rather complicated process. To save your document to XLSX format using Aspose.Words, use the [XlsxSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/xlsxsaveoptions/) class and the new `Xlsx` element in the [SaveFormat](https://reference.aspose.com/words/java/com.aspose.words/saveformat/) enumeration. As mentioned above, you can save the document in any load format supported by Aspose.Words to XLSX.

The following code example shows how to save DOCX to XLSX:

{{< gist "aspose-words-gists" "82fb3ee435d5abdc1472a58774ebe98c" "docx-to-xlsx.java" >}}

{{% alert color="primary" %}}

Sometimes it is necessary to specify additional options, which can affect the result of saving a document as a XLSX. These options can be specified using the [XlsxSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/xlsxsaveoptions/) class, containing properties that determine how the XLSX output will be displayed.

{{% /alert %}}

## Find and Replace When Saving to XLSX

Also using Aspose.Words, you can find a specific string or regular expression in your document and replace it with the matching one you need. Then you can also save the result to XLSX format.

The following code example shows how to perform find and replace operation and save result to XLSX:

{{< gist "aspose-words-gists" "50971daf8f0c9ef4b0250c4a526b1652" "find-replace-xlsx.java" >}}

## Specify Compression Level When Saving to XLSX

You can also specify the compression level when saving using the [CompressionLevel](https://reference.aspose.com/words/java/com.aspose.words/compressionlevel/) property.

The following code example shows how to specify the compression level when saving to XLSX format:

{{< gist "aspose-words-gists" "50971daf8f0c9ef4b0250c4a526b1652" "compress-xlsx.java" >}}

## See Also

- Documentation section [Protect or Encrypt a Document](/words/java/protect-or-encrypt-a-document/) for more information about protecting and encrypting a document
- The article [Find and Replace](/words/java/find-and-replace/) for more information about finding and replacing the content you want

------ 

## FAQ

1. **Q:** Which document formats can be converted to Excel using Aspose.Words for Java?  
   **A:** Aspose.Words can load any format listed in the `LoadFormat` enumeration (e.g., DOC, DOCX, RTF, HTML, ODT, EPUB, etc.). After loading, you can save the document to XLSX by using `XlsxSaveOptions` with the `SaveFormat.XLSX` option.

2. **Q:** How do I perform a find‑and‑replace operation before saving to XLSX?  
   **A:** Use the document's `Range` to locate and replace text (e.g., `doc.getRange().replace("old", "new", new FindReplaceOptions())`). After the replacement, call `document.save("output.xlsx", SaveFormat.XLSX)` with optional `XlsxSaveOptions`.

3. **Q:** How can I control the compression level of the generated XLSX file?  
   **A:** Create an instance of `XlsxSaveOptions` and call `setCompressionLevel` (e.g., `XlsxSaveOptions options = new XlsxSaveOptions(); options.setCompressionLevel(CompressionLevel.MAXIMUM);`). Pass this options object to `document.save`.

4. **Q:** Do I need a license to use the conversion features?  
   **A:** Not to use the feature. Without a license, Aspose.Words for Java works in evaluation mode with full functionality, but it adds an evaluation watermark and limits the document size to a few hundred paragraphs. To remove these limitations, apply a license: `License license = new License(); license.setLicense("Aspose.Words.Java.lic");`.