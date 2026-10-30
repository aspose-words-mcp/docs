---
title: Work with Digital Signatures in Java
second_title: Aspose.Words for Java
articleTitle: Work with Digital Signatures
linktitle: Work with Digital Signatures
description: "Digitally sign documents and detect, count, verify, and remove existing digital signatures using Java."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-digital-signatures/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with digital signatures, including signing and verification.

{{% /alert %}}

A digital signature is a technological implementation of electronic signatures to sign documents and authenticate the signer to guarantee that a document has not been modified since it was signed. Each digital signature is unique for each signer because of following the PKI protocol to generate both public and private keys. Signing a document digitally means creating a signature using the signer's private key where a mathematical algorithm is used to encrypt the generated hash.

Aspose.Words allows you to detect, count, or verify existing digital signatures, and also add a new signature to your document to find out any tampering in it. You can also remove all digital signatures from a document. Use the [DigitalSignatureUtil](https://reference.aspose.com/words/java/com.aspose.words/digitalsignatureutil/) class to work with digital signatures.

This article explains how to do all of the above to validate the authenticity and integrity of a digital document.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online signature](https://products.aspose.app/words/signature).

{{% /alert %}}

## Supported Formats

Aspose.Words allows you to work with digital signatures on DOC, OOXML, and ODT documents and to sign the generated document in PDF or XPS format.

## Limitations of Digital Signatures

The table below describes a few limitations that you may face while working with digital signatures through Aspose.Words, as well as some alternative options.

| Limitation | Alternative Option                                           |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Loss of digital signatures on a document after loading and saving it. Therefore, processing a document to a server may cause the loss of all digital signatures without a notice. | Check if a document has digital signatures and take the appropriate action if any are found. For example, send an alert to the clients informing them that the document they are uploading contains digital signatures that will be lost if it is processed. |
| Aspose.Words supports working with macros in a document. But Aspose.Words does not yet support digital signatures on macros. | Export the document back to any Word format, and use Microsoft Word to add a digital signature to macros. |

## Detect, Count, and Verify Digital Signatures

Aspose.Words allows you to detect digital signature in a document using the [detectFileFormat()](https://reference.aspose.com/words/java/com.aspose.words/fileformatutil/#detectFileFormat-java.io.InputStream) method and the [hasDigitalSignature()](https://reference.aspose.com/words/java/com.aspose.words/fileformatinfo/#hasDigitalSignature) property. It is worth noting that such a check will only detect the fact of the signature, but not its validity.

A document can be signed more than once, and this can be done by different users. To check the validity of digital signatures, you need to load them from the document using the [loadSignatures()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignatureutil/#loadSignatures-java.io.InputStream) method and use the [isValid()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignaturecollection/#isValid) property. Also Aspose.Words allows you to count a set of all digital signatures within a document using the [getCount()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignaturecollection/#getCount) property.

All of this provides an efficient and safe way to check a document for signatures before processing it.

The following code example shows how to detect the presence of digital signatures and verify them:

{{< gist "aspose-words-gists" "39ea49b7754e472caf41179f8b5970a0" "detect-document-signatures.java" >}}

## Create a Digital Signature {#create-a-digital-signature}

To create a digital signature, you will require to load a signing certificate that confirms identity. When you send a digitally signed document, you also send your certificate and public key.

Aspose.Words allows you to create X.509 certificate, a digital certificate that uses the internationally accepted X.509 PKI standard to verify that a public key belongs to the signer included inside the certificate. To do this, use the [Create](https://reference.aspose.com/words/java/com.aspose.words/certificateholder/#create-byte---java.lang.String) method within the [CertificateHolder](https://reference.aspose.com/words/java/com.aspose.words/certificateholder/) class.

The next sections explain how to add a digital signature, signature line, and how to sign a generated PDF document.

### Sign a Document

Aspose.Words allows you to sign a DOC, DOCX, XPS, or ODT document digitally using the [sign()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignatureutil/#sign-java.io.InputStream-java.io.OutputStream-com.aspose.words.CertificateHolder) method and [SignOptions](https://reference.aspose.com/words/java/com.aspose.words/signoptions/) properties.

The following code example shows how to sign documents using a certificate holder and sign options:

{{< gist "aspose-words-gists" "39ea49b7754e472caf41179f8b5970a0" "sign-document.java" >}}

### Add a Signature Line

A signature line is a visual representation of a digital signature in a document. Aspose.Words allows you to insert a signature line using the [DocumentBuilder.insertSignatureLine](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertSignatureLine-com.aspose.words.SignatureLineOptions) method.  You can also set the parameters for this representation using the [SignatureLineOptions](https://reference.aspose.com/words/java/com.aspose.words/signaturelineoptions/) class.

For example, the picture below shows how valid and invalid signatures can be displayed.

<img src="valid.png" alt="drawing-java" style="width:300px"/>

<img src="invalid.png" alt="drawing-java" style="width:300px"/>

Also, if a document contains a signature line and no digital signature, there is a feature to ask the user to add a signature.

The following code example shows how to sign a document with a personal certificate and a specific signature line:

{{< gist "aspose-words-gists" "39ea49b7754e472caf41179f8b5970a0" "create-new-signature-line-and-set-provider-id.java" >}}

### Sign a Generated PDF Document {#sign-a-generated-pdf-document}

Aspose.Words allows you to sign and get all details of a PDF document using the [PdfDigitalSignatureDetails](https://reference.aspose.com/words/java/com.aspose.words/pdfdigitalsignaturedetails/) properties.

The following code example shows how to sign a generated PDF:

{{< gist "aspose-words-gists" "39ea49b7754e472caf41179f8b5970a0" "digitally-signed-pdf-using-certificate-holder.java" >}}

## Retrieve the Digital Signature Value

Aspose.Words also provides the ability to retrieve the digital signature value from a digitally signed document as a byte array using the [getSignatureValue()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignature/#getSignatureValue) property.

The following code example shows how to obtain the digital signature value as a byte array from a document:

{{< gist "aspose-words-gists" "39ea49b7754e472caf41179f8b5970a0" "signature-value.java" >}}

## Remove Digital Signatures

Aspose.Words allows you to remove all digital signatures from a signed document using the [removeAllSignatures()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignatureutil/#removeAllSignatures-java.io.InputStream-java.io.OutputStream) method.

The following code example shows how to load and remove digital signatures from a document:

{{< gist "aspose-words-gists" "39ea49b7754e472caf41179f8b5970a0" "remove-signatures.java" >}}

{{% alert color="primary" %}}

Note that you can not remove only one digital signature within your document.

{{% /alert %}}

## Related APIs

- [DigitalSignatureUtil](https://reference.aspose.com/words/java/com.aspose.words/digitalsignatureutil/)
- [DigitalSignatureCollection](https://reference.aspose.com/words/java/com.aspose.words/digitalsignaturecollection/)
- [DigitalSignature](https://reference.aspose.com/words/java/com.aspose.words/digitalsignature/)
- [CertificateHolder](https://reference.aspose.com/words/java/com.aspose.words/certificateholder/)
- [SignOptions](https://reference.aspose.com/words/java/com.aspose.words/signoptions/)
- [SignatureLineOptions](https://reference.aspose.com/words/java/com.aspose.words/signaturelineoptions/)
- [FileFormatUtil.detectFileFormat](https://reference.aspose.com/words/java/com.aspose.words/fileformatutil/#detectFileFormat-java.io.InputStream)
- [FileFormatInfo.hasDigitalSignature](https://reference.aspose.com/words/java/com.aspose.words/fileformatinfo/#hasDigitalSignature)
- [DocumentBuilder.insertSignatureLine](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertSignatureLine-com.aspose.words.SignatureLineOptions)
- [PdfDigitalSignatureDetails](https://reference.aspose.com/words/java/com.aspose.words/pdfdigitalsignaturedetails/)
- [DigitalSignature.getSignatureValue()](https://reference.aspose.com/words/java/com.aspose.words/digitalsignature/#getSignatureValue)

## FAQ

1. **Q:** Do I need a licensed copy of Aspose.Words to use digital signature features?  
   **A:** Not to use the feature. Without a license, Aspose.Words for Java works in evaluation mode with full functionality, but it adds an evaluation watermark and limits the document size to a few hundred paragraphs. To remove these limitations, apply a license: `License license = new License(); license.setLicense("Aspose.Words.Java.lic");`.

2. **Q:** Can I remove a single digital signature from a document?  
   **A:** No. Aspose.Words can only remove all signatures at once using `removeAllSignatures()`. Individual signature removal is not supported.

3. **Q:** Is it possible to sign a PDF that was generated from a Word document?  
   **A:** Yes, when you save the document to PDF: set `PdfSaveOptions.setDigitalSignatureDetails(new PdfDigitalSignatureDetails(certificateHolder, reason, location, signatureDate))`. `DigitalSignatureUtil.sign` does not sign PDF files; it supports DOC, DOT, DOCX, DOTX, DOCM, DOTM, ODT, and OTT.