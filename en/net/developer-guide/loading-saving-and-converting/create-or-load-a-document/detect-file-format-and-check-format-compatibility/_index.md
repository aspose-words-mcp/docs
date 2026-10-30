---
title: Detect File Format When Loading
second_title: Aspose.Words for .NET
articleTitle: Detect File Format and Check Format Compatibility
linktitle: Detect File Format and Check Format Compatibility
description: "Determine the file format in C# if you are not sure what the actual content of the file is, or to check the format compatibility."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/detect-file-format-and-check-format-compatibility/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to detect file format and verify compatibility before loading a document with Aspose.Words.

{{% /alert %}}

Sometimes it is necessary to determine the format of a document before opening because the file extension does not guarantee that the contents of the file are appropriate. For example, it is known that Crystal Reports often outputs documents in RTF format, but gives them the .doc extension.

Aspose.Words provides an ability to obtain information about the file type in order to avoid an exception if you are not sure what the actual content of the file is.

## Detect File Format without an Exception

When you are dealing with multiple documents in various file formats, you may need to separate out those files that can be processed by Aspose.Words from those that cannot. You may also want to know why some of the documents cannot be processed.

If you attempt to load a file into a [Document](https://reference.aspose.com/words/net/aspose.words/document/) object and Aspose.Words cannot recognize the file format or the format is not supported, Aspose.Words will throw an exception. You can catch those exceptions and analyze them, but Aspose.Words also provides the [DetectFileFormat](https://reference.aspose.com/words/net/aspose.words/fileformatutil/detectfileformat/) method that allows us to quickly determine the file format without loading a document with possible exceptions. This method returns a [FileFormatInfo](https://reference.aspose.com/words/net/aspose.words/fileformatinfo/) object that contains the detected information about the file type.

{{% alert color="primary" %}}

DetectFileFormat only checks the file format but does not validate the file format. There is no guarantee that the file will be opened successfully, even if **DetectFileFormat** returns that it is one of the supported formats. This is because of **DetectFileFormat** method reads only partial file format data, sufficient for checking the file format, but not enough for complete validation.

{{% /alert %}}

## Check Files Format Compatibility

We can check the format compatibility of all files in the selected folder and sort them by format into corresponding subfolders.

Since we are dealing with contents in a folder, the first thing we need to do is get a collection of all the files in this folder using the **GetFiles** method of the `Directory` class (from the `System.IO` namespace).

The following code example shows how to get a list of all the files in the folder:

{{< gist "aspose-words-gists" "7fe3fc4004f081628a63608db70332b3" "get-files.cs" >}}

When all the files are collected, the rest of the work is done by the **DetectFileFormat** method, which checks the file format.

The following code example shows how to iterate over the collected list of files, check the format of each file, and moves each file to the appropriate folder:

{{< gist "aspose-words-gists" "7fe3fc4004f081628a63608db70332b3" "check-format-compatibility.cs" >}}

The files are moved into appropriate subfolders using the `Move` method of the `File` class, from the same `System.IO` namespace.

The following files are used in the example above. The file name is on the left and its description is on the right:

| Group of Files | Input Document | Type |
| :- | :- | :- |
| Supported file formats | Test File (Doc).doc | Microsoft Word 95/6.0 or Microsoft Word 97 – 2003 document. |
|  | Test File (Dot).dot | Microsoft Word 95/6.0 or Microsoft Word 97 – 2003 template. |
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

1. **Q:** How can I detect the file format of a document without loading it into a `Document` object?  
   **A:** Use the static method `FileFormatUtil.DetectFileFormat(string filePath)`. It returns a `FileFormatInfo` object that contains the detected format, version, and whether the format is supported, all without creating a `Document` instance.

2. **Q:** Which Aspose.Words API method checks whether a detected format is compatible with the library?  
   **A:** After calling `DetectFileFormat`, check the `FileFormatInfo.LoadFormat` property. If it is `LoadFormat.Unknown`, Aspose.Words cannot load the file; otherwise you can attempt loading it.

3. **Q:** Does a successful `DetectFileFormat` call guarantee that the document will open without errors?  
   **A:** No. `DetectFileFormat` reads only the header information needed to identify the format. The file may still be corrupted, encrypted with an unknown password, or contain unsupported features that cause loading to fail.

4. **Q:** How should I handle files that are not supported when processing a folder of documents?  
   **A:** After detecting the format, move unsupported files to a separate folder (e.g., “Unsupported”) using `File.Move`. This prevents exceptions during bulk processing and lets you log or review those files later.

5. **Q:** Can `DetectFileFormat` identify encrypted documents?  
   **A:** Yes. For encrypted Word files, `FileFormatInfo.IsEncrypted` will be `true`. You can then decide whether to prompt for a password or skip the file, depending on your application's requirements.