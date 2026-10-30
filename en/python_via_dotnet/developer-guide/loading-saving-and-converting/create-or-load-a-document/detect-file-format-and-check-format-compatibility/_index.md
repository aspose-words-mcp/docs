---
title: Detect File Format When Loading
second_title: Aspose.Words for Python via .NET
articleTitle: Detect File Format and Check Format Compatibility
linktitle: Detect File Format and Check Format Compatibility
description: "Determine the file format in Python if you are not sure what the actual content of the file is, or to check the format compatibility."
type: docs
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/detect-file-format-and-check-format-compatibility/
aliases: [/python/detect-file-format-and-check-format-compatibility/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to detect a document's file format without loading it and to verify format compatibility, including code samples for processing multiple files and organizing them by supported, encrypted, or unsupported formats.

{{% /alert %}}

Sometimes it is necessary to determine the format of a document before opening because the file extension does not guarantee that the contents of the file are appropriate. For example, it is known that Crystal Reports often outputs documents in RTF format, but gives them the .doc extension.

Aspose.Words provides an ability to obtain information about the file type in order to avoid an exception if you are not sure what the actual content of the file is.

## Detect File Format without an Exception

When you are dealing with multiple documents in various file formats, you may need to separate out those files that can be processed by Aspose.Words from those that cannot. You may also want to know why some of the documents cannot be processed.

If you attempt to load a file into a [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) object and Aspose.Words cannot recognize the file format or the format is not supported, Aspose.Words will throw an exception. You can catch those exceptions and analyze them, but Aspose.Words also provides the [detect_file_format](https://reference.aspose.com/words/python-net/aspose.words/fileformatutil/detect_file_format/) method that allows us to quickly determine the file format without loading a document with possible exceptions. This method returns a [FileFormatInfo](https://reference.aspose.com/words/python-net/aspose.words/fileformatinfo/) object that contains the detected information about the file type.

{{% alert color="primary" %}}

The detect_file_format method only checks the file format but does not validate the file format. There is no guarantee that the file will be opened successfully, even if **detect_file_format** returns that it is one of the supported formats. This is because of **detect_file_format** method reads only partial file format data, sufficient for checking the file format, but not enough for complete validation.

{{% /alert %}}

## Check Files Format Compatibility

We can check the format compatibility of all files in the selected folder and sort them by format into corresponding subfolders.

In Python, use `import os` and `files = os.listdir(folder_path)` or `from pathlib import Path` and `files = list(Path(folder_path).glob('*'))` to obtain the collection of files.

The following code example shows how to get a list of all the files in the folder:

{{< gist "aspose-words-gists" "85de5d316960e79e2ab11a50c4dde445" "get-files.py" >}}

When all the files are collected, the rest of the work is done by the **detect_file_format** method, which checks the file format.

The following code example shows how to iterate over the collected list of files, check the format of each file, and moves each file to the appropriate folder:

{{< gist "aspose-words-gists" "85de5d316960e79e2ab11a50c4dde445" "check-format-compatibility.py" >}}

Use Python's standard library, e.g., `import shutil; shutil.move(src_path, dest_path)` or `pathlib.Path(src).rename(dest_path)`.

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

## FAQ

1. **Q:** How can I determine a document's format without loading it into a `Document` object?  
   **A:** Use `FileFormatUtil.detect_file_format(file_path)`. The method returns a `FileFormatInfo` object that contains the detected load format (`LoadFormat.UNKNOWN` if the format is not recognized) and shows whether the file is encrypted, digitally signed, or contains macros, without loading the document.

2. **Q:** Does `detect_file_format` guarantee that the file can be opened successfully afterwards?  
   **A:** No. The method only reads enough bytes to identify the format; it does not perform full validation. A file may still cause an exception when loaded if it is corrupted or partially supported.

3. **Q:** Which file formats are considered supported by Aspose.Words for Python via .NET?  
   **A:** Supported formats include DOC, DOT, DOCX, DOCM, DOTX, DOTM, XML (Flat OPC), RTF, WORDML (Word 2003), HTML, MHTML, ODT, OTT, and others. See the full list of supported formats on the [Supported Document Formats](https://docs.aspose.com/words/python-net/supported-document-formats/) page.

4. **Q:** How should I handle files that `detect_file_format` reports as unsupported?  
   **A:** You can skip processing them, move them to a separate folder, or log a warning. Attempting to load an unsupported file with `Document` will raise an exception.

5. **Q:** Can `detect_file_format` identify encrypted documents, and do I need a license to work with them?  
   **A:** Yes, it can detect encrypted DOC/DOCX files and will mark them as encrypted in `FileFormatInfo`. To load it, provide the password in `LoadOptions.password`; no license is needed for this.