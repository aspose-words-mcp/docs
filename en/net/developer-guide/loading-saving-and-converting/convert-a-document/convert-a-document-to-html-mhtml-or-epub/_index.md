---
title: Convert a Document to HTML, MHTML or EPUB in C#
second_title: Aspose.Words for .NET
articleTitle: Convert a Document to HTML, MHTML or EPUB
linktitle: Convert a Document to HTML, MHTML or EPUB
description: "Convert a document from almost any format to HTML or MHTML, as well as to EPUB format using C#. You can also specify save options for managing the output document."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/convert-a-document-to-html-mhtml-or-epub/
timestamp: 2024-07-09-19-00-42
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert Word documents to HTML, MHTML, or EPUB, and describes the key options that influence layout and formatting during export.

{{% /alert %}}

Documents in HTML and MHTML flow-layout formats are also very popular and can be used on any web platform. For that reason, converting documents to HTML and MHTML is an important feature of Aspose.Words.

EPUB (short for "Electronic Publication") is an HTML-based format commonly used for electronic book distribution. This format is fully supported in Aspose.Words for exporting electronic books that are compatible with most reading devices.

## Convert a Document

For simple conversion to HTML, MHTML, or EPUB, one of the [Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save/) method overloads is used. You can save the document to a file or stream and explicitly set the output document save format or define it from the file name extension.

The following example shows how to convert DOCX to HTML with specifying a save format:

{{< gist "aspose-words-gists" "c0df00d37081f41a7683339fd7ef66c1" "docx-to-html.cs" >}}

To convert a document to MHTML or EPUB, use `SaveFormat.Mhtml` or `SaveFormat.Epub` respectively.

## Convert a Document with Round-trip Information

The HTML format does not support many Microsoft Word features, and if we need to restore a document model as close to the original as possible, we need to save some extra information within the HTML file. Such information is also called "round-trip information". For this purpose, Aspose.Words provides an ability to export round-trip information when saving to HTML, MHTML, or EPUB using the [ExportRoundtripInformation](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/exportroundtripinformation/) property. Saving the round-trip information allows to restore document properties such as tabs, comments, headers, and footers during the loading documents of the listed formats back into a **Document** object.

The default value is **true** for HTML and **false** for MHTML and EPUB:

- When **true**, the round-trip information is exported as - aw - * CSS properties of the corresponding HTML elements
- When **false**, there is no round-trip information to be output into produced files

The following code example shows how to export round-trip information when converting a document from DOCX into HTML:

{{< gist "aspose-words-gists" "c0df00d37081f41a7683339fd7ef66c1" "export-roundtrip-information.cs" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

## Specify Save Options when Conversion to HTML

Aspose.Words allows to convert a Word document to HTML using default or custom save options. Few examples of custom save options are described below.

### Specify a Folder for Saving Resources

Using Aspose.Words we can specify a physical folder where all resources, such as images, fonts, and external CSS, are saved when a document is converted to HTML. By default, this is an empty string.

Specifying the [ResourceFolder](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/resourcefolder/) property is the simplest way to set the folder where all resources should be written. We can use individual properties, such as [FontsFolder](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/fontsfolder/) which saves fonts to the specified folder and [ImagesFolder](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/imagesfolder/) which saves images to a specified folder. When a relative path is specified, **FontsFolder** and **ImagesFolder** refer to the folder where the code assembly is located, **ResourceFolder** and [CssStyleSheetFileName](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/cssstylesheetfilename/) refer to the output folder where the HTML document is located.

In this example, **ResourceFolder** specifies the relative path. This path refers to the output folder where HTML document is saved. The value of the **ResourceFolderAlias** property is used to create URLs for all resources.

The following code example shows how to work with these properties:

{{< gist "aspose-words-gists" "c0df00d37081f41a7683339fd7ef66c1" "export-resources.cs" >}}

Using the [ResourceFolderAlias](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/) property, we can also specify the name of the folder used to construct URIs of all resources written into an HTML document. This is the simplest way to specify how URIs should be generated for all resource files. The same information can be specified for images and fonts separately via [ImagesFolderAlias](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/) and [FontsFolderAlias](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/) properties, respectively.

However, there is no individual property for CSS. The behavior of the **FontsFolder**, **FontsFolderAlias**, **ImagesFolder**, **ImagesFolderAlias** and **CssStyleSheetFileName** properties are not changed. Note that the **CssStyleSheetFileName** property is used both for specifying folder name and file name.

- **ResourceFolder** has lower priority than folders specified via **FontsFolder**, **ImagesFolder**, and **CssStyleSheetFileName**. If the folder specified in the **ResourceFolder** does not exist, it will be created automatically.
- **ResourceFolderAlias** has a lower priority than **FontsFolderAlias** and **ImagesFolderAlias**. If **ResourceFolderAlias** is empty, the value of the **ResourceFolder** property will be used to create resource URIs. If **ResourceFolderAlias** is set to "." (dot), resource URIs will only contain file names without specifying a path.

### Export Base64 Encoding Fonts Resources

Aspose.Words provides an ability to specify whether font resources should be embedded into HTML in Base64 encodings. To perform this, use the [ExportFontsAsBase64](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/exportfontsasbase64/) property – this is an extension of the [ExportFontResources](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/exportfontresources/) property. By default, its value is **false**, and fonts are written into separate files. But if this option is set to **true**, fonts will be embedded into the document's CSS in Base64 encoding. The **ExportFontsAsBase64** property only affects HTML format and does not affect EPUB and MHTML.

The following code example shows how to export Base64‑encoded fonts to HTML:

{{< gist "aspose-words-gists" "c0df00d37081f41a7683339fd7ef66c1" "export-fonts-as-base64.cs" >}}

## Specify Save Options when Conversion to EPUB

Aspose.Words allows to convert a Word document into EPUB format using default or custom save options. You can specify a number of options by passing an instance of [HtmlSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/htmlsaveoptions/) to the [Save](https://reference.aspose.com/words/net/aspose.words/document/save/#save/) method.

The following code example shows how to converts a Word document to EPUB with specifying some custom save options:

{{< gist "aspose-words-gists" "c0df00d37081f41a7683339fd7ef66c1" "split-document-by-headings.cs" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

------

## FAQ

1. **Q:** How do I convert a DOCX file to HTML using Aspose.Words for .NET?  
   **A:** Load the document with `Document doc = new Document("input.docx");` and call `doc.Save("output.html", SaveFormat.Html);`. The `Save` method automatically selects the HTML format based on the file extension.

2. **Q:** How can I preserve Word‑specific information (comments, headers, footers) when saving to HTML?  
   **A:** Set `HtmlSaveOptions options = new HtmlSaveOptions(); options.ExportRoundtripInformation = true;` and pass the options to `doc.Save("output.html", options);`. This embeds round‑trip data as custom CSS properties that Aspose.Words can read back.

3. **Q:** Where are images, fonts and CSS files written when I export a document to HTML?  
   **A:** Use `HtmlSaveOptions options = new HtmlSaveOptions(); options.ResourceFolder = "Resources";` to specify a folder. You can also set `options.ImagesFolder`, `options.FontsFolder`, and `options.CssStyleSheetFileName` for finer control.

4. **Q:** Can I embed fonts directly into the generated HTML instead of creating separate font files?  
   **A:** Yes. Set `options.ExportFontsAsBase64 = true;` (or `options.ExportFontResources = true` for separate files). This will encode the font data in Base64 and place it inside the CSS of the HTML document.

5. **Q:** How do I convert a document to EPUB and customize the output?  
   **A:** Create an `HtmlSaveOptions` instance for EPUB (`new HtmlSaveOptions(SaveFormat.Epub)`), configure any desired properties (e.g., `options.ExportImagesAsBase64 = true;`), and call `doc.Save("output.epub", options);`. The same options used for HTML apply to EPUB where applicable.