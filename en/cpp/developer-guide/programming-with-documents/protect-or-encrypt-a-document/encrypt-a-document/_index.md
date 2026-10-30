---
title: Encrypt a Document in C++
second_title: Aspose.Words for C++
articleTitle: Encrypt a Document
linktitle: Encrypt a Document
description: "Encrypt your document using appropriate encryption algorithms for specific document formats."
type: docs
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/encrypt-a-document/
timestamp: 2024-10-21-11-17-44
---

Encryption is the process that translates readable text to meaningless sequences of bytes so it can only be read by the person who has the decryption key or the secret code. This process plays an important role in securing your content. It helps to encode the content, verify the origin of a document, prove that the content has not been modified after it was sent, and ensure that the data from the document is safe.

This article explains how Aspose.Words allows you to encrypt a document and how to check if a document has encryption or not.

## Encrypt with Password

To encrypt a document, use the **Password** property to provide a password that functions as an encryption key. This will modify the content of your document and make it unreadable. The encrypted document will require to have this password entered before it can be opened.

{{% alert color="primary" %}}

You can find the appropriate **Password** property for the required format. Each document save format in the [Saving Namespace](https://reference.aspose.com/words/cpp/aspose.words.saving/) has a corresponding class containing save options for this format. For example, the [get_Password()](https://reference.aspose.com/words/cpp/aspose.words.saving/docsaveoptions/get_password/) property in the [DocSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/docsaveoptions/) class for DOC, or the [get_Password()](https://reference.aspose.com/words/cpp/aspose.words.saving/ooxmlsaveoptions/get_password/) property in the [OoxmlSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/ooxmlsaveoptions/) class for DOCX, DOCM, DOTX, DOTM, and FlatOpc.

{{% /alert %}}

{{% alert color="primary" %}}

Note that only certain document formats support encryption. For example, RTF does not support encryption.

{{% /alert %}}

The table below lists the formats and encryption algorithms supported by Aspose.Words:

| Format | Supported Encryption while Loading                    | Supported Encryption while Saving            |
| ------------------------------------------------------------ | ----------------------------------------------------------- | -------------------------------------------- |
| DOC, DOT                                                     | XOR encryption<br>40-bit RC4 Encryption<br>CryptoAPI RC4 Encryption | RC4 Encryption (40-bit)                      |
| DOCX, DOTX, DOCM, DOTM, FlatOPC, FlatOpcTemplate, FlatOpcMacroEnabled, FlatOpcTemplateMacroEnabled | ECMA-376 Standard Encryption<br>ECMA-376 Agile Encryption       | ECMA-376 Standard Encryption (AES128 + SHA1) |
| ODT, OTT                                                     | ODF Encryption (Blowfish/AES)                               | ODF Encryption (AES256 + SHA256)             |
| PDF                                                          | -                                                           | AES-128 / AES-256                            |

The following code example shows how to encrypt a document with a password:

{{< gist "aspose-words-gists" "b4e8a7baa7d3c08127f9a043487de21b" "encrypt-document-with-password.h" >}}

## Check If a Document Is Encrypted

In some cases, you may have an unreadable document and want to be sure that the document is encrypted and not corrupted or compressed.

To detect if a document is encrypted and if a password is required, you can use the [get_IsEncrypted()](https://reference.aspose.com/words/cpp/aspose.words/fileformatinfo/get_isencrypted/) property of the [FileFormatInfo](https://reference.aspose.com/words/cpp/aspose.words/fileformatinfo) class. This property will also allow you to perform some action before loading a document, for example, informing a user to provide a password.

The following code example shows how to detect the document encryption:

{{< gist "aspose-words-gists" "b4e8a7baa7d3c08127f9a043487de21b" "verify-encrypted-document.h" >}}

## Open a Document With or Without a Password

When we have made sure that a document is encrypted, we can try to open this document without a password, which should lead to an exception.

The following code example shows how to try opening an encrypted document without a password:

{{< gist "aspose-words-gists" "b4e8a7baa7d3c08127f9a043487de21b" "load-encrypted-document-without-password.h" >}}

After we have seen that an encrypted document cannot be opened without a password, we can try to open it by entering the password.

The following code example shows how to try opening an encrypted document with a password:

{{< gist "aspose-words-gists" "b4e8a7baa7d3c08127f9a043487de21b" "load-save-encrypted-document.h" >}}

------  

## FAQ

1. **Q:** Which file formats can be encrypted when saving with Aspose.Words for C++?  
   **A:** Encryption is supported for DOC, DOCX/DOTX/DOCM/DOTM, Flat OPC families, ODT/OTT, and PDF. Formats such as RTF do **not** support encryption.

2. **Q:** How can I choose a specific encryption algorithm for a DOCX file?  
   **A:** Aspose.Words for C++ does not let you choose the algorithm. Set a password with `OoxmlSaveOptions::set_Password` and the document is encrypted when saved. For example:  

   ```cpp
   auto saveOptions = System::MakeObject<Aspose::Words::Saving::OoxmlSaveOptions>();
   saveOptions->set_Password(u"MyPassword");
   doc->Save(u"encrypted.docx", saveOptions);
   ```

3. **Q:** How do I determine whether a document is encrypted before loading it?  
   **A:** Call `FileFormatUtil::DetectFileFormat` with the file path and check `FileFormatInfo::get_IsEncrypted()`. It returns `true` if the file is encrypted, allowing you to prompt the user for a password before attempting to load the document.

4. **Q:** What exception is thrown if I try to open an encrypted document without providing a password?  
   **A:** Aspose.Words throws `IncorrectPasswordException`. Catch this exception to inform the user that a password is required or to request the correct password.

5. **Q:** Can I encrypt a PDF document with Aspose.Words, and which algorithms are available?  
   **A:** Yes. Use `PdfSaveOptions::set_EncryptionDetails` with a `PdfEncryptionDetails` object that holds the user and owner passwords. The algorithm is chosen automatically: AES-128 for PDF 1.7 based compliance (including PDF/UA-1) and AES-256 for PDF 2.0 based compliance. Example:  

   ```cpp
   auto pdfOptions = System::MakeObject<Aspose::Words::Saving::PdfSaveOptions>();
   pdfOptions->set_EncryptionDetails(System::MakeObject<Aspose::Words::Saving::PdfEncryptionDetails>(u"PdfPass", u""));
   doc->Save(u"encrypted.pdf", pdfOptions);
   ```

These FAQs address the most common questions related to document encryption with Aspose.Words for C++.