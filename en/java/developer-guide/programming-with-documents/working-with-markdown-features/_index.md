---
title: Working with Markdown Features in Java
second_title: Aspose.Words for Java
articleTitle: Working with Markdown Features
linktitle: Working with Markdown Features
description: "How to implement Markdown features using Java. All the features are represented as corresponding styles or direct formatting."
type: docs
weight: 420
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-markdown-features/
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

- Bold and Italic are accessed via `font.getBold()` / `font.setBold(true)` and `font.getItalic()` / `font.setItalic(true)`.
- Headings are paragraphs with Heading 1 – Heading 6 styles.
- Quotes are paragraphs whose style name contains "Quote".
- HorizontalRule is a paragraph that contains a HorizontalRule shape.

{{% alert color="primary" %}}

There are nuances of translating Markdown to the Aspose.Words Document Object Model (DOM), described in the article [Translate Markdown to Document Object Model (DOM)](/words/java/translate-markdown-to-document-object-model/).

{{% /alert %}}

## Markdown Document with Emphases

This section demonstrates you how to produce a markdown document with emphases as given below:

{{< highlight csharp >}}
Markdown treats asterisks (*) and underscores (_) as indicators of emphasis.
You can write **bold** or *italic* text. 
You can also write ***BoldItalic*** text.
{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "50b2b6a8785c07713e7c09d772e9a396" "emphases.java" >}}

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

{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "heading.java" >}}

## Markdown Document with Block Quotes

This section demonstrates you how to produce a markdown document with block quotes as given below:

{{< highlight csharp >}}
> *Blockquote*
>> *1. Nested blockquote*
>>
>{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "quote.java" >}}

## Markdown Document with Horizontal Rule

This section demonstrates you how to produce a markdown document with Horizontal Rule as given below:

{{< highlight csharp >}}
Insert a horizontal rule shape into the document.
-----
{{< /highlight >}}

The following code snippet can be used to produce the above given markdown document.

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "insert-horizontal-rule.java" >}}

## Reading a Markdown Document

The following code snippet shows you how to read a markdown document.

{{< gist "aspose-words-gists" "50b2b6a8785c07713e7c09d772e9a396" "read-markdown-document.java" >}}

## Specify Markdown Save Options

Aspose.Words API provides [MarkdownSaveOptions](https://reference.aspose.com/words/java/com.aspose.words/markdownsaveoptions/) class to specify additional options while saving a document into the Markdown format.

The following code example demonstrated how to specify various Markdown save options.

{{< gist "aspose-words-gists" "642767bbe8d8bec8eab080120b707990" "images-folder.java" >}}

## How to Align Content Inside the Table while Exporting into Markdown

Aspose.Words API provides [TableContentAlignment](https://reference.aspose.com/words/java/com.aspose.words/tablecontentalignment/) enumeration which defines alignment directions to align contents in tables while exporting into the Markdown document. The following code example demonstrates how to align content inside the table.

{{< gist "aspose-words-gists" "50b2b6a8785c07713e7c09d772e9a396" "markdown-table-content-alignment.java" >}}

## FAQ

1. **Q:** Which Markdown elements are currently supported by Aspose.Words for Java?  
   **A:** Aspose.Words for Java implements the CommonMark subset and supports headings (levels 1‑6), bold and italic emphasis, block quotes, horizontal rules, and tables (when using `TableContentAlignment`). Each element is mapped to a corresponding Word style or direct formatting.

2. **Q:** How can I convert an existing Markdown file to a Word document (.docx) using Java?  
   **A:** Load the Markdown file with `MarkdownLoadOptions` and then save it as a DOCX. Example:  
   ```java
   Document doc = new Document("input.md", new MarkdownLoadOptions());
   doc.save("output.docx");
   ```  
   The load options let you control how unknown tags are handled.

3. **Q:** Can I preserve custom styles or additional formatting when converting Markdown to Word?  
   **A:** Partly. `MarkdownLoadOptions` has no style-mapping methods. When Markdown is loaded, each feature becomes a corresponding style or direct formatting, for example `Heading 1`…`Heading 6` for headings and a `Quote` style for block quotes (see [Translate Markdown to Document Object Model](/words/java/translate-markdown-to-document-object-model/)). After loading, you can change these styles in `doc.getStyles()` or apply your own styles to the paragraphs.

4. **Q:** How do I export a Word document to Markdown while controlling the alignment of table contents?  
   **A:** Use `MarkdownSaveOptions` together with the `TableContentAlignment` enumeration. Set the desired alignment with `MarkdownSaveOptions.setTableContentAlignment` (e.g., `TableContentAlignment.CENTER`) before calling `save`. This ensures table cells are rendered with the chosen alignment in the resulting Markdown file.

5. **Q:** Is it possible to enable additional CommonMark extensions, such as task lists or footnotes, during conversion?  
   **A:** Aspose.Words for Java follows the core CommonMark specification. Extensions like task lists or footnotes are not natively supported, but you can preprocess the Markdown (e.g., replace extension syntax with standard Markdown) before loading it with `MarkdownLoadOptions`.