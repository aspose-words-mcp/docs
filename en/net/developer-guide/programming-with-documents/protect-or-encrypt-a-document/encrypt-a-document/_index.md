---
title: Encrypt a Document in C#
second_title: Aspose.Words for .NET
articleTitle: Encrypt a Document
linktitle: Encrypt a Document
description: "Encrypt your document using appropriate encryption algorithms for specific document formats in C#."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/encrypt-a-document/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to encrypt Word documents using passwords and various encryption algorithms.

{{% /alert %}}

Encryption is the process that translates readable text to meaningless sequences of bytes so it can only be read by the person who has the decryption key or the secret code. This process plays an important role in securing your content. It helps to encode the content, verify the origin of a document, prove that the content has not been modified after it was sent, and ensure that the data from the document is safe.

This article explains how Aspose.Words allows you to encrypt a document and how to check if a document has encryption or not.

## Encrypt with Password

To encrypt a document, use the **Password** property to provide a password that functions as an encryption key. This will modify the content of your document and make it unreadable. The encrypted document will require to have this password entered before it can be opened.

{{% alert color="primary" %}}

You can find the appropriate **Password** property for the required format. Each document save format in the [Saving Namespace](https://reference.aspose.com/words/net/aspose.words.saving/) has a corresponding class containing save options for this format. For example, the [Password](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/password/) property in the [DocSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/) class for DOC, or the [Password](https://reference.aspose.com/words/net/aspose.words.saving/ooxmlsaveoptions/password/) property in the [OoxmlSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/ooxmlsaveoptions/) class for DOCX, DOCM, DOTX, DOTM, and FlatOpc.

{{% /alert %}}

{{% alert color="primary" %}}

Note that only certain document formats support encryption. For example, RTF does not support encryption.

{{% /alert %}}

The table below lists the formats and encryption algorithms supported by Aspose.Words:

| Format | Supported Encryption while Loading                          | Supported Encryption while Saving            |
| ------------------------------------------------------------ | ----------------------------------------------------------- | -------------------------------------------- |
| DOC, DOT                                                     | XOR encryption<br>40-bit RC4 Encryption<br>CryptoAPI RC4 Encryption | RC4 Encryption (40-bit)                      |
| DOCX, DOTX, DOCM, DOTM, FlatOPC, FlatOpcTemplate, FlatOpcMacroEnabled, FlatOpcTemplateMacroEnabled | ECMA-376 Standard Encryption<br>ECMA-376 Agile Encryption       | ECMA-376 Standard Encryption (AES128 + SHA1) |
| ODT, OTT                                                     | ODF Encryption (Blowfish/AES)                               | ODF Encryption (AES256 + SHA256)             |
| PDF | -                                                           | AES-128 / AES-256                            |

The following code example shows how to encrypt a document with a password:

{{< gist "aspose-words-gists" "af95c7a408187bb25cf9137465fe5ce6" "encrypt-document-with-password.cs" >}}

## Check If a Document Is Encrypted

In some cases, you may have an unreadable document and want to be sure that the document is encrypted and not corrupted or compressed.

To detect if a document is encrypted and if a password is required, you can use the [IsEncrypted](https://reference.aspose.com/words/net/aspose.words/fileformatinfo/isencrypted/) property of the [FileFormatInfo](https://reference.aspose.com/words/net/aspose.words/fileformatinfo/) class. This property will also allow you to perform some action before loading a document, for example, informing a user to provide a password.

The following code example shows how to detect the document encryption:

{{< gist "aspose-words-gists" "af95c7a408187bb25cf9137465fe5ce6" "verify-encrypted-document.cs" >}}

## Open a Document With or Without a Password

When we have made sure that a document is encrypted, we can try to open this document without a password, which should lead to an exception.

The following code example shows how to try opening an encrypted document without a password:

{{< gist "aspose-words-gists" "af95c7a408187bb25cf9137465fe5ce6" "load-encrypted-document-without-password.cs" >}}

After we have seen that an encrypted document cannot be opened without a password, we can try to open it by entering the password.

The following code example shows how to try opening an encrypted document with a password:

{{< gist "aspose-words-gists" "af95c7a408187bb25cf9137465fe5ce6" "load-save-encrypted-document.cs" >}}

## Limitations and Considerations

This section covers specific constraints and important considerations for document encryption using Aspose.Words:

- **Encryption algorithm selection**: Aspose.Words does not expose a direct property to choose the encryption algorithm. The algorithm used depends on the output format and save options:
  - For DOC: RC4 40-bit.
  - For DOCX/DOTX/DOCM/DOTM/FlatOPC: ECMA-376 Standard Encryption using AES128 + SHA1.
  - For ODT/OTT: ODF Encryption using AES256 + SHA256.
  - For PDF: AES-128 (PDF 1.7 based compliance) or AES-256 (PDF 2.0 based compliance), set with `PdfSaveOptions.EncryptionDetails`.

- **Password policies are not enforced**: Aspose.Words does not validate or enforce password strength or complexity. It is the application developer's responsibility to enforce appropriate password policies if required.

- **Encryption header compatibility**: While Aspose.Words supports decrypting documents created by other tools (e.g., Microsoft Word) if the correct password is known, encryption compatibility is guaranteed only for documents created with Aspose.Words. interoperability with third-party implementations may vary.

- **No encryption support for all formats**: Not all document formats support encryption. Examples of unsupported formats include RTF, HTML, MHTML, and image formats.

- **Password protection applies only to saving**: Setting a password in save options does not protect an already-loaded document from being modified or saved again without encryption. Each `Save` call must explicitly include encrypted save options to ensure protection.

- **No support for multiple encryption layers**: Aspose.Words does not support applying multiple encryption layers to the same document. Over-encryption (e.g., encrypting an already encrypted document) requires re-saving with a new password and will use the algorithm defined for the output format.

- **Loading encrypted documents with invalid password**: When loading an encrypted document using `Document` constructor with an incorrect password, Aspose.Words throws an `IncorrectPasswordException`. Applications should handle this exception to provide appropriate user feedback.

- **FlatOpc variants**: FlatOpc, FlatOpcTemplate, FlatOpcMacroEnabled, and FlatOpcTemplateMacroEnabled formats use the same encryption mechanism as DOCX (ECMA-376 Standard), but they are not editable in all word processors without conversion to the native DOCX structure.

## Related APIs

- [DocSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/) — Save options for DOC/DOT formats, includes [Password](https://reference.aspose.com/words/net/aspose.words.saving/docsaveoptions/password/) property.
- [OoxmlSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/ooxmlsaveoptions/) — Save options for DOCX, DOTX, DOCM, DOTM, and FlatOpc formats, includes [Password](https://reference.aspose.com/words/net/aspose.words.saving/ooxmlsaveoptions/password/) property.
- [FileFormatInfo](https://reference.aspose.com/words/net/aspose.words/fileformatinfo/) — Contains [IsEncrypted](https://reference.aspose.com/words/net/aspose.words/fileformatinfo/isencrypted/) property to detect encryption.
- [IncorrectPasswordException](https://reference.aspose.com/words/net/aspose.words/incorrectpasswordexception/) — Exception thrown when an incorrect password is provided for an encrypted document.

------

## FAQ

1. **Q:** How do I encrypt a Word document with a password in C#?  
   **A:** Create the appropriate save options object for the target format (e.g., `DocSaveOptions` for DOC or `OoxmlSaveOptions` for DOCX) and set its `Password` property. Then call `Document.Save` with those options. The document will be saved encrypted and will require the password to open.

2. **Q:** Which file formats support encryption when saving with Aspose.Words?  
   **A:** Encryption is supported for DOC/DOT (RC4 40‑bit), DOCX/DOTX/DOCM/DOTM/FlatOPC families (ECMA‑376 AES‑128 + SHA‑1), ODT/OTT (AES‑256 + SHA‑256), and PDF (AES‑128 or AES‑256, depending on the PDF version). Formats such as RTF do not support encryption.

3. **Q:** How can I determine whether a document is encrypted before loading it?  
   **A:** Call `FileFormatUtil.DetectFileFormat` with a file path or stream and check the `IsEncrypted` property of the returned `FileFormatInfo`. This lets you prompt the user for a password only when necessary.

4. **Q:** What happens if I try to open an encrypted document without providing a password?  
   **A:** Aspose.Words throws an `IncorrectPasswordException`. Catch this exception, inform the user that a password is required, and optionally request the password to retry loading the document.

5. **Q:** Can I change the encryption algorithm of an already encrypted document?  
   **A:** No. The algorithm is determined by the output format (see the Limitations section above). You can change the password: load the document using the existing password, then save it again with new save options that specify a different `Password`. This re‑encrypts the document using the new settings.