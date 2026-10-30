---
title: How to Create BarCode using C#
second_title: Aspose.Words for .NET
articleTitle: Generate a Custom BarCode Image
linktitle: Generate a Custom BarCode Image
description: "Example of barcode shape generation using C#."
type: docs
weight: 350
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/how-to-generate-a-custom-barcode-image-for-displaybarcode-field/
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

Aspose.Words supports various types of barcodes. The barcode type is passed as a string value in the [BarcodeType](https://reference.aspose.com/words/net/aspose.words.fields/barcodeparameters/barcodetype/) property.

{{% alert color="primary" %}}

Since working with barcodes within the functionality of Aspose.Words is limited, the user can use any library, including Aspose.Barcode, or write his own rendering to work with barcodes. You can learn more about the types of barcodes [supported by Aspose.BarCode](https://docs.aspose.com/barcode/net/barcode-types/).

{{% /alert %}}

When saving to Word formats that support barcodes, you can use any type of barcode that is [supported by Microsoft Word](https://support.microsoft.com/en-us/word/field-codes-displaybarcode). If an incorrect type of barcode was passed, Word will display an error.

When saving to other formats, such as PDF, Aspose.Words delegates barcode rendering to the user code, so the user is limited to the barcode types of their implementation or library used.

## Insert a Barcode into a Document or Load a Document with an Added Barcode

Aspose.Words provides the ability to:

1. Programmatically insert a barcode into a document using the [DisplayBarcode](https://support.microsoft.com/en-au/word/field-codes-displaybarcode) and [MergeBarcode](https://support.microsoft.com/en-au/word/field-codes-mergebarcode) field codes
2. Or load a Word document with barcodes already inserted into it for further work

Aspose.Words has an interface for generating custom barcodes that makes it easy to use [Aspose.Words](https://products.aspose.com/words/net/) and [Aspose.BarCode](https://products.aspose.com/barcode/net/) together to render barcode images in output documents. For example, you can create a DOC, OOXML, or RTF document and add DISPLAYBARCODE field to it using Aspose.Words. Or you can load a DOC, OOXML or RTF document with DISPLAYBARCODE field already existing in it and provide your implementation of custom barcode generator.

A typical DISPLAYBARCODE field has the following syntax:

`{ DISPLAYBARCODE "SomeData" QR \h 720 }`

Below is an example code generator using the Aspose.Words and Aspose.BarCode APIs. This example shows how to insert barcode images at DISPLAYBARCODE field position in a Word document:

{{< gist "aspose-words-gists" "00d34dba66626dbc0175b60bb3b71c8a" "barcode-generator.cs" >}}

{{< gist "aspose-words-gists" "00d34dba66626dbc0175b60bb3b71c8a" "custom-barcode-generator.cs" >}}

You can also save the document with the loaded or newly inserted barcode in fixed page formats such as PDF, XPS, etc. The following code example shows how to save a Word document to PDF format:

{{< gist "aspose-words-gists" "a53bdaad548845275c1b9556ee21ae65" "docx-to-pdf.cs" >}}

{{% alert color="primary" %}}

For more information about converting documents from one format to another, see  the [Convert a Document](/words/net/convert-a-document/) documentation section.

{{% /alert %}}

{{% alert color="primary" %}}

You can also use the [IBarcodeGenerator](https://reference.aspose.com/words/net/aspose.words.fields/ibarcodegenerator/) interface to convert barcodes embedded in Word documents into images. The resulting images can be extracted from the document – see the Working with Images article for details.

{{% /alert %}}

## Specify Barcode Options

When working with barcodes, you can set some additional properties. Aspose.Words provides you with the [BarcodeParameters](https://reference.aspose.com/words/net/aspose.words.fields/barcodeparameters/) class for barcode parameters to pass-through to BarcodeGenerator.

Aspose.Words supports embedded 96 ppi resolution for images generated with [IBarcodeGenerator](https://reference.aspose.com/words/net/aspose.words.fields/ibarcodegenerator/), which limits the minimum size of a barcode image. To address this, developers can manually insert barcode images with the target resolution into a Word document and save them in the required format. For more details and examples on working with barcodes, see the article [Create Custom Barcodes with IBarcodeGenerator](https://docs.aspose.com/barcode/net/how-to-create-custom-barcodes-with-ibarcodegenerator/).

## Limitations and Considerations

- Barcode images returned by your [IBarcodeGenerator](https://reference.aspose.com/words/net/aspose.words.fields/ibarcodegenerator/) implementation are rendered at a fixed 96 ppi resolution, which limits the minimum achievable barcode size.
- Microsoft Word only supports specific barcode types. If an unsupported type is specified via `BarcodeParameters.BarcodeType`, Word will display an error and Aspose.Words will not generate an image.
- When saving to non-Word formats (e.g., PDF, XPS), Aspose.Words does not perform barcode rendering by default. You must either provide a custom `IBarcodeGenerator` implementation or use an external library such as Aspose.Barcode to render barcodes before saving.
- The `DisplayBarcode` and `MergeBarcode` field codes are the only supported methods for inserting barcodes programmatically. Legacy barcode fields from older Word versions may not be fully supported.
- Barcode rendering via `IBarcodeGenerator` is available only when saving to fixed-page formats. For editable Word documents, the barcode remains as a field and rendering occurs in Word.
- Custom `IBarcodeGenerator` implementations must handle all aspects of barcode generation, including resolution, size, and format conversion, since Aspose.Words does not modify the provided image data.

## Related APIs


- [FieldDisplayBarcode](https://reference.aspose.com/words/net/aspose.words.fields/fielddisplaybarcode/)
- [FieldMergeBarcode](https://reference.aspose.com/words/net/aspose.words.fields/fieldmergebarcode/)
- [BarcodeParameters](https://reference.aspose.com/words/net/aspose.words.fields/barcodeparameters/)
- [IBarcodeGenerator](https://reference.aspose.com/words/net/aspose.words.fields/ibarcodegenerator/)

## FAQ

1. **Q:** Which barcode types are supported by the `DISPLAYBARCODE` field?  
   **A:** Any barcode type that Microsoft Word recognises (e.g., QR, CODE128, EAN13) can be used. When using Aspose.BarCode you can also use all types listed in the Aspose.BarCode documentation; specify the type via `BarcodeParameters.BarcodeType`.

2. **Q:** What happens if I specify an unsupported barcode type?  
   **A:** Word will display an error message in the field, and Aspose.Words will not generate an image. Ensure the type string matches a supported value or provide a custom `IBarcodeGenerator` that can handle the requested type.

3. **Q:** Can I control the resolution of the generated barcode images?  
   **A:** Barcode images from an `IBarcodeGenerator` implementation are rendered at 96 ppi. For higher‑resolution barcodes, generate the image yourself (e.g., with Aspose.BarCode) at the desired DPI, insert the image into the document with `DocumentBuilder.InsertImage`, and then remove the original `DISPLAYBARCODE` field if needed.