---
title: Detect File Format When Loading
second_title: Aspose.Words for Node.js via .NET
articleTitle: Detect File Format and Check Format Compatibility
linktitle: Detect File Format and Check Format Compatibility
description: "Determine the file format in Node.js if you are not sure what the actual content of the file is, or to check the format compatibility."
type: docs
weight: 20
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/detect-file-format-and-check-format-compatibility/
aliases: [/nodejs/detect-file-format-and-check-format-compatibility/]
timestamp: 2025-04-21-11-17-44
---

Sometimes it is necessary to determine the format of a document before opening because the file extension does not guarantee that the contents of the file are appropriate. For example, it is known that Crystal Reports often outputs documents in RTF format, but gives them the .doc extension.

Aspose.Words provides an ability to obtain information about the file type in order to avoid an exception if you are not sure what the actual content of the file is.

## Detect File Format without an Exception

When you are dealing with multiple documents in various file formats, you may need to separate out those files that can be processed by Aspose.Words from those that cannot. You may also want to know why some of the documents cannot be processed.

If you attempt to load a file into a [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/) object and Aspose.Words cannot recognize the file format or the format is not supported, Aspose.Words will throw an exception. You can catch those exceptions and analyze them, but Aspose.Words also provides the [detectFileFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/detectfileformat/) method that allows us to quickly determine the file format without loading a document with possible exceptions. This method returns a [FileFormatInfo](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatinfo/) object that contains the detected information about the file type.

{{% alert color="primary" %}}

[detectFileFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/detectfileformat/) only checks the file format but does not validate the file format. There is no guarantee that the file will be opened successfully, even if [detectFileFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/detectfileformat/) returns that it is one of the supported formats. This is because of [detectFileFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/detectfileformat/) method reads only partial file format data, sufficient for checking the file format, but not enough for complete validation.

{{% /alert %}}

## Check Files Format Compatibility

We can check the format compatibility of all files in the selected folder and sort them by format into corresponding subfolders.

Since we are dealing with contents in a folder, the first thing we need to do is get a collection of all the files in this folder using the **readDir** method of the **fs** module.

The following code example shows how to get a list of all the files in the folder:

{{< gist "aspose-words-gists" "eabbcbd1e117d4d628dfe4fd7c30321c" "get-files.js" >}}

When all the files are collected, the rest of the work is done by the [detectFileFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/fileformatutil/detectfileformat/) method, which checks the file format.

The following code example shows how to iterate over the collected list of files, check the format of each file, and moves each file to the appropriate folder:

{{< gist "aspose-words-gists" "eabbcbd1e117d4d628dfe4fd7c30321c" "check-format-compatibility.js" >}}

The files are moved into appropriate subfolders using the **copyFile** method of the **fs** module.

The following files are used in the example above. The file name is on the left and its description is on the right:

| Group of Files | Input Document | Type |
| :- | :- | :- |
| Supported file formats | Test File (Doc).doc | Microsoft Word 95/6.0 or Microsoft Word 97 – 2003 document. |
|  | Test File (`Dot`).dot | Microsoft Word 95/6.0 or Microsoft Word 97 – 2003 template. |
|  | Test File (Docx).docx | Office Open XML WordprocessingML document without macros. |
|  | Test File (Docm).docm | Office Open XML WordprocessingML document with macros. |
|  | Test File (Dotx).dotx | Office Open XML WordprocessingML template. |
|  | Test File (Dotm).dotm | Office Open XML WordprocessingML template with macros. |
|  | Test File (XML).xml | FlatOPC OOXML Document. |
|  | Test File (RTF).rtf | Rich Text Format document. |
|  | Test File (WordML).xml | Microsoft Word 2003 WordprocessingML document. |
|  | Test File (HTML).html | HTML document. |
|  | Test File (MHTML).mhtml | MHTML (Web archive) document. |
|  | Test File (Odt).odt | OpenDocument Text (OpenOffice Writer). |
|  | Test File (Ott).ott | OpenDocument Document Template. |
|  | Test File (DocPreWord60).doc | Microsoft Word 2.0 document. |
| Encrypted documents | Test File (Enc).doc | Encrypted Microsoft Word 95/6.0 or Microsoft Word 97 – 2003 document. |
|  | Test File (Enc).docx | Encrypted Office Open XML WordprocessingML document. |
| Unsupported file formats | Test File (JPG).jpg | JPEG image file. |

------  

## FAQ

1. **Q:** How can I determine a document's format without loading it into a `Document` object?  
   **A:** Use the static method `FileFormatUtil.detectFileFormat(filePath)`. It reads only the header bytes of the file and returns a `FileFormatInfo` object that contains the detected format, extension, and whether the format is supported by Aspose.Words.

2. **Q:** What does `detectFileFormat` return for a file whose format is not supported?  
   **A:** The returned `FileFormatInfo` will have the `loadFormat` property set to `LoadFormat.Unknown`. This lets you skip or move the file without throwing an exception.

3. **Q:** How can I verify that the detected format is actually supported for loading?  
   **A:** Check the `loadFormat` property of the `FileFormatInfo`. If it is not `LoadFormat.Unknown`, the format is one of the formats that Aspose.Words can load. You may still need to handle encrypted or corrupted files separately.

4. **Q:** What should I do if `detectFileFormat` indicates a supported format but loading the document still fails?  
   **A:** The detection step only reads a small portion of the file. If loading fails, the file may be corrupted, encrypted with an unknown password, or contain features not handled by the current version. Catch the exception, inspect its message, and consider validating the file (e.g., checking for encryption with `FileFormatInfo.isEncrypted`) before retrying.  