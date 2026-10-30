---
title: Convert a Document to Markdown
second_title: Aspose.Words for Python via .NET
articleTitle: Convert a Document to Markdown
linktitle: Convert a Document to Markdown
type: docs
description: "Convert a document in any supported load format to Markdown and vice versa using Python."
keywords: how to convert a document to markdown python
weight: 40
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/convert-a-document-to-markdown/
aliases: [/python/convert-a-document-to-markdown/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to use Aspose.Words for Python via .NET to convert documents between supported formats and Markdown, including code examples, save options, and supported Markdown features.
{{% /alert %}}

Markdown is a popular format used to markup text and its further converting to HTML, PDF, DOCX, or other formats. Many developers choose this format for writing documentation, preparing articles for publication on blogs, describing projects, and so on.

Markdown is so popular because it is easy to work with this format, as well as it can be quite simply converted to other formats. For this reason, Aspose.Words provides the ability to convert a document in [any supported load format](https://reference.aspose.com/words/python-net/aspose.words/loadformat/) to Markdown and vice versa – Aspose.Words also supports most popular [save formats](https://reference.aspose.com/words/python-net/aspose.words/saveformat/).

Now the functionality for working with the Markdown format is being actively developed to provide you with more opportunities for convenient and comfortable work with documents.

## Convert a Document

To convert a document to Markdown, you just need to load a document in any supported format or create a new one programmatically. Then you need to save the document to Markdown format.

The following code example shows how to convert DOCX to Markdown:

{{< gist "aspose-words-gists" "461290170d82b0922d265fa7bc854942" "docx-to-markdown.py" >}}

You can also specify the physical folder in which you want to save images when exporting a document to Markdown format. By default, Aspose.Words saves images in the same folder where the document file is saved, but you can override this behavior using the [images_folder](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/images_folder/) property.

Specifying a folder via **images_folder** is also useful if you save a document to a stream and Aspose.Words does not have a folder for saving images.

If the specified **images_folder** does not exist, it will be created automatically.

The following code example shows how to specify a folder for images when saving a document to a stream:

{{< gist "aspose-words-gists" "461290170d82b0922d265fa7bc854942" "images-folder.py" >}}

## Specify Save Options when Converting to Markdown

Aspose.Words provides the ability to use the [MarkdownSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/) class to work with advanced options when saving a document to Markdown format. Most properties are inheriting or overloading properties that already exist within other [aspose.words.saving](https://reference.aspose.com/words/python-net/aspose.words.saving/) Namespace classes. In addition to them, a number of properties that are specific for Markdown format have also been added. For example, the [table_content_alignment](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/table_content_alignment/) property to control the alignment of content in tables, or [images_folder](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/images_folder/) and [images_folder](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/images_folder/) to control how images are saved upon converting a document to Markdown format.

## Supported Markdown Features

Aspose.Words currently supports the following Markdown features, which mostly follow the `CommonMark` specification in the Aspose.Words API and are represented as appropriate styles or direct formatting:

* Headings are paragraphs with Heading 1 – Heading 6 styles
* Blockquotes are paragraphs with “Quote” in the style name
* IndentedCode are paragraphs with "IndentedCode" in the style name
* FencedCode are paragraphs with "FencedCode" in the style name
* InlineCode are runs with "InlineCode" in the `Font` style name
* Horizontal rules are paragraphs with the `HorizontalRule` shape
* Bold emphasis
* Italic emphasis
* StrikeThrough formatting
* Lists are numbered or bulleted paragraphs
* Tables are represented with the `Table` class
* Links are represented as the `FieldHyperlink` class

The following example shows how to create a document with some styles and save it to Markdown:

{{< gist "aspose-words-gists" "461290170d82b0922d265fa7bc854942" "supported-features.py" >}}

The result of this code example is shown below.

![markdown-example-aspose-words-python](markdown-example.png)

## Useful Tips

There are several nuances and interesting cases, having learned which you can work with Markdown files more flexibly and conveniently. For example, there is the ability to use:

* SetextHeading that allows you to create multi-line headings in Markdown, while regular headings in Markdown can only be single-line. SetextHeading is based on a "Heading N" style, and its level can only be 1 or 2. If N in "Heading N" is greater than or equal to 2, then the corresponding SetextHeading is based on "Heading 2", otherwise on "Heading 1".
* Different markers for the first level of bulleted lists ("-", "+" or "*", the default marker is “-”.) and different types of numbering for ordered lists ("." or ")", the default marker is "."). 

## FAQ

1. **Q:** How do I convert a document to Markdown using Aspose.Words for Python via .NET?  
   **A:** Load the source document with `doc = aw.Document("source.docx")` and then call `doc.save("output.md", aw.SaveFormat.MARKDOWN)`. The API automatically handles the conversion based on the file extensions.

2. **Q:** How can I control where images are saved when exporting to Markdown?  
   **A:** Create a `MarkdownSaveOptions` object, set its `images_folder` property to the desired path, and pass the options to `save`. Example:  
   ```python
   options = aw.saving.MarkdownSaveOptions()
   options.images_folder = "C:/ExportedImages"
   doc.save("output.md", options)
   ```

3. **Q:** Is there a way to adjust the alignment of tables in the generated Markdown?  
   **A:** Yes. Use the `table_content_alignment` property of `MarkdownSaveOptions`. Set it to `aw.saving.TableContentAlignment.LEFT`, `CENTER`, or `RIGHT` before saving.

4. **Q:** Which heading styles are recognized when converting to Markdown?  
   **A:** Paragraphs styled with Heading 1 through Heading 6 are converted to Markdown headings (`#` to `######`). For multi‑line headings you can use the `SetextHeading` style, which maps to the Setext syntax.

5. **Q:** Can I convert a Markdown file back to DOCX or PDF?  
   **A:** Absolutely. Load the Markdown file using `aw.LoadFormat.MARKDOWN` and then save it to any supported format, e.g., `doc.save("output.docx", aw.SaveFormat.DOCX)` or `doc.save("output.pdf", aw.SaveFormat.PDF)`.