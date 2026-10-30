---
title: Working with Digital Signatures
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Digital Signatures
linktitle: Working with Digital Signatures
description: "Digitally sign documents and detect, count, verify, and remove existing digital signatures using Node.js."
type: docs
weight: 40
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-digital-signatures/
timestamp: 2025-07-09-10-05-05
---

A digital signature is used to authenticate a document to establish that the sender of the document is who they say they are and the content of the document has not been tampered with.

Aspose.Words supports documents with digital signatures and provides access to them allowing you to detect and validate digital signatures on a document and sign a generated PDF document with a supplied certificate. At the present time digital signatures are supported on DOC, OOXML and ODT documents. Signing of generated documents is supported in PDF format.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online signature](https://products.aspose.app/words/signature).

{{% /alert %}}

## Digital Signatures are not Preserved on Open and Save

An important point to note is that a document loaded and then saved using Aspose.Words will lose any digital signatures signed on the document. This is by design as a digital signature ensures that the content has not been modified and furthermore authenticates the identify of who signed the document. These principles would be invalidated if the original signatures were carried over to the resulting document.

Due to this, if you process documents uploaded to a server this could potentially mean you may corrupt a document uploaded to your server in this way without knowing. Therefore it is best to check for digital signatures on a document and take the appropriate action if any are found, for example an alert can be sent to the client informing them that the document they are passing contains digital signatures which will be lost if it is processed. You can download template file of this example from [here](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Digitally%20signed.docx).

{{< gist "aspose-words-gists" "246abc8bf535665565cc872be9b805ac" "detect-document-signatures.js" >}}

The code above uses the [FileFormatUtil.detectFileFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/detectFileFormat/) method to detect if a document contains digital signatures without loading the document first. This provides an efficient and safe way to check a document for signatures before processing them. When executed, the method returns a [FileFormatInfo](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatinfo/) object which provides the property [FileFormatInfo.hasDigitalSignature](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatinfo/hasdigitalsignature/). This property returns true if the document contains one or more digital signatures. It's important to note that this method does not validate the signatures, it only determines if signatures are present. Validating digital signatures is covered in the next section.

{{% alert color="primary" %}}

You can also check if a document has digital signatures after loading by checking the `Count` property of the [Document.digitalSignatures](https://reference.aspose.com/words/nodejs-net/aspose.words/document/digitalsignatures/) collection.

{{% /alert %}}

## Digital Signatures on Macros (VBA Projects)

Digital signatures on macros cannot be accessed or signed. This is because Aspose.Words does not directly deal with macros in a document. However digital signatures on macros are preserved when exporting the document back to any word format. These signatures can be preserved on VBA code because the binary content of the macros are not changed even if the document itself is modified.

### Access and Verify Digital Signatures

A document can have multiple digital signatures. These signatures can all be accessed through the [Document.digitalSignatures](https://reference.aspose.com/words/nodejs-net/aspose.words/document/digitalsignatures/) collection. Each object returned is a [DigitalSignature](https://reference.aspose.com/words/nodejs-net/aspose.words/digitalsignature/) which represents a single digital signature belonging to the document. This provides members that allow you to check the validity of the signature.

The most important property to check with digital signatures is the validity of each signature in the document. All signatures in the document can be validated at once by calling the [DigitalSignatureCollection.isValid](https://reference.aspose.com/words/nodejs-net/aspose.words.digitalsignatures/digitalsignaturecollection/isValid/) property. This will return true if all signatures in the document are valid or if the document has no signatures and false if at least one digital signature is not valid.

Each signature can also be individually validated by calling [DigitalSignature.isValid](https://reference.aspose.com/words/nodejs-net/aspose.words/digitalsignature/isValid/). A signature can return not valid for several reasons, for instance the document has been changed since signing or the certificate has expired. Additionally extra details of the signature can also be accessed.

The following code example shows how to validate each signature in a document and display basic information about the signature:

{{< gist "aspose-words-gists" "246abc8bf535665565cc872be9b805ac" "access-and-verify-signature.js" >}}

{{% alert color="primary" %}}

You can download template file of this example from [here](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Digitally%20signed.docx).

{{% /alert %}}

## Retrieve the Digital Signature Value

Aspose.Words also provides the ability to retrieve the digital signature value from a digitally signed document as a byte array using the [signatureValue](https://reference.aspose.com/words/nodejs-net/aspose.words/digitalsignature/signatureValue/) property.

The following code example shows how to obtain the digital signature value as a byte array from a document:

{{< gist "aspose-words-gists" "246abc8bf535665565cc872be9b805ac" "signature-value.js" >}}

## Remove Digital Signatures

Aspose.Words allows you to remove all digital signatures from a signed document using the [removeAllSignatures](https://reference.aspose.com/words/nodejs-net/aspose.words.digitalsignatures/digitalsignatureutil/removeallsignatures/#buffer_unknown/) method.

The following code example shows how to load and remove digital signatures from a document:

{{< gist "aspose-words-gists" "246abc8bf535665565cc872be9b805ac" "remove-signatures.js" >}}

{{% alert color="primary" %}}

Note that you can not remove only one digital signature within your document.

{{% /alert %}}

------  

## FAQ

1. **Q:** How can I detect whether a document contains digital signatures without loading the whole document?  
   **A:** Use `FileFormatUtil.detectFileFormat(filePath)` to obtain a `FileFormatInfo` object, then check its `hasDigitalSignature` property. This method reads only the file header, so it is fast and does not modify the document.

2. **Q:** After loading a document, how do I verify that all its digital signatures are valid?  
   **A:** Load the document with `new Document(filePath)`, then read `document.digitalSignatures.isValid`. The property returns `true` only if every signature in the collection is valid; otherwise it returns `false`.

3. **Q:** How can I retrieve the raw signature data from a digital signature?  
   **A:** Iterate through `document.digitalSignatures` and for each `DigitalSignature` use the `signatureValue` property. The property returns a `Uint8Array` (byte array) that contains the raw signature bytes.

4. **Q:** What is the correct way to remove digital signatures from a signed document?  
   **A:** Use `DigitalSignatureUtil.removeAllSignatures(srcFileName, dstFileName)`. This static method removes every signature from the source file and saves the result to the destination file; Aspose.Words does not support removing a single signature.

5. **Q:** Why are digital signatures lost when I open and then save a document with Aspose.Words?  
   **A:** Saving a document modifies its content, which invalidates any existing digital signatures. Aspose.Words intentionally discards signatures on save to preserve the integrity of the signing process. To avoid losing signatures, check for them first and avoid saving the document unless you intend to re‑sign it.