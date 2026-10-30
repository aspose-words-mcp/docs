---
title: Convert a Document to HTML, MHTML or EPUB in Java
second_title: Aspose.Words for Java
articleTitle: Convert a Document to HTML, MHTML or EPUB
linktitle: Convert a Document to HTML, MHTML or EPUB
description: "Convert a document from almost any format to HTML or MHTML, as well as to EPUB format using Java. You can also specify save options for managing the output document."
type: docs
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/convert-a-document-to-html-mhtml-or-epub/
timestamp: 2024-10-21-08-52-03
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to convert Word documents to HTML, MHTML, or EPUB, and describes the key options that influence layout and formatting during export.

{{% /alert %}}

Documents in HTML and MHTML flow-layout formats are also very popular and can be used on any web platform. For that reason, converting documents to HTML and MHTML is an important feature of Aspose.Words.

EPUB (short for "Electronic Publication") is an HTML-based format commonly used for electronic book distribution. This format is fully supported in Aspose.Words for exporting electronic books that are compatible with most reading devices.

## Convert a Document

For simple conversion to HTML, MHTML, or EPUB, one of the [save()](https://reference.aspose.com/words/java/com.aspose.words/document/#save-java.lang.String-int) method overloads is used. You can save the document to a file or stream and explicitly set the output document save format or define it from the file name extension.

The following example shows how to convert DOCX to HTML with specifying a save format:

{{< gist "aspose-words-gists" "c2ec8aa36ef37670eceec8da5c612b86" "docx-to-html.java" >}}

To convert a document to MHTML or EPUB, use `SaveFormat.MHTML` or `SaveFormat.EPUB` respectively.

## Convert a Document with Round-trip Information

The HTML format does not support many Microsoft Word features, and if we need to restore a document model as close to the original as possible, we need to save some extra information within the HTML file. Such information is also called "round-trip information". For this purpose, Aspose.Words provides an ability to export round-trip information when saving to HTML, MHTML, or EPUB using the [getExportRoundtripInformation()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getExportRoundtripInformation) property. Saving the round-trip information allows restoring document properties such as tabs, comments, headers, and footers during the loading documents of the listed formats back into a **Document** object.

The default value is **true** for HTML and **false** for MHTML and EPUB:

- When **true**, the round-trip information is exported as - aw - * CSS properties of the corresponding HTML elements
- When **false**, there is no round-trip information to be output into produced files

The following code example shows how to export round-trip information when converting a document from DOCX into HTML:

{{< gist "aspose-words-gists" "c2ec8aa36ef37670eceec8da5c612b86" "export-roundtrip-information.java" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

## Specify Save Options when Conversion to HTML

Aspose.Words allows to convert a Word document to HTML using default or custom save options. Few examples of custom save options are described below.

### Specify a Folder for Saving Resources

Using Aspose.Words we can specify a physical folder where all resources, such as images, fonts, and external CSS, are saved when a document is converted to HTML. By default, this is an empty string.

Specifying the [getResourceFolder()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getResourceFolder) property is the simplest way to set the folder where all resources should be written. We can use individual properties, such as [getFontsFolder()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getFontsFolder) which saves fonts to the specified folder and [getImagesFolder()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getImagesFolder) which saves images to a specified folder. When a relative path is specified, **getFontsFolder()** and **getImagesFolder()** refer to the folder where the code assembly is located, **getResourceFolder()** and [getCssStyleSheetFileName()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getCssStyleSheetFileName) refer to the output folder where the HTML document is located.

In this example, **getResourceFolder()** specifies the relative path. This path refers to the output folder where the HTML document is saved. The value of the **getResourceFolderAlias()** property is used to create URLs for all resources.

The following code example shows how to work with these properties:

{{< gist "aspose-words-gists" "c2ec8aa36ef37670eceec8da5c612b86" "export-resources.java" >}}

Using the [getResourceFolderAlias()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getResourceFolderAlias) property, we can also specify the name of the folder used to construct URIs of all resources written into an HTML document. This is the simplest way to specify how URIs should be generated for all resource files. The same information can be specified for images and fonts separately via [getImagesFolderAlias()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getImagesFolderAlias) and [getFontsFolderAlias()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getFontsFolderAlias) properties, respectively.

However, there is no individual property for CSS. The behavior of the **getFontsFolder()**, **getFontsFolderAlias()**, **getImagesFolder()**, **getImagesFolderAlias()** and **getCssStyleSheetFileName()** properties are not changed. Note that the **getCssStyleSheetFileName()** property is used both for specifying folder name and file name.

- **getResourceFolder()** has lower priority than folders specified via **getFontsFolder()**, **getImagesFolder()**, and **getCssStyleSheetFileName()**. If the folder specified in the **getResourceFolder()** does not exist, it will be created automatically.
- **getResourceFolderAlias()** has a lower priority than **getFontsFolderAlias()** and **getImagesFolderAlias()**. If **getResourceFolderAlias()** is empty, the value of the **getResourceFolder()** property will be used to create resource URIs. If **getResourceFolderAlias()** is set to "." (dot), resource URIs will only contain file names without specifying a path.

### Export Base64 Encoding Fonts Resources

Aspose.Words provides an ability to specify whether font resources should be embedded into HTML in Base64 encodings. To perform this, use the [getExportFontsAsBase64()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getExportFontsAsBase64) property – this is an extension of the [getExportFontResources()](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/#getExportFontResources) property. By default, its value is **false**, and fonts are written into separate files. But if this option is set to **true**, fonts will be embedded into the document's CSS in Base64 encoding. The **getExportFontsAsBase64()** property only affects HTML format and does not affect EPUB and MHTML.

The following code example shows how to export Base64-encoded fonts to HTML:

{{< gist "aspose-words-gists" "c2ec8aa36ef37670eceec8da5c612b86" "export-fonts-as-base64.java" >}}

## Specify Save Options when Conversion to EPUB

Aspose.Words allows converting a Word document into EPUB format using default or custom save options. You can specify a number of options by passing an instance of [HtmlSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/htmlsaveoptions/) to the [save()](https://reference.aspose.com/words/java/com.aspose.words/document/#save-java.lang.String-com.aspose.words.SaveOptions) method.

The following code example shows how to converts a Word document to EPUB with specifying some custom save options:

{{< gist "aspose-words-gists" "c2ec8aa36ef37670eceec8da5c612b86" "split-document-by-headings.java" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

------ 

## FAQ

1. **Q:** How can I convert a DOCX file to HTML using Aspose.Words for Java?  
   **A:** Load the document with `Document document = new Document("input.docx");` and call `document.save("output.html", SaveFormat.HTML);`. You can also pass an `HtmlSaveOptions` instance to customize the output.

2. **Q:** How do I embed fonts directly into the generated HTML file?  
   **A:** Set `HtmlSaveOptions options = new HtmlSaveOptions(); options.setExportFontsAsBase64(true);` before saving. This embeds the font files as Base64 strings inside the CSS, eliminating external font files.

3. **Q:** Where can I control the folder where images and other resources are saved during HTML conversion?  
   **A:** Use `HtmlSaveOptions` properties such as `setResourceFolder("resources")`, `setImagesFolder("resources/images")`, and `setFontsFolder("resources/fonts")`. These properties define the physical locations for the exported resources.

4. **Q:** How can I preserve Word features like comments, headers, and footers when converting to HTML?  
   **A:** Enable round‑trip information by setting `options.setExportRoundtripInformation(true);`. This adds special `aw-*` CSS attributes that allow the document to be re‑loaded with those features intact.

5. **Q:** What is the simplest way to convert a document to EPUB format?  
   **A:** Call `document.save("output.epub", SaveFormat.EPUB);`. For advanced control, pass an `HtmlSaveOptions` object to the `save` method and specify EPUB‑specific options.