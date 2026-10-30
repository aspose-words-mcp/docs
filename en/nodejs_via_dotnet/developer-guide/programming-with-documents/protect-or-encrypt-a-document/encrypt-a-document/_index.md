---
title: Encrypt a Document in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Encrypt a Document
linktitle: Encrypt a Document
description: "Encrypt your document using appropriate encryption algorithms for specific document formats in Node.js."
type: docs
weight: 20
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/encrypt-a-document/
timestamp: 2024-10-21-11-17-44
---

Encryption is the process that translates readable text to meaningless sequences of bytes so it can only be read by the person who has the decryption key or the secret code. This process plays an important role in securing your content. It helps to encode the content, verify the origin of a document, prove that the content has not been modified after it was sent, and ensure that the data from the document is safe.

This article explains how Aspose.Words allows you to encrypt a document and how to check if a document has encryption or not.

## Encrypt with Password

To encrypt a document, use the **password** property to provide a password that functions as an encryption key. This will modify the content of your document and make it unreadable. The encrypted document will require to have this password entered before it can be opened.

{{% alert color="primary" %}}

You can find the appropriate **password** property for the required format. Each document save format in the [Aspose.Words.Saving](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/) module has a corresponding class containing save options for this format. For example, the [password](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/docsaveoptions/password/) property in the [DocSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/docsaveoptions/) class for DOC, or the [password](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/docsaveoptions/password/) property in the [OoxmlSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/ooxmlsaveoptions/) class for DOCX, DOCM, DOTX, DOTM, and FlatOpc.

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
| PDF |                                                        | AES-128 / AES-256                            |

The following code example shows how to encrypt a document with a password:

{{< gist "aspose-words-gists" "50a58d2d88c2177a9a4888b5d0e4de81" "encrypt-document-with-password.js" >}}

## Check If a Document Is Encrypted

In some cases, you may have an unreadable document and want to be sure that the document is encrypted and not corrupted or compressed.

To detect if a document is encrypted and if a password is required, you can use the [isEncrypted](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatinfo/isEncrypted/) property of the [FileFormatInfo](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatinfo/) class. This property will also allow you to perform some action before loading a document, for example, informing a user to provide a password.

The following code example shows how to detect the document encryption:

{{< gist "aspose-words-gists" "50a58d2d88c2177a9a4888b5d0e4de81" "verify-encrypted-document.js" >}}

## Open a Document With or Without a Password

When we have made sure that a document is encrypted, we can try to open this document without a password, which should lead to an exception.

The following code example shows how to try opening an encrypted document without a password:

{{< gist "aspose-words-gists" "50a58d2d88c2177a9a4888b5d0e4de81" "load-encrypted-document-without-password.js" >}}

After we have seen that an encrypted document cannot be opened without a password, we can try to open it by entering the password.

The following code example shows how to try opening an encrypted document with a password:

{{< gist "aspose-words-gists" "50a58d2d88c2177a9a4888b5d0e4de81" "load-save-encrypted-document.js" >}}
