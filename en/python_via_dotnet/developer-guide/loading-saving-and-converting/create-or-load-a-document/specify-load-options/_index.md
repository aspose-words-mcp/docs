---
title: Specify Load Options in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Specify Load Options
linktitle: Specify Load Options
description: "More accurately control the load process using Python."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/specify-load-options/
aliases: [/python/specify-load-options/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to use the `LoadOptions` class in Aspose.Words for Python via .NET to customize document loading, including setting the Microsoft Word version, language preferences, temporary folder, encoding, and loading encrypted documents.
{{% /alert %}}

When loading a document, you can set some advanced properties. Aspose.Words provides you with the [LoadOptions](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/) class, which allows more precise control of the load process. Some load formats have a corresponding class that holds load options for this load format, for example, there is [PdfLoadOptions](https://reference.aspose.com/words/python-net/aspose.words.loading/pdfloadoptions/) for loading to PDF format or [TxtLoadOptions](https://reference.aspose.com/words/python-net/aspose.words.loading/txtloadoptions/) for loading to TXT. This article provides examples of working with options of the **LoadOptions** class.

## Set Microsoft Word Version to Change the Appearance

Different versions of Microsoft Word application can display documents in differently. For example, there is a well‑known problem with OOXML documents such as DOCX or DOTX produced using WPS Office. In such case essential document markup elements may be missing or may be interpreted differently causing Microsoft Word 2019 to show such a document differently compared to Microsoft Word 2010.

By default Aspose.Words opens documents using Microsoft Word 2019 rules. If you need to make document loading appear as it would happen in one of the previous Microsoft Word application versions, you should explicitly specify the desired version using the [msw_version](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/msw_version/) property of the **LoadOptions** class.

The following code example shows how to set the Microsoft Word version with load options:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "set-ms-word-version.py" >}}

## Set Language Preferences to Change the Appearance

The details of displaying a document in Microsoft Word depend not only on the application version and the **msw_version** property value but also on the language settings. Microsoft Word may show documents differently depending on the "Office Language Preferences" dialog settings, that can be found in "File → Options → Language". Using this dialog a user can select, for example, primary language, proofing languages, display languages, and so on. Aspose.Words provides the [language_preferences](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/language_preferences/) property as the equivalent of this dialog. If Aspose.Words output differs from the Microsoft Word output, set the appropriate value for **default_editing_language** – this can improve the output document.

The following code example shows how to set Japanese as **default_editing_language**:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "add-editing-language.py" >}}

## Use WarningCallback to Control Problems While Loading a Document

Some documents may be corrupted, contain invalid entries, or have features not currently supported by Aspose.Words. If you want to know about problems that occurred while loading a document, Aspose.Words provides the [IWarningCallback](https://reference.aspose.com/words/python-net/aspose.words/iwarningcallback/) interface.

The following code example shows the implementation of the **IWarningCallback** interface:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "i-warning-callback.py" >}}

To get information about all problems throughout the load time, use the [warning_callback](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/warning_callback/) property.

The following code example shows how to use this property:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "warning-callback.py" >}}

## Use ResourceLoadingCallback to Control the External Resources Loading

A document may contain external links to images located somewhere on a local disk, network, or Internet. Aspose.Words automatically loads such images into a document, but there are situations when this process needs to be controlled. For example, to decide whether we really need to load a certain image or perhaps skip it. The [resource_loading_callback](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/resource_loading_callback/) load option allows you to control this.

The following code example shows the implementation of the [IResourceLoadingCallback](https://reference.aspose.com/words/python-net/aspose.words.loading/iresourceloadingcallback/) interface:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "i-resource-loading-callback.py" >}}

The following code example shows how to use the **resource_loading_callback** property:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "resource-loading-callback.py" >}}

## Use TempFolder to Avoid a Memory Exception

Aspose.Words supports extremely large documents that have thousands of pages full of rich content. Loading such documents may require much RAM. In the process of loading, Aspose.Words needs even more memory to hold temporary structures used to parse a document.

If you have a problem with Out of Memory exception while loading a document, try to use the [temp_folder](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/temp_folder/) property. In this case, Aspose.Words will store some data in temporary files instead of memory, and this can help avoid such an exception.

The following code example shows how to set **temp_folder**:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "temp-folder.py" >}}

## Set the Encoding Explicitly

Most modern document formats store their content in Unicode and do not require special handling. On the other hand, there are still many documents that use some pre‑Unicode encoding and sometimes either miss encoding information or do not even support encoding information by nature. Aspose.Words tries to automatically detect the appropriate encoding by default, but in a rare case you may need to use an encoding different from the one detected by our encoding recognition algorithm. In this case, use the [encoding](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/encoding/) property to get or set the encoding.

The following code example shows how to set the encoding to override the automatically chosen encoding:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "load-with-encoding.py" >}}

## Load Encrypted Documents

You can load Word documents encrypted with a password. To do this, use a special constructor overload, which accepts a [LoadOptions](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/) object. This object contains the [password](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/password/) property, which specifies the password string.

The following code example shows how to load a document encrypted with a password:

{{< gist "aspose-words-gists" "41c71acaf4924abe47f4bc2ff2c87d6a" "open-encrypted-document.py" >}}

If you do not know in advance whether the file is encrypted, you can use the [FileFormatUtil](https://reference.aspose.com/words/python-net/aspose.words/fileformatutil/) class, which provides utility methods for working with file formats, such as detecting the file format or converting file extensions to/from file format enumerations. To detect if the document is encrypted and requires a password to open it, use the [is_encrypted](https://reference.aspose.com/words/python-net/aspose.words/fileformatinfo/is_encrypted/) property.

The following code example shows how to verify OpenDocument either it is encrypted or not:

{{< gist "aspose-words-gists" "6548546f98bd830e363bbb567b114850" "verify-encrypted-document.py" >}} 

## FAQ

1. **Q:** How can I load a password‑protected Word document with Aspose.Words for Python?  
   **A:** Create a `LoadOptions` object, set its `password` property to the document’s password, and pass this object to the `Document` constructor. Example:  
   ```python
   import aspose.words as aw
   load_options = aw.loading.LoadOptions()
   load_options.password = "MySecret"
   doc = aw.Document("encrypted.docx", load_options)
   ```

2. **Q:** Which property should I use to make Aspose.Words render a document as it would appear in an older version of Microsoft Word?  
   **A:** Use the `msw_version` property of `LoadOptions`. Set it to the desired `MsWordVersion` enum value (e.g., `MsWordVersion.WORD2010`). Example:  
   ```python
   import aspose.words as aw
   load_options = aw.loading.LoadOptions()
   load_options.msw_version = aw.settings.MsWordVersion.WORD2010
   doc = aw.Document("sample.docx", load_options)
   ```

3. **Q:** How do I change the language preferences (e.g., editing language) when loading a document?  
   **A:** Add the desired `EditingLanguage` to the `language_preferences` of `LoadOptions`. Example:  
   ```python
   import aspose.words as aw
   load_options = aw.loading.LoadOptions()
   load_options.language_preferences.add_editing_language(aw.loading.EditingLanguage.JAPANESE)
   doc = aw.Document("sample.docx", load_options)
   ```

4. **Q:** My application runs out of memory when loading a very large document. Is there a way to reduce memory usage?  
   **A:** Yes. Specify a folder for temporary files using the `temp_folder` property of `LoadOptions`. Aspose.Words will write intermediate data to disk instead of keeping everything in RAM. Example:  
   ```python
   import aspose.words as aw
   load_options = aw.loading.LoadOptions()
   load_options.temp_folder = "C:/temp/aw_temp"
   doc = aw.Document("large.docx", load_options)
   ```

5. **Q:** The text in a legacy document appears garbled after loading. How can I force a specific encoding?  
   **A:** Set the `encoding` property of `LoadOptions` to the name of the required codec, for example `"utf-8"` or `"windows-1251"`.

   ```python
   import aspose.words as aw
   load_options = aw.loading.LoadOptions()
   load_options.encoding = "windows-1251"
   doc = aw.Document("legacy.txt", load_options)
   ```