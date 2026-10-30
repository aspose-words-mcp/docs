---
title: Specify Load Options in Java
second_title: Aspose.Words for Java
articleTitle: Specify Load Options
linktitle: Specify Load Options
description: "Set advanced properties when loading a document using Java to obtain more precise control of the process."
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/specify-load-options/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to specify load options when opening a document.

{{% /alert %}}

When loading a document, you can set some advanced properties. Aspose.Words provides you with the [LoadOptions](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/) class, which allows more precise control of the load process. Some load formats have a corresponding class that holds load options for this load format, for example, there is [PdfLoadOptions](https://reference.aspose.com/words/java/com.aspose.words/pdfloadoptions/) for loading to PDF format or [TxtLoadOptions](https://reference.aspose.com/words/java/com.aspose.words/txtloadoptions/) for loading to TXT. This article provides examples of working with options of the **LoadOptions** class.

## Set Microsoft Word Version to Change the Appearance

Different versions of Microsoft Word application can display documents in differently. For example, there is a well-known problem with OOXML documents such as DOCX or DOTX produced using WPS Office. In such case essential document markup elements may be missing or may be interpreted differently causing Microsoft Word 2019 to show such a document differently compared to Microsoft Word 2010.

By default Aspose.Words opens documents using Microsoft Word 2019 rules. If you need to make document loading appear as it would happen in one of the previous Microsoft Word application versions, you should explicitly specify the desired version using the [getMswVersion()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getMswVersion) property of the **LoadOptions** class.

The following code example shows how to set the Microsoft Word version with load options:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "set-ms-word-version.java" >}}

## Set Language Preferences to Change the Appearance

The details of displaying a document in Microsoft Word depend not only on the application version and the **getMswVersion()** property value but also on the language settings. Microsoft Word may show documents differently depending on the "Office Language Preferences" dialog settings, that can be found in "File → Options → Language". Using this dialog a user can select, for example, primary language, proofing languages, display languages, and so on. Aspose.Words provides the [getLanguagePreferences()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getLanguagePreferences) property as the equivalent of this dialog. If Aspose.Words output differs from the Microsoft Word output, set the appropriate value for **EditingLanguage** – this can improve the output document.

The following code example shows how to set Japanese as **EditingLanguage**:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "add-editing-language.java" >}}

## Use WarningCallback to Control Problems While Loading a Document

Some documents may be corrupted, contain invalid entries, or have features not currently supported by Aspose.Words. If you want to know about problems that occurred while loading a document, Aspose.Words provides the [IWarningCallback](https://reference.aspose.com/words/java/com.aspose.words/iwarningcallback/) interface.

The following code example shows the implementation of the **IWarningCallback** interface:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "i-warning-callback.java" >}}

To get information about all problems throughout the load time, use the [getWarningCallback()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getWarningCallback) property.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "warning-callback.java" >}}

## Use ResourceLoadingCallback to Control the External Resources Loading

A document may contain external links to images located somewhere on a local disk, network, or Internet. Aspose.Words automatically loads such images into a document, but there are situations when this process needs to be controlled. For example, to decide whether we really need to load a certain image or perhaps skip it. the [getResourceLoadingCallback()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getResourceLoadingCallback) load option allows you to control this.

The following code example shows the implementation of the [IResourceLoadingCallback](https://reference.aspose.com/words/java/com.aspose.words/iresourceloadingcallback/) interface:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "i-resource-loading-callback.java" >}}

The following code example shows how to use the **getResourceLoadingCallback()** property:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "resource-loading-callback.java" >}}

## Use TempFolder to Avoid a Memory Exception

Aspose.Words supports extremely large documents that have thousands of pages full of rich content. Loading such documents may require much RAM. In the process of loading, Aspose.Words needs even more memory to hold temporary structures used to parse a document.

If you have a problem with the Out of Memory exception while loading a document, try to use the [getTempFolder()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getTempFolder) property. In this case, Aspose.Words will store some data in temporary files instead of memory, and this can help avoid such an exception.

The following code example shows how to set **getTempFolder()**:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "temp-folder.java" >}}

## Set the Encoding Explicitly

Most modern document formats store their content in Unicode and do not require special handling. On the other hand, there are still many documents that use some pre-Unicode encoding and sometimes either miss encoding information or do not even support encoding information by nature. Aspose.Words tries to automatically detect the appropriate encoding by default, but in a rare case you may need to use an encoding different from the one detected by our encoding recognition algorithm. In this case, use the [getEncoding()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getEncoding) property to get or set the encoding.

The following code example shows how to set the encoding to override the automatically chosen encoding:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "load-with-encoding.java" >}}

## Load Encrypted Documents

You can load Word documents encrypted with a password. To do this, use a special constructor overload, which accepts a [LoadOptions](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/) object. This object contains the [getPassword()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getPassword) property, which specifies the password string.

The following code example shows how to load a document encrypted with a password:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "open-encrypted-document.java" >}}

If you do not know in advance whether the file is encrypted, you can use the [FileFormatUtil](https://reference.aspose.com/words/java/com.aspose.words/fileformatutil/) class, which provides utility methods for working with file formats, such as detecting the file format or converting file extensions to/from file format enumerations. To detect if the document is encrypted and requires a password to open it, use the [isEncrypted()](https://reference.aspose.com/words/java/com.aspose.words/fileformatinfo/#isEncrypted) property.

The following code example shows how to verify OpenDocument either it is encrypted or not:

{{< gist "aspose-words-gists" "821ff3a1df0c75b2af641299b393fb60" "verify-encrypted-document.java" >}}

------

## FAQ

1. **Q:** How can I load a document using a specific Microsoft Word version?  
   **A:** Create a `LoadOptions` object and call `setMswVersion` with the desired `MsWordVersion` value (e.g., `MsWordVersion.WORD_2007`). Pass this `LoadOptions` instance to the `Document` constructor.

2. **Q:** What should I do if the document's encoding is detected incorrectly?  
   **A:** Set the `Encoding` property of `LoadOptions` to the required `java.nio.charset.Charset` (e.g., `Charset.forName("Windows-1252")`) before loading the document.

3. **Q:** How can I load a password‑protected Word file?  
   **A:** Provide a `LoadOptions` object with its `Password` property set to the document's password, then use this object when constructing the `Document`.

4. **Q:** How do I receive warnings about problems that occur while loading a document?  
   **A:** Implement the `IWarningCallback` interface, assign an instance to the `getWarningCallback()` property of `LoadOptions`, and then load the document with those options.

5. **Q:** Is there a way to limit memory usage when loading very large documents?  
   **A:** Yes. Set the `getTempFolder()` property of `LoadOptions` to a folder path where Aspose.Words can write temporary files, reducing RAM consumption during loading.