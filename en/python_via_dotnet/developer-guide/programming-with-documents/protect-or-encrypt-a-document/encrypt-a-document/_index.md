---
title: Encrypt a Document in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Encrypt a Document
linktitle: Encrypt a Document
description: "Encrypt your document using appropriate encryption algorithms for specific document formats in Python."
type: docs
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/encrypt-a-document/
aliases: [/python/encrypt-a-document/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to encrypt documents using Aspose.Words for Python via .NET, how to detect whether a document is encrypted, and how to open encrypted files with or without a password, including details on supported formats and encryption options.

{{% /alert %}}

Encryption is the process that translates readable text to meaningless sequences of bytes so it can only be read by the person who has the decryption key or the secret code. This process plays an important role in securing your content. It helps to encode the content, verify the origin of a document, prove that the content has not been modified after it was sent, and ensure that the data from the document is safe.

This article explains how Aspose.Words allows you to encrypt a document and how to check if a document has encryption or not.

## Encrypt with Password

To encrypt a document, use the **password** property to provide a password that functions as an encryption key. This will modify the content of your document and make it unreadable. The encrypted document will require to have this password entered before it can be opened.

{{% alert color="primary" %}}

You can find the appropriate **Password** property for the required format. Each document save format in the [aspose.words.saving](https://reference.aspose.com/words/python-net/aspose.words.saving/) has a corresponding class containing save options for this format. For example, the [password](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/password/) property in the [DocSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/) class for DOC, or the [password](https://reference.aspose.com/words/python-net/aspose.words.saving/ooxmlsaveoptions/password/) property in the [OoxmlSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/ooxmlsaveoptions/) class for DOCX, DOCM, DOTX, DOTM, and FlatOpc.

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

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "encrypt-document-with-password.py" >}}

## Check If a Document Is Encrypted

In some cases, you may have an unreadable document and want to be sure that the document is encrypted and not corrupted or compressed.

To detect if a document is encrypted and if a password is required, you can use the [is_encrypted](https://reference.aspose.com/words/python-net/aspose.words/fileformatinfo/is_encrypted/) property of the [FileFormatInfo](https://reference.aspose.com/words/python-net/aspose.words/fileformatinfo/) class. This property will also allow you to perform some action before loading a document, for example, informing a user to provide a password.

The following code example shows how to detect the document encryption:

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "verify-encrypted-document.py" >}}

## Open a Document With or Without a Password

When we have made sure that a document is encrypted, we can try to open this document without a password, which should lead to an exception.

The following code example shows how to try opening an encrypted document without a password:

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "load-encrypted-document-without-password.py" >}}

After we have seen that an encrypted document cannot be opened without a password, we can try to open it by entering the password.

The following code example shows how to try opening an encrypted document with a password:

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "load-save-encrypted-document.py" >}}

## Limitations and Considerations

This section covers specific constraints and important considerations for document encryption using Aspose.Words:

- **Encryption algorithm selection**: Aspose.Words does not expose a direct property to choose the encryption algorithm. The algorithm used depends on the output format and save options:
  - For DOC: RC4 40-bit.
  - For DOCX/DOTX/DOCM/DOTM/FlatOPC: ECMA-376 Standard Encryption using AES128 + SHA1.
  - For ODT/OTT: ODF Encryption using AES256 + SHA256.
  - For PDF: AES-128 (PDF 1.7 based compliance) or AES-256 (PDF 2.0 based compliance), set with `PdfSaveOptions.encryption_details`.

- **Password policies are not enforced**: Aspose.Words does not validate or enforce password strength or complexity. It is the application developer’s responsibility to enforce appropriate password policies if required.

- **Encryption header compatibility**: While Aspose.Words supports decrypting documents created by other tools (e.g., Microsoft Word) if the correct password is known, encryption compatibility is guaranteed only for documents created with Aspose.Words. interoperability with third-party implementations may vary.

- **No encryption support for all formats**: Not all document formats support encryption. Examples of unsupported formats include RTF, HTML, MHTML, and image formats.

- **Password protection applies only to saving**: Setting a password in save options does not protect an already-loaded document from being modified or saved again without encryption. Each `save` call must explicitly include encrypted save options to ensure protection.

- **No support for multiple encryption layers**: Aspose.Words does not support applying multiple encryption layers to the same document. Over-encryption (e.g., encrypting an already encrypted document) requires re-saving with a new password and will use the algorithm defined for the output format.

- **Loading encrypted documents with invalid password**: When loading an encrypted document using `Document` constructor with an incorrect password, Aspose.Words throws an `IncorrectPasswordException`. Applications should handle this exception to provide appropriate user feedback.

- **FlatOpc variants**: FlatOpc, FlatOpcTemplate, FlatOpcMacroEnabled, and FlatOpcTemplateMacroEnabled formats use the same encryption mechanism as DOCX (ECMA-376 Standard), but they are not editable in all word processors without conversion to the native DOCX structure.

## Related APIs

- [DocSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/) — Save options for DOC/DOT formats, includes [password](https://reference.aspose.com/words/python-net/aspose.words.saving/docsaveoptions/password/) property.
- [OoxmlSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/ooxmlsaveoptions/) — Save options for DOCX, DOTX, DOCM, DOTM, and FlatOpc formats, includes [password](https://reference.aspose.com/words/python-net/aspose.words.saving/ooxmlsaveoptions/password/) property.
- [FileFormatInfo](https://reference.aspose.com/words/python-net/aspose.words/fileformatinfo/) — Contains [is_encrypted](https://reference.aspose.com/words/python-net/aspose.words/fileformatinfo/is_encrypted/) property to detect encryption.
- [IncorrectPasswordException](https://reference.aspose.com/words/python-net/aspose.words/incorrectpasswordexception/) — Exception thrown when an incorrect password is provided for an encrypted document. 

## FAQ

1. **Q:** How can I encrypt a Word document using Aspose.Words for Python?  
   **A:** Choose the SaveOptions class that matches the target format (e.g., `DocSaveOptions` for DOC, `OoxmlSaveOptions` for DOCX), set its `password` property to the desired password, and then save the document with those options.

2. **Q:** Which file formats support encryption when saving with Aspose.Words?  
   **A:** DOC, DOCX, DOCM, DOTX, DOTM, FlatOpc, ODT, OTT, and PDF support encryption. Formats such as RTF do **not** support encryption.

3. **Q:** How can I determine whether a document is encrypted before loading it?  
   **A:** Use `aw.FileFormatUtil.detect_file_format(path)` to obtain a `FileFormatInfo` object and check its `is_encrypted` property. This lets you prompt the user for a password only when necessary.

4. **Q:** How do I open an encrypted document programmatically?  
   **A:** Create a `LoadOptions` object with the password (`aw.loading.LoadOptions("MyPassword")`) and pass it to the `Document` constructor: `doc = aw.Document(path, load_options)`.

5. **Q:** What happens if I try to open an encrypted document without providing a password?  
   **A:** Aspose.Words throws an `IncorrectPasswordException` (in Python, a `RuntimeError` whose message starts with `Proxy error(IncorrectPasswordException)`). Catch this exception to inform the user that a password is required, or supply the correct password via `LoadOptions`.