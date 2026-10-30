---
title: How to Create BarCode using Java
second_title: Aspose.Words for Java
articleTitle: Generate a Custom BarCode Image
linktitle: Generate a Custom BarCode Image
description: "Example of barcode shape generation using Java."
type: docs
weight: 350
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/how-to-generate-a-custom-barcode-image-for-displaybarcode-field/
timestamp: 2024-09-05-11-07-10
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to generate custom barcode images for DISPLAYBARCODE fields.

{{% /alert %}}

A barcode is a visual representation of data in the form of parallel lines or patterns. Barcodes are widely used in various industries such as retail, logistics, healthcare, banking, and many others.

Microsoft Word allows users to embed barcodes directly into documents using fields. Users can insert a specific type of barcode, such as a QR code or a linear barcode, using the [BARCODE](https://learn.microsoft.com/en-us/openspecs/office_standards/ms-oi29500/cbc893c0-9683-416d-84c6-407a92451c19) field.

In this article, we will look at how the BARCODE field is implemented in Aspose.Words and how Aspose.Words allows users to work with Word documents to which a barcode has already been added.

## Barcode Types Supported by Aspose.Words

Aspose.Words supports various types of barcodes. The barcode type is passed as a string value in the [getBarcodeType()](https://reference.aspose.com/words/java/com.aspose.words/barcodeparameters/#getBarcodeType) property.

{{% alert color="primary" %}}

Since working with barcodes within the functionality of Aspose.Words is limited, the user can use any library, including Aspose.Barcode, or write his own rendering to work with barcodes. You can learn more about the types of barcodes [supported by Aspose.BarCode](https://docs.aspose.com/barcode/java/barcode-types/).

{{% /alert %}}

When saving to Word formats that support barcodes, you can use any type of barcode that is [supported by Microsoft Word](https://support.microsoft.com/en-us/word/field-codes-displaybarcode). If an incorrect type of barcode was passed, Word will display an error.

When saving to other formats, such as PDF, Aspose.Words delegates barcode rendering to the user code, so the user is limited to the barcode types of their implementation or library used.

## Insert a Barcode into a Document or Load a Document with an Added Barcode

Aspose.Words provides the ability to:

1. Programmatically insert a barcode into a document using the [DisplayBarcode](https://support.microsoft.com/en-au/word/field-codes-displaybarcode) and [MergeBarcode](https://support.microsoft.com/en-au/word/field-codes-mergebarcode) field codes
2. Or load a Word document with barcodes already inserted into it for further work

Aspose.Words has an interface for generating custom barcodes that makes it easy to use [Aspose.Words](https://products.aspose.com/words/java/) and [Aspose.BarCode](https://products.aspose.com/barcode/java/) together to render barcode images in output documents. For example, you can create a DOC, OOXML, or RTF document and add DISPLAYBARCODE field to it using Aspose.Words. Or you can load a DOC, OOXML or RTF document with DISPLAYBARCODE field already existing in it and provide your implementation of custom barcode generator.

A typical DISPLAYBARCODE field has the following syntax:

`{ DISPLAYBARCODE "SomeData" QR \h 720 }`

Below is an example code generator using the Aspose.Words and Aspose.BarCode APIs. This example shows how to insert barcode images at DISPLAYBARCODE field position in a Word document:

{{< gist "aspose-words-gists" "689e63b98de2dcbb12dffc37afbe9067" "barcode-generator.java" >}}

{{< gist "aspose-words-gists" "689e63b98de2dcbb12dffc37afbe9067" "custom-barcode-generator.java" >}}

You can also save the document with the loaded or newly inserted barcode in fixed page formats such as PDF, XPS, etc. The following code example shows how to save a Word document to PDF format:

{{< gist "aspose-words-gists" "b237846932dfcde42358bd0c887661a5" "docx-to-pdf.java" >}}

{{% alert color="primary" %}}

For more information about converting documents from one format to another, see  the [Convert a Document](/words/java/convert-a-document/) documentation section.

{{% /alert %}}

{{% alert color="primary" %}}

You can also use the [IBarcodeGenerator](https://reference.aspose.com/words/java/com.aspose.words/ibarcodegenerator/) interface to convert barcodes embedded in Word documents into images. The resulting images can be extracted from the document – see the Working with Images article for details.

{{% /alert %}}

## Specify Barcode Options

When working with barcodes, you can set some additional properties. Aspose.Words provides you with the [BarcodeParameters](https://reference.aspose.com/words/java/com.aspose.words/barcodeparameters/) class for barcode parameters to pass-through to BarcodeGenerator.

Aspose.Words supports embedded 96 ppi resolution for images generated with [IBarcodeGenerator](https://reference.aspose.com/words/java/com.aspose.words/ibarcodegenerator/), which limits the minimum size of a barcode image. To address this, developers can manually insert barcode images with the target resolution into a Word document and save them in the required format. For more details and examples on working with barcodes, see the article [Create Custom Barcodes with IBarcodeGenerator](https://docs.aspose.com/barcode/net/how-to-create-custom-barcodes-with-ibarcodegenerator/).

## Limitations and Considerations

- Barcode images returned by your [IBarcodeGenerator](https://reference.aspose.com/words/java/com.aspose.words/ibarcodegenerator/) implementation are rendered at a fixed 96 ppi resolution, which limits the minimum achievable barcode size.
- Microsoft Word only supports specific barcode types. If an unsupported type is specified via `BarcodeParameters.getBarcodeType()`, Word will display an error and Aspose.Words will not generate an image.
- When saving to non-Word formats (e.g., PDF, XPS), Aspose.Words does not perform barcode rendering by default. You must either provide a custom `IBarcodeGenerator` implementation or use an external library such as Aspose.Barcode to render barcodes before saving.
- The `DisplayBarcode` and `MergeBarcode` field codes are the only supported methods for inserting barcodes programmatically. Legacy barcode fields from older Word versions may not be fully supported.
- Barcode rendering via `IBarcodeGenerator` is available only when saving to fixed-page formats. For editable Word documents, the barcode remains as a field and rendering occurs in Word.
- Custom `IBarcodeGenerator` implementations must handle all aspects of barcode generation, including resolution, size, and format conversion, since Aspose.Words does not modify the provided image data.

## Related APIs

- [FieldDisplayBarcode](https://reference.aspose.com/words/java/com.aspose.words/fielddisplaybarcode/)
- [FieldMergeBarcode](https://reference.aspose.com/words/java/com.aspose.words/fieldmergebarcode/)
- [BarcodeParameters](https://reference.aspose.com/words/java/com.aspose.words/barcodeparameters/)
- [IBarcodeGenerator](https://reference.aspose.com/words/java/com.aspose.words/ibarcodegenerator/) 

## FAQ

1. **Q:** How can I programmatically insert a `DISPLAYBARCODE` field into a Word document?  
   **A:** Create a `DocumentBuilder` and call `insertField` with the field code (without braces), e.g.  
   ```java
   Document doc = new Document();
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.insertField("DISPLAYBARCODE \"1234567890\" CODE128");
   ```  
   To render the barcode when the document is saved, assign your `IBarcodeGenerator` implementation with `doc.getFieldOptions().setBarcodeGenerator(...)`.

2. **Q:** What is the purpose of the `IBarcodeGenerator` interface?  
   **A:** `IBarcodeGenerator` lets you supply your own barcode rendering logic. Implement the `getBarcodeImage(BarcodeParameters parameters)` method to return a `java.awt.image.BufferedImage`. Aspose.Words calls this method for each `DISPLAYBARCODE` field when saving to formats that do not support native barcode rendering (e.g., PDF).

3. **Q:** Which barcode types are supported by Aspose.Words out‑of‑the‑box?  
   **A:** The `BarcodeParameters.getBarcodeType()` property accepts any barcode type that Microsoft Word recognises (QR, CODE128, EAN13, etc.). If you need additional types, use Aspose.BarCode or another library inside your `IBarcodeGenerator` implementation.

4. **Q:** How can I control the resolution or size of the generated barcode image?  
   **A:** `BarcodeParameters` has no resolution setting: images returned by an `IBarcodeGenerator` implementation are rendered at 96 ppi. You can set the barcode height with the `\h` switch (in twips) and scale it with the `\s` switch (in percent), e.g., `{ DISPLAYBARCODE "Data" QR \h 720 \s 100 }`. Your generator receives these values in `BarcodeParameters.getSymbolHeight()` and `getScalingFactor()`.

5. **Q:** Do I need a license to use barcode generation with Aspose.Words for Java?  
   **A:** Not to use the feature. Without a license, Aspose.Words for Java works in evaluation mode with full functionality, but it adds an evaluation watermark and limits the document size to a few hundred paragraphs. To remove these limitations, apply a license: `License license = new License(); license.setLicense("Aspose.Words.Java.lic");`.