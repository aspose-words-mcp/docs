---  
title: Detect File Format  
second_title: Aspose.Words for Java  
articleTitle: Detect File Format and Check Format Compatibility  
linktitle: Detect File Format and Check Format Compatibility  
description: "Obtain information about the document format before opening it to avoid an exception if you are not sure what the actual content of the file is using Java."  
type: docs  
weight: 20  
ai_search_scope: words_java  
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"  
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"  
url: /java/detect-file-format-and-check-format-compatibility/  
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

If you attempt to load a file into a [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) object and Aspose.Words cannot recognize the file format or the format is not supported, Aspose.Words will throw an exception. You can catch those exceptions and analyze them, but Aspose.Words also provides the [detectFileFormat()](https://reference.aspose.com/words/java/com.aspose.words/fileformatutil/#detectFileFormat-java.lang.String) method that allows us to quickly determine the file format without loading a document with possible exceptions. This method returns a [FileFormatInfo](https://reference.aspose.com/words/java/com.aspose.words/fileformatinfo/) object that contains the detected information about the file type.

{{% alert color="primary" %}}

DetectFileFormat only checks the file format but does not validate the file format. There is no guarantee that the file will be opened successfully, even if **detectFileFormat()** returns that it is one of the supported formats. This is because of **detectFileFormat()** method reads only partial file format data, sufficient for checking the file format, but not enough for complete validation.

{{% /alert %}}

## Check Files Format Compatibility

We can check the format compatibility of all files in the selected folder and sort them by format into corresponding subfolders.

Since we are dealing with contents in a folder, the first thing we need to do is get a collection of all the files in this folder using the `listFiles` method of the `java.io.File` class.

The following code example shows how to get a list of all the files in the folder:

{{< gist "aspose-words-gists" "13b31394822a30faeb5b68ad2b82fd75" "get-files.java" >}}

When all the files are collected, the rest of the work is done by the **detectFileFormat()** method, which checks the file format.

The following code example shows how to iterate over the collected list of files, check the format of each file, and copy each file to the appropriate folder:

{{< gist "aspose-words-gists" "13b31394822a30faeb5b68ad2b82fd75" "check-format-compatibility.java" >}}

The files are copied into appropriate subfolders using the `copyFile` method of the `FileUtils` class (Apache Commons IO).

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

1. **Q:** How can I determine a document's format without loading it into a `Document` object?  
   **A:** Use the static method `FileFormatUtil.detectFileFormat(String filePath)`. It returns a `FileFormatInfo` object that contains properties such as `getLoadFormat()` and `isEncrypted()`, allowing you to identify the format safely.

2. **Q:** What information does `FileFormatInfo` provide?  
   **A:** It tells you the detected format as a `LoadFormat` value (e.g., DOCX, RTF, HTML) and whether the file is encrypted, contains macros, or has a digital signature. You can query these via `getLoadFormat()`, `isEncrypted()`, `hasMacros()`, and `hasDigitalSignature()`.

3. **Q:** Does a successful `detectFileFormat()` call guarantee that the file can be opened by Aspose.Words?  
   **A:** No. `detectFileFormat()` only reads enough header data to identify the format. The file may still be corrupted or contain unsupported features, which could cause an exception when you later load it.

4. **Q:** How should I handle encrypted files when checking format compatibility?  
   **A:** `FileFormatInfo.isEncrypted()` will be `true` for encrypted documents. You can move them to a separate folder or prompt the user for a password before attempting to load them with `new Document(String, LoadOptions)`.

5. **Q:** Can I use `detectFileFormat()` to process many files in a folder automatically?  
   **A:** Yes. Combine `FileFormatUtil.detectFileFormat` with `java.io.File.listFiles()` to iterate over each file, evaluate its format, and then move or categorize the file based on the returned `FileFormatInfo`.