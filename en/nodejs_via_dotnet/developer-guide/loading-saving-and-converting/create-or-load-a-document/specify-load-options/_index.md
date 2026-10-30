---
title: Specify Load Options in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Specify Load Options
linktitle: Specify Load Options
description: "More accurately control the load process using Node.js."
type: docs
weight: 10
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/specify-load-options/
aliases: [/nodejs/specify-load-options/]
timestamp: 2025-01-21-14-07-04
---

When loading a document, you can set some advanced properties. Aspose.Words provides you with the [LoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/) class, which allows more precise control of the load process. Some load formats have a corresponding class that holds load options for this load format, for example, there is [PdfLoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/pdfloadoptions/) for loading to PDF format or [TxtLoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/txtloadoptions/) for loading to TXT. This article provides examples of working with options of the [LoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/) class.

## Set Microsoft Word Version to Change the Appearance

Different versions of Microsoft Word application can display documents in differently. For example, there is a well-known problem with OOXML documents such as DOCX or DOTX produced using WPS Office. In such case essential document markup elements may be missing or may be interpreted differently causing Microsoft Word 2019 to show such a document differently compared to Microsoft Word 2010.

By default Aspose.Words opens documents using Microsoft Word 2019 rules. If you need to make document loading appear as it would happen in one of the previous Microsoft Word application versions, you should explicitly specify the desired version using the [mswVersion](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/mswVersion/) property of the [LoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/) class.

The following code example shows how to set the Microsoft Word version with load options:

{{< gist "aspose-words-gists" "9298958b7a6872536299cd7e3f3ab24b" "set-ms-word-version.js" >}}

## Set Language Preferences to Change the Appearance

The details of displaying a document in Microsoft Word depend not only on the application version and the [mswVersion](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/mswVersion/) property value but also on the language settings. Microsoft Word may show documents differently depending on the "Office Language Preferences" dialog settings, that can be found in "File → Options → Language". Using this dialog a user can select, for example, primary language, proofing languages, display languages, and so on. Aspose.Words provides the [languagePreferences](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/languagePreferences/) property as the equivalent of this dialog. If Aspose.Words output differs from the Microsoft Word output, set the appropriate value for [EditingLanguage](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/editinglanguage/) – this can improve the output document.

The following code example shows how to set Japanese as [EditingLanguage](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/editinglanguage/):

{{< gist "aspose-words-gists" "9298958b7a6872536299cd7e3f3ab24b" "add-editing-language.js" >}}

## Use TempFolder to Avoid a Memory Exception

Aspose.Words supports extremely large documents that have thousands of pages full of rich content. Loading such documents may require much RAM. In the process of loading, Aspose.Words needs even more memory to hold temporary structures used to parse a document.

If you have a problem with Out of Memory exception while loading a document, try to use the [tempFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/tempFolder/) property. In this case, Aspose.Words will store some data in temporary files instead of memory, and this can help avoid such an exception.

The following code example shows how to set [tempFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/tempFolder/):

{{< gist "aspose-words-gists" "9298958b7a6872536299cd7e3f3ab24b" "temp-folder.js" >}}

## Set the Encoding Explicitly

Most modern document formats store their content in Unicode and do not require special handling. On the other hand, there are still many documents that use some pre-Unicode encoding and sometimes either miss encoding information or do not even support encoding information by nature. Aspose.Words tries to automatically detect the appropriate encoding by default, but in a rare case you may need to use an encoding different from the one detected by our encoding recognition algorithm. In this case, use the [encoding](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/encoding/) property to get or set the encoding.

The following code example shows how to set the encoding to override the automatically chosen encoding:

{{< gist "aspose-words-gists" "9298958b7a6872536299cd7e3f3ab24b" "load-with-encoding.js" >}}

## Load Encrypted Documents

You can load Word documents encrypted with a password. To do this, use a special constructor overload, which accepts a [LoadOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/) object. This object contains the [password](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/password/) property, which specifies the password string.

The following code example shows how to load a document encrypted with a password:

{{< gist "aspose-words-gists" "9298958b7a6872536299cd7e3f3ab24b" "open-encrypted-document.js" >}}

If you do not know in advance whether the file is encrypted, you can use the [FileFormatUtil](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/) class, which provides utility methods for working with file formats, such as detecting the file format or converting file extensions to/from file format enumerations. To detect if the document is encrypted and requires a password to open it, use the [isEncrypted](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatinfo/isEncrypted/) property.

The following code example shows how to verify document either it is encrypted or not:

{{< gist "aspose-words-gists" "50a58d2d88c2177a9a4888b5d0e4de81" "verify-encrypted-document.js" >}}

------ 

## FAQ

1. Q: How can I load a document using a specific Microsoft Word version?  
   A: Set the `mswVersion` property of a `LoadOptions` instance to the desired `MsWordVersion` enum value (e.g., `MsWordVersion.Word2010`) and pass this object to the `Document` constructor.

2. Q: Which property controls language‑specific rendering when loading a document?  
   A: Use the `languagePreferences` property of `LoadOptions`. Within it, set `defaultEditingLanguage` (e.g., `EditingLanguage.Japanese`) to match the language preferences you need.

3. Q: My application runs out of memory when loading a large file; what can I do?  
   A: Assign a folder path to the `tempFolder` property of `LoadOptions`. Aspose.Words will write temporary data to that folder instead of keeping everything in RAM, reducing memory pressure.

4. Q: How do I force a particular text encoding while loading a document?  
   A: Set the `encoding` property of `LoadOptions` to the name of the required encoding (e.g., `"windows-1252"`) before opening the document.

5. Q: What is the recommended way to open a password‑protected Word file?  
   A: Create a `LoadOptions` object, set its `password` property to the document's password, and pass this object to the `Document` constructor. You can also check `FileFormatUtil` → `FileFormatInfo.isEncrypted` beforehand.