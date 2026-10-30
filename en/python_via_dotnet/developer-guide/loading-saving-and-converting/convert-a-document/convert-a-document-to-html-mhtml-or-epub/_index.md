---
title: Convert Document to HTML
second_title: Aspose.Words for Python via .NET
articleTitle: Convert a Document to HTML, MHTML or EPUB
linktitle: Convert a Document to HTML, MHTML or EPUB
description: "Convert a document from almost any format to HTML or MHTML, as well as to EPUB format using Python. You can also specify save options for managing the output document."
type: docs
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/convert-a-document-to-html-mhtml-or-epub/
aliases: [/python/convert-a-document-to-html-mhtml-or-epub/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to convert Word documents to HTML, MHTML, or EPUB, and explains how to configure save options such as round‑trip information, resource folders, and font embedding.
{{% /alert %}}

Documents in HTML and MHTML flow-layout formats are also very popular and can be used on any web platform. For that reason, converting documents to HTML and MHTML is an important feature of Aspose.Words.

EPUB (short for "Electronic Publication") is an HTML-based format commonly used for electronic book distribution. This format is fully supported in Aspose.Words for exporting electronic books that are compatible with most reading devices.

## Convert a Document

For simple conversion to HTML, MHTML, or EPUB, one of the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method overloads is used. You can save the document to a file or stream and explicitly set the output document save format or define it from the file name extension.

The following example shows how to convert DOCX to HTML with specifying a save format:

{{< gist "aspose-words-gists" "c5d01a71f65e540e5e77650b846b24cc" "docx-to-html.py" >}}

To convert a document to MHTML or EPUB, use `aspose.words.SaveFormat.MHTML` or `aspose.words.SaveFormat.EPUB` respectively.

## Convert a Document with Round-trip Information

The HTML format does not support many Microsoft Word features, and if we need to restore a document model as close to the original as possible, we need to save some extra information within the HTML file. Such information is also called "round-trip information". For this purpose, Aspose.Words provides an ability to export round-trip information when saving to HTML, MHTML, or EPUB using the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) property. Saving the round-trip information allows to restore document properties such as tabs, comments, headers, and footers during the loading documents of the listed formats back into a **Document** object.

The default value is *True* for HTML and *False* for MHTML and EPUB:

- When **true**, the round-trip information is exported as - aw - * CSS properties of the corresponding HTML elements
- When **false**, there is no round-trip information to be output into produced files

The following code example shows how to export round-trip information when converting a document from DOCX into HTML:

{{< gist "aspose-words-gists" "c5d01a71f65e540e5e77650b846b24cc" "export-roundtrip-information.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

## Specify Save Options when Conversion to HTML

Aspose.Words allows to convert a Word document to HTML using default or custom save options. Few examples of custom save options are described below.

### Specify a Folder for Saving Resources

Using Aspose.Words we can specify a physical folder where all resources, such as images, fonts, and external CSS, are saved when a document is converted to HTML. By default, this is an empty string.

Specifying the [resource_folder](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/resource_folder/) property is the simplest way to set the folder where all resources should be written. We can use individual properties, such as [fonts_folder](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/fonts_folder/) which saves fonts to the specified folder and [images_folder](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/images_folder/) which saves images to a specified folder. When a relative path is specified, **fonts_folder** and **images_folder** refer to the current working directory, **resource_folder** and [css_style_sheet_file_name](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/css_style_sheet_file_name/) refer to the output folder where the HTML document is located.

In this example, **resource_folder** specifies the relative path. This path refers to the output folder where HTML document is saved. The value of the **resource_folder_alias** property is used to create URLs for all resources.

The following code example shows how to work with these properties:

{{< gist "aspose-words-gists" "c5d01a71f65e540e5e77650b846b24cc" "export-resources.py" >}}

Using the [resource_folder_alias](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/resource_folder_alias/) property, we can also specify the name of the folder used to construct URIs of all resources written into an HTML document. This is the simplest way to specify how URIs should be generated for all resource files. The same information can be specified for images and fonts separately via [images_folder_alias](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/images_folder_alias/) and [fonts_folder_alias](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/fonts_folder_alias/) properties, respectively.

However, there is no individual property for CSS. The behavior of the **fonts_folder**, **fonts_folder_alias**, **images_folder**, **images_folder_alias** and **css_style_sheet_file_name** properties are not changed. Note that the **css_style_sheet_file_name** property is used both for specifying folder name and file name.

- **resource_folder** has lower priority than folders specified via **fonts_folder**, **images_folder**, and **css_style_sheet_file_name**. If the folder specified in the **resource_folder** does not exist, it will be created automatically.
- **resource_folder_alias** has a lower priority than **fonts_folder_alias** and **images_folder_alias**. If **resource_folder_alias** is empty, the value of the **resource_folder** property will be used to create resource URIs. If **resource_folder_alias** is set to "." (dot), resource URIs will only contain file names without specifying a path.

### Export Base64 Encoding Fonts Resources

Aspose.Words provides an ability to specify whether font resources should be embedded into HTML in Base64 encodings. To perform this, use the [export_fonts_as_base64](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/export_fonts_as_base64/) property – this is an extension of the [export_font_resources](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/export_font_resources/) property. By default, its value is **false**, and fonts are written into separate files. But if this option is set to **true**, fonts will be embedded into the document's CSS in Base64 encoding. The **export_fonts_as_base64** property only affects HTML format and does not affect EPUB and MHTML.

The following code example shows how to export Base64‑encoded fonts to HTML:

{{< gist "aspose-words-gists" "c5d01a71f65e540e5e77650b846b24cc" "export-fonts-as-base64.py" >}}

## Specify Save Options when Conversion to EPUB

Aspose.Words allows to convert a Word document into EPUB format using default or custom save options. You can specify a number of options by passing an instance of [HtmlSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/) to the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method.

The following code example shows how to converts a Word document to EPUB with specifying some custom save options:

{{< gist "aspose-words-gists" "c5d01a71f65e540e5e77650b846b24cc" "split-document-by-headings.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

## FAQ

1. **Q:** How can I change the folder where images, fonts and other resources are saved when converting to HTML?  
   **A:** Use the `resource_folder` property of `HtmlSaveOptions`. You can also set `fonts_folder`, `images_folder` and `css_style_sheet_file_name` individually. If the specified folder does not exist, Aspose.Words creates it automatically.

2. **Q:** How do I embed fonts directly into the generated HTML file?  
   **A:** Set `export_fonts_as_base64` to `True` on an `HtmlSaveOptions` instance. This causes fonts to be written as Base64‑encoded data URIs inside the CSS of the HTML output.

3. **Q:** What is “round‑trip information” and when should I enable it?  
   **A:** Round‑trip information stores Word‑specific data (such as comments, headers, footers, and tab settings) in the HTML so that loading the HTML back into a `Document` restores those features. It is enabled by default for HTML (`export_roundtrip_information = True`). Disable it only if you need a cleaner HTML without extra CSS.

4. **Q:** Can I convert a PDF file to HTML using Aspose.Words?  
   **A:** Yes. First, load PDF files to convert them to HTML. Then save the resulting document as HTML.

5. **Q:** How do I customize the EPUB conversion, for example to split the content by headings?  
   **A:** Create an `HtmlSaveOptions` object, set `document_split_criteria` to `aw.saving.DocumentSplitCriteria.HEADING_PARAGRAPH`, configure any other options (encoding, export properties, etc.), set `save_format` to `aw.SaveFormat.EPUB`, and pass the options to `Document.save`. This splits the EPUB into separate HTML files at each heading level.