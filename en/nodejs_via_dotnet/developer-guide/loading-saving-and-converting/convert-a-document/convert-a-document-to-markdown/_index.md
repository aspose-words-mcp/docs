---
title: Convert a Document to Markdown
second_title: Aspose.Words for Node.js via .NET
articleTitle: Convert a Document to Markdown
linktitle: Convert a Document to Markdown
type: docs
description: "Convert a document in any supported load format to Markdown and vice versa using Node.js."
keywords: how to convert a document to markdown Node.js
weight: 40
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/convert-a-document-to-markdown/
aliases: [/nodejs/convert-a-document-to-markdown/]
timestamp: 2025-04-21-14-07-04
---

Markdown is a popular format used to markup text and its further converting to HTML, PDF, DOCX, or other formats. Many developers choose this format for writing documentation, preparing articles for publication on blogs, describing projects, and so on.

Markdown is so popular because it is easy to work with this format, as well as it can be quite simply converted to other formats. For this reason, Aspose.Words provides the ability to convert a document in [any supported load format](https://reference.aspose.com/words/nodejs-net/aspose.words/loadformat/) to Markdown and vice versa – Aspose.Words also supports most popular [save formats](https://reference.aspose.com/words/nodejs-net/aspose.words/saveformat/).

Now the functionality for working with the Markdown format is being actively developed to provide you with more opportunities for convenient and comfortable work with documents.

## Convert a Document

To convert a document to Markdown, you just need to load a document in any supported format or create a new one programmatically. Then you need to save the document to Markdown format.

The following code example shows how to convert DOCX to Markdown:

{{< gist "aspose-words-gists" "a2fee7fa3d8e5704ce24f041be9a4821" "docx-to-markdown.js" >}}

You can also specify the physical folder in which you want to save images when exporting a document to Markdown format. By default, Aspose.Words saves images in the same folder where the document file is saved, but you can override this behavior using the [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/markdownsaveoptions/imagesfolder/) property.

Specifying a folder via [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/markdownsaveoptions/imagesfolder/) is also useful if you save a document to a stream and Aspose.Words does not have a folder for saving images.

If the specified [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/markdownsaveoptions/imagesfolder/) does not exist, it will be created automatically.

The following code example shows how to specify a folder for images when saving a document to a stream:

{{< gist "aspose-words-gists" "a2fee7fa3d8e5704ce24f041be9a4821" "images-folder.js" >}}

## Specify Save Options when Converting to Markdown

Aspose.Words provides the ability to use the [MarkdownSaveOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/markdownsaveoptions/) class to work with advanced options when saving a document to Markdown format. Most properties are inheriting or overloading properties that already exist within other [aspose.words.saving](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/) classes. In addition to them, a number of properties that are specific for Markdown format have also been added. For example, the [tableContentAlignment](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/markdownsaveoptions/tablecontentalignment/) property to control the alignment of content in tables, or [imagesFolder](https://reference.aspose.com/words/nodejs-net/aspose.words.saving/markdownsaveoptions/imagesfolder/) to control where images are saved upon converting a document to Markdown format.

## Supported Markdown Features

Aspose.Words currently supports the following Markdown features, which mostly follow the `CommonMark` specification in the Aspose.Words API and are represented as appropriate styles or direct formatting:

* Headings are paragraphs with Heading 1 – Heading 6 styles
* Blockquotes are paragraphs with "Quote" in the style name
* IndentedCode are paragraphs with "IndentedCode" in the style name
* FencedCode are paragraphs with "FencedCode" in the style name
* InlineCode are runs with "InlineCode" in the `Font` style name
* Horizontal rules are paragraphs with the `HorizontalRule` shape
* Bold emphasis
* Italic emphasis
* StrikeThrough formatting
* Lists are numbered or bulleted paragraphs
* Tables are represented with the [Table](https://reference.aspose.com/words/nodejs-net/aspose.words/table/) class
* Links are represented as the [FieldHyperlink](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldhyperlink/) class

The following example shows how to create a document with some styles and save it to Markdown:

{{< gist "aspose-words-gists" "a2fee7fa3d8e5704ce24f041be9a4821" "supported-features.js" >}}

The result of this code example is shown below.

![markdown-example-aspose-words-net](markdown-example.png)

## Useful Tips

There are several nuances and interesting cases, having learned which you can work with Markdown files more flexibly and conveniently. For example, there is the ability to use:

* SetextHeading that allows you to create multi-line headings in Markdown, while regular headings in Markdown can only be single-line. SetextHeading is based on a "Heading N" style, and its level can only be 1 or 2. If N in "Heading N" is greater than or equal to 2, then the corresponding SetextHeading is based on "Heading 2", otherwise on "Heading 1".
* Different markers for the first level of bulleted lists ("-", "+" or "*", the default marker is “-”.) and different types of numbering for ordered lists ("." or ")", the default marker is ".").
