---
title: Convert a Document to HTML, MHTML or EPUB
second_title: Aspose.Words for C++
articleTitle: Convert a Document to HTML, MHTML or EPUB
linktitle: Convert a Document to HTML, MHTML or EPUB
description: "Convert a document from almost any format to HTML or MHTML, as well as to EPUB format using C++. You can also specify save options for managing the output document."
type: docs
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/convert-a-document-to-html-mhtml-or-epub/
timestamp: 2024-10-21-08-52-03
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert Word documents to HTML, MHTML, or EPUB, and describes the key options that influence layout and formatting during export.

{{% /alert %}}

Documents in HTML and MHTML flow-layout formats are also very popular and can be used on any web platform. For that reason, converting documents to HTML and MHTML is an important feature of Aspose.Words.

EPUB (short for "Electronic Publication") is an HTML-based format commonly used for electronic book distribution. This format is fully supported in Aspose.Words for exporting electronic books that are compatible with most reading devices.

## Convert a Document

For simple conversion to HTML, MHTML, or EPUB, one of the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method overloads is used. You can save the document to a file or stream and explicitly set the output document save format or define it from the file name extension.

The following example shows how to convert DOCX to HTML with specifying a save format:

{{< gist "aspose-words-gists" "058a709735430153ce719761043ded8f" "docx-to-html.h" >}}

To convert a document to MHTML or EPUB, use `SaveFormat::Mhtml` or `SaveFormat::Epub` respectively.

## Convert a Document with Round-trip Information

The HTML format does not support many Microsoft Word features, and if we need to restore a document model as close to the original as possible, we need to save some extra information within the HTML file. Such information is also called "round-trip information". For this purpose, Aspose.Words provides an ability to export round-trip information when saving to HTML, MHTML, or EPUB using the [get_ExportRoundtripInformation()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_exportroundtripinformation/) property. Saving the round-trip information allows to restore document properties such as tabs, comments, headers, and footers during the loading documents of the listed formats back into a **Document** object.

The default value is **true** for HTML and **false** for MHTML and EPUB:

- When **true**, the round-trip information is exported as - aw - * CSS properties of the corresponding HTML elements
- When **false**, there is no round-trip information to be output into produced files

The following code example shows how to export round-trip information when converting a document from DOCX into HTML:

{{< gist "aspose-words-gists" "058a709735430153ce719761043ded8f" "export-roundtrip-information.h" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

## Specify Save Options when Conversion to HTML

Aspose.Words allows to convert a Word document to HTML using default or custom save options. Few examples of custom save options are described below.

### Specify a Folder for Saving Resources

Using Aspose.Words we can specify a physical folder where all resources, such as images, fonts, and external CSS, are saved when a document is converted to HTML. By default, this is an empty string.

Specifying the [get_ResourceFolder()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_resourcefolder/) property is the simplest way to set the folder where all resources should be written. We can use individual properties, such as [get_FontsFolder()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_fontsfolder/) which saves fonts to the specified folder and [get_ImagesFolder()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_imagesfolder/) which saves images to a specified folder. When a relative path is specified, **FontsFolder** and **get_ImagesFolder()** refer to the folder where the code assembly is located, **get_ResourceFolder()** and [get_CssStyleSheetFileName()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_cssstylesheetfilename/) refer to the output folder where the HTML document is located.

In this example, **get_ResourceFolder()** specifies the relative path. This path refers to the output folder where HTML document is saved. The value of the **get_ResourceFolderAlias()** property is used to create URLs for all resources.

The following code example shows how to work with these properties:

{{< gist "aspose-words-gists" "058a709735430153ce719761043ded8f" "export-resources.h" >}}

Using the [get_ResourceFolderAlias()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_resourcefolderalias/) property, we can also specify the name of the folder used to construct URIs of all resources written into an HTML document. This is the simplest way to specify how URIs should be generated for all resource files. The same information can be specified for images and fonts separately via [get_ImagesFolderAlias()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_imagesfolderalias/) and [get_FontsFolderAlias()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_fontsfolderalias/) properties, respectively.

However, there is no individual property for CSS. The behavior of the **FontsFolder**, **get_FontsFolderAlias()**, **get_ImagesFolder()**, **get_ImagesFolderAlias()** and **get_CssStyleSheetFileName()** properties are not changed. Note that the **get_CssStyleSheetFileName()** property is used both for specifying folder name and file name.

- **get_ResourceFolder()** has lower priority than folders specified via **FontsFolder**, **get_ImagesFolder()**, and **get_CssStyleSheetFileName()**. If the folder specified in the **get_ResourceFolder()** does not exist, it will be created automatically.
- **get_ResourceFolderAlias()** has a lower priority than **get_FontsFolderAlias()** and **get_ImagesFolderAlias()**. If **get_ResourceFolderAlias()** is empty, the value of the **get_ResourceFolder()** property will be used to create resource URIs. If **get_ResourceFolderAlias()** is set to "." (dot), resource URIs will only contain file names without specifying a path.

### Export Base64 Encoding Fonts Resources

Aspose.Words provides an ability to specify whether font resources should be embedded into HTML in Base64 encodings. To perform this, use the [get_ExportFontsAsBase64()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_exportfontsasbase64/) property – this is an extension of the [get_ExportFontResources()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_exportfontresources/) property. By default, its value is **false**, and fonts are written into separate files. But if this option is set to **true**, fonts will be embedded into the document's CSS in Base64 encoding. The **get_ExportFontsAsBase64()** property only affects HTML format and does not affect EPUB and MHTML.

The following code example shows how to export Base64‑encoded fonts to HTML:

{{< gist "aspose-words-gists" "058a709735430153ce719761043ded8f" "export-fonts-as-base64.h" >}}

## Specify Save Options when Conversion to EPUB

Aspose.Words allows to convert a Word document into EPUB format using default or custom save options. You can specify a number of options by passing an instance of [HtmlSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/) to the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method.

The following code example shows how to converts a Word document to EPUB with specifying some custom save options:

{{< gist "aspose-words-gists" "058a709735430153ce719761043ded8f" "split-document-by-headings.h" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

## See Also

- [How to export round‑trip information when saving to HTML](/words/cpp/convert-a-document-to-html-mhtml-or-epub/#convert-a-document-with-round-trip-information)

------  

## FAQ

1. **Q:** How do I convert a DOCX file to HTML using Aspose.Words for C++?  
   **A:** Load the document with `auto doc = System::MakeObject<Document>(u"input.docx");` and call `doc->Save(u"output.html", SaveFormat::Html);`. This uses the default `HtmlSaveOptions`.  

2. **Q:** How can I preserve Word‑specific features (round‑trip information) when saving to HTML?  
   **A:** Create an `HtmlSaveOptions` object with `auto options = System::MakeObject<HtmlSaveOptions>();`, call `options->set_ExportRoundtripInformation(true);`, and pass it to `Document::Save`. This embeds additional CSS that allows the document to be re‑loaded with tabs, comments, headers, and footers restored.  

3. **Q:** Where can I specify the folder for images, fonts, and other resources generated during HTML conversion?  
   **A:** Create `auto options = System::MakeObject<HtmlSaveOptions>();`, then call `options->set_ResourceFolder(u"Resources");`, `options->set_ImagesFolder(u"Resources/Images");`, and `options->set_FontsFolder(u"Resources/Fonts");`. The folders are created automatically if they do not exist.  

4. **Q:** How do I embed fonts directly into the HTML file as Base64 strings?  
   **A:** Call `options->set_ExportFontsAsBase64(true);` on an `HtmlSaveOptions` instance before saving. This causes font files to be encoded in Base64 and placed inside the generated CSS, eliminating external font files.  

5. **Q:** What is the recommended way to convert a document to EPUB with custom options?  
   **A:** EPUB uses `HtmlSaveOptions`: create the options with `SaveFormat::Epub` and pass them to `Document::Save`. For example:  

   ```cpp
   auto options = System::MakeObject<HtmlSaveOptions>(SaveFormat::Epub);
   options->set_ExportFontResources(true);
   options->set_ExportImagesAsBase64(true);
   auto doc = System::MakeObject<Document>(u"input.docx");
   doc->Save(u"output.epub", options);
   ```  

   This lets you control font embedding, image handling, and other EPUB‑specific settings.