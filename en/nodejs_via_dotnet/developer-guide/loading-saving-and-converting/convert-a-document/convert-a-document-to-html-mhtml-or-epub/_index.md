---
title: Convert Document to HTML
second_title: Aspose.Words for Node.js via .NET
articleTitle: Convert a Document to HTML, MHTML or EPUB
linktitle: Convert a Document to HTML, MHTML or EPUB
description: "Convert a document from almost any format to HTML or MHTML, as well as to EPUB format using Node.js. You can also specify save options for managing the output document."
type: docs
weight: 20
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/convert-a-document-to-html-mhtml-or-epub/
aliases: [/nodejs/convert-a-document-to-html-mhtml-or-epub/]
timestamp: 2025-04-21-14-07-04
---

Documents in HTML and MHTML flow-layout formats are also very popular and can be used on any web platform. For that reason, converting documents to HTML and MHTML is an important feature of Aspose.Words.

EPUB (short for "Electronic Publication") is an HTML-based format commonly used for electronic book distribution. This format is fully supported in Aspose.Words for exporting electronic books that are compatible with most reading devices.

## Convert a Document

For simple conversion to HTML, MHTML, or EPUB, one of the [save](https://reference.aspose.com/words/nodejs-net/aspose.words/document/save/) method overloads is used. You can save the document to a file or stream and explicitly set the output document save format or define it from the file name extension.

The following example shows how to convert DOCX to HTML with specifying a save format:

{{< highlight js >}}
const aw = require('@aspose/words');

// Load the document from disk.
var doc = new aw.Document("Test File.docx");

// Save the document into HTML.
doc.save("Document", aw.SaveFormat.Html);
{{< /highlight >}}

To convert a document to MHTML or EPUB, use [SaveFormat.Mhtml](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/#mhtml) or [SaveFormat.Epub](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/#epub) respectively.

## Convert a Document with Round-trip Information

The HTML format does not support many Microsoft Word features, and if we need to restore a document model as close to the original as possible, we need to save some extra information within the HTML file. Such information is also called "round-trip information". For this purpose, Aspose.Words provides an ability to export round-trip information when saving to HTML, MHTML, or EPUB using the **exportRoundtripInformation** property. Saving the round-trip information allows to restore document properties such as tabs, comments, headers, and footers during the loading documents of the listed formats back into a [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/) object.

The default value is *true* for HTML and *false* for MHTML and EPUB:

- When *true*, the round-trip information is exported as - aw - * CSS properties of the corresponding HTML elements
- When *false*, there is no round-trip information to be output into produced files

The following code example shows how to export round-trip information when converting a document from DOCX into HTML:

{{< gist "aspose-words-gists" "e4b272992a7c8fafdd7ff42f8c2de379" "export-roundtrip-information.js" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/blob/main/Data/Rendering.docx).

{{% /alert %}}

## Specify Save Options when Conversion to HTML

Aspose.Words allows to convert a Word document to HTML using default or custom save options. Few examples of custom save options are described below.

### Specify a Folder for Saving Resources

Using Aspose.Words we can specify a physical folder where all resources, such as images, fonts, and external CSS, are saved when a document is converted to HTML. By default, this is an empty string.

Specifying the [resourceFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolder/) property is the simplest way to set the folder where all resources should be written. We can use individual properties, such as [fontsFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolder/) which saves fonts to the specified folder and [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolder/) which saves images to a specified folder. When a relative path is specified, [fontsFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolder/) and [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolder/) refer to the folder where the code assembly is located, [resourceFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolder/) and [cssStyleSheetFileName](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/cssstylesheetfilename/) refer to the output folder where the HTML document is located.

In this example, [resourceFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolder/) specifies the relative path. This path refers to the output folder where HTML document is saved. The value of the [resourceFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/) property is used to create URLs for all resources.

The following code example shows how to work with these properties:

{{< gist "aspose-words-gists" "e4b272992a7c8fafdd7ff42f8c2de379" "export-resources.js" >}}

Using the [resourceFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/) property, we can also specify the name of the folder used to construct URIs of all resources written into an HTML document. This is the simplest way to specify how URIs should be generated for all resource files. The same information can be specified for images and fonts separately via [imagesFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/) and [fontsFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/) properties, respectively.

However, there is no individual property for CSS. The behavior of the [fontsFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolder/), [fontsFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/), [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolder/), [imagesFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/) and [cssStyleSheetFileName](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/cssstylesheetfilename/) properties are not changed. Note that the [cssStyleSheetFileName](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/cssstylesheetfilename/) property is used both for specifying folder name and file name.

- [resourceFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolder/) has lower priority than folders specified via [fontsFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolder/), [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolder/), and [cssStyleSheetFileName](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/cssstylesheetfilename/). If the folder specified in the [resourceFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolder/) does not exist, it will be created automatically.
- [resourceFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/) has a lower priority than [fontsFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/) and [imagesFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/). If [resourceFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/) is empty, the value of the [resourceFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolder/) property will be used to create resource URIs. If [resourceFolderAlias](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/) is set to "." (dot), resource URIs will only contain file names without specifying a path.

### Export Base64 Encoding Fonts Resources

Aspose.Words provides an ability to specify whether font resources should be embedded into HTML in Base64 encodings. To perform this, use the [exportFontsAsBase64](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/exportfontsasbase64/) property – this is an extension of the [exportFontResources](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/exportfontresources/) property. By default, its value is *false*, and fonts are written into separate files. But if this option is set to *true*, fonts will be embedded into the document's CSS in Base64 encoding. The [exportFontsAsBase64](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/exportfontsasbase64/) property only affects HTML format and does not affect EPUB and MHTML.

The following code example shows how to export Base64-encoded fonts to HTML:

{{< gist "aspose-words-gists" "e4b272992a7c8fafdd7ff42f8c2de379" "export-fonts-as-base64.js" >}}

## Specify Save Options when Conversion to EPUB

Aspose.Words allows to convert a Word document into EPUB format using default or custom save options. You can specify a number of options by passing an instance of [HtmlSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/htmlsaveoptions/) to the [save](https://reference.aspose.com/words/nodejs-net/aspose.words/document/save/) method.

The following code example shows how to converts a Word document to EPUB with specifying some custom save options:

{{< highlight js >}}
const aw = require('@aspose/words');

// Load the document from disk.
var doc = new aw.Document("Rendering.docx");

// Create a new instance of HtmlSaveOptions. This object allows us to set options that control
// How the output document is saved.
var saveOptions = new aw.Saving.HtmlSaveOptions();

// Specify the desired encoding.
saveOptions.encoding = "utf-8"

// Specify at what elements to split the internal HTML at. This creates a new HTML within the EPUB 
// which allows you to limit the size of each HTML part. This is useful for readers which cannot read 
// HTML files greater than a certain size e.g 300kb.
saveOptions.documentSplitCriteria = aw.Saving.DocumentSplitCriteria.HeadingParagraph;

// Specify that we want to export document properties.
saveOptions.exportDocumentProperties = true;

// Specify that we want to save in EPUB format.
saveOptions.saveFormat = aw.SaveFormat.Epub;

// Export the document as an EPUB file.
doc.save("Document.EpubConversion_out.epub", saveOptions)
{{< /highlight >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/blob/main/Data/Rendering.docx).

{{% /alert %}}

------ 

## FAQ

1. **Q:** How do I convert a DOCX file to HTML with Aspose.Words for Node.js?  
   **A:** Load the document using `new aw.Document("input.docx")` and call `doc.save("output.html", aw.SaveFormat.Html);`. The `SaveFormat` enum tells the API which format to produce.

2. **Q:** How can I store images, fonts, and CSS files in a separate folder when saving to HTML?  
   **A:** Create an `HtmlSaveOptions` object, set `resourceFolder`, `fontsFolder`, and/or `imagesFolder` to the desired paths, then pass the options to `doc.save`. Example:  
   ```js
   var options = new aw.Saving.HtmlSaveOptions();
   options.resourceFolder = "./html_resources";
   doc.save("output.html", options);
   ```

3. **Q:** Is it possible to embed fonts directly into the generated HTML?  
   **A:** Yes. Set `options.exportFontsAsBase64 = true;` on an `HtmlSaveOptions` instance before saving. The fonts will be encoded in Base64 and placed inside the CSS of the HTML file.

4. **Q:** How can I preserve Word features such as comments, headers, and footers during HTML conversion?  
   **A:** Enable round‑trip information by setting `options.exportRoundtripInformation = true;` (the default for HTML). This stores extra data in the HTML that Aspose.Words can read back to reconstruct those Word features.

5. **Q:** What is the recommended way to convert a document to EPUB format?  
   **A:** Use `HtmlSaveOptions`, set `saveOptions.saveFormat = aw.SaveFormat.Epub;` and configure any additional options (encoding, split criteria, etc.), then call `doc.save("output.epub", saveOptions);`. This produces a valid EPUB file with the specified settings.