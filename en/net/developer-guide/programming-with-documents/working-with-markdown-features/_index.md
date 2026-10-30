---
title: Working with Markdown Features in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Markdown Features
linktitle: Working with Markdown Features
description: "How to implement Markdown features using C#. All the features are represented as corresponding styles or direct formatting."
type: docs
weight: 420
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-markdown-features/
timestamp: 2024-01-31-14-23-37
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with Markdown features when loading or saving Markdown.

{{% /alert %}}

This topic discusses how to implement Markdown features using Aspose.Words. Markdown is a simple way to format plain text that can easily be converted to HTML. Aspose.Words supports the following Markdown features:

- Headings
- Blockquotes
- Horizontal rules
- Bold emphasis
- Italic emphasis

The Markdown feature implementation mostly follows the `CommonMark` specification in Aspose.Words API and all the features are represented as corresponding styles or direct formatting. Which means that

- Bold and Italic are represented as `Font.Bold` and `Font.Italic`.
- Headings are paragraphs with Heading 1 - Heading 6 styles.
- Quotes are paragraphs with "Quote" in the style name.
- HorizontalRule is a paragraph with HorizontalRule shape.

{{% alert color="primary" %}}

There are nuances of translating Markdown to the Aspose.Words Document Object Model (DOM), described in the article [Translate Markdown to Document Object Model (DOM)](/words/net/translate-markdown-to-document-object-model/).

{{% /alert %}}

## Markdown Document with Emphases

This section demonstrates you how to produce a markdown document with emphases as given below:

{{< highlight csharp >}}
Markdown treats asterisks (*) and underscores (_) as indicators of emphasis.
You can write **bold** or *italic* text. 
You can also write ***BoldItalic*** text.
{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "19de942ef8827201c1dca99f76c59133" "emphases.cs" >}}

## Markdown Document with Headings

This section demonstrates you how to produce a markdown document with headings as given below:

{{< highlight csharp >}}
The following produces headings:
# Heading1
## Heading2
### Heading3
#### Heading4
##### Heading5
###### Heading6
# **Bold Heading1**
{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "0697355b7f872839932388d269ed6a63" "heading.cs" >}}

## Markdown Document with Block Quotes

This section demonstrates you how to produce a markdown document with block quotes as given below:

{{< highlight csharp >}}
> *Blockquote*
>> *1. Nested blockquote*
>>
>{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "0697355b7f872839932388d269ed6a63" "quote.cs" >}}

## Markdown Document with Horizontal Rule

This section demonstrates you how to produce a markdown document with Horizontal Rule as given below:

{{< highlight csharp >}}
Insert a horizontal rule shape into the document.
-----
{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "ad463bf5f128fe6e6c1485df3c046a4c" "insert-horizontal-rule.cs" >}}

## Reading a Markdown Document

The following code snippet shows you how to read a markdown document.

{{< gist "aspose-words-gists" "19de942ef8827201c1dca99f76c59133" "read-markdown-document.cs" >}}

## Specify Markdown Save Options

Aspose.Words API provides [MarkdownSaveOptions](https://reference.aspose.com/words/net/aspose.words.saving/markdownsaveoptions/) class to specify additional options while saving a document into the Markdown format.

The following code example demonstrated how to specify various Markdown save options.

{{< gist "aspose-words-gists" "51b4cb9c451832f23527892e19c7bca6" "images-folder.cs" >}}

## How to Align Content Inside the Table while Exporting into Markdown

Aspose.Words API provides [TableContentAlignment](https://reference.aspose.com/words/net/aspose.words.saving/markdownsaveoptions/tablecontentalignment/) enumeration which defines alignment directions to align contents in tables while exporting into the Markdown document. The following code example demonstrates how to align content inside the table.

{{< gist "aspose-words-gists" "19de942ef8827201c1dca99f76c59133" "markdown-table-content-alignment.cs" >}}

------

## FAQ

1. **Q:** How do I apply bold or italic formatting when generating Markdown with Aspose.Words?  
   **A:** Use the `Font.Bold` and `Font.Italic` properties on a `Run` or `Paragraph`. When the document is saved as Markdown, these properties are converted to `**bold**` or `*italic*` syntax automatically.

2. **Q:** Which style names are used for Markdown headings?  
   **A:** Headings are represented by the built‑in heading styles `Heading 1` through `Heading 6`. Setting a paragraph's `StyleIdentifier` to one of these styles will produce the corresponding `#` to `######` Markdown heading when saved.

3. **Q:** How can I control the appearance of tables when exporting to Markdown?  
   **A:** Set the `TableContentAlignment` property of `MarkdownSaveOptions` to `Left`, `Center`, or `Right`. This aligns the text inside each table cell in the generated Markdown table.

4. **Q:** What option should I use to include images in the saved Markdown file?  
   **A:** Use `MarkdownSaveOptions.ImagesFolder` to specify a folder where images will be written, and set `ImagesFolderAlias` if you need a different relative path. The generated Markdown will contain image links pointing to that folder.

5. **Q:** How do I read an existing Markdown file into an Aspose.Words `Document`?  
   **A:** Load the file with `Document doc = new Document("input.md");`. Aspose.Words parses the Markdown according to the CommonMark specification and creates the corresponding DOM, which you can then manipulate programmatically.