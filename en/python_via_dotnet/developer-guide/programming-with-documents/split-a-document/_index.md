---
title: Split a Document in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Split a Document
linktitle: Split a Document
description: "Split a document into several files using Python. Use the split feature to effectively split a document by headings or sections, as well as by pages or by page ranges."
type: docs
weight: 90
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/split-a-document/
aliases: [/python/split-a-document/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to split a document into multiple files using Aspose.Words for Python via .NET, covering splitting by headings, sections, pages, and page ranges, and includes code examples for each method.

{{% /alert %}}

*Splitting* or *split a document* is the process of breaking a large document into a greater number of smaller files. There are various reasons to split a file. For example, you only need some pages from a specific document and not the entire one. Or for privacy reasons, you want to share only some parts of a document with others. With the splitting feature, you can get only the required parts of the document and do the necessary actions with them, for example, to mark up, save, or send.

Aspose.Words provides you with an efficient way to split one document into multiple documents by headings or sections. You can also split a document by pages or by page ranges. Both splitting options will be described in this article.

To split a document into smaller files using Aspose.Words, you need to follow these steps:

1. Load the document in any supported format.
1. Split the document.
1. Save the output documents.

After you split a document, you will be able to open all the output documents that will start with the required pages, text, etc.

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online document splitter](https://products.aspose.app/words/splitter).

{{% /alert %}}

## Split a Document Using Different Criteria {#split-a-document-using-different-criteria}

Aspose.Words allows you to split EPUB or HTML documents into chapters according to various criteria. In the process, the style and layout of the source document are preserved for the output documents.

You can specify criteria using the [DocumentSplitCriteria](https://reference.aspose.com/words/python-net/aspose.words.saving/documentsplitcriteria/) enumeration. So you can divide a document into chapters using one of the following criteria or combine more than one criteria together:

- heading paragraph,
- section break,
- column break,
- page break.

When saving the output to HTML, Aspose.Words save each individual chapter as a separate HTML file. As a result, the document will be split into multiple HTML files. When saving the output to EPUB, Aspose.Words save the result in a single EPUB file regardless of the `DocumentSplitCriteria` value you used. So, using DocumentSplitCriteria for EPUB documents only affects the appearance of their content in reader applications: content will be divided into chapters and the document will no longer appear continuous.

{{% alert color="primary" %}}

You cannot split a document using the [document_split_criteria](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/document_split_criteria/) property when saving to MHTML format.

{{% /alert %}}

In this section, we consider only some of the possible split criteria.

### Split a Document by Headings {#split-a-document-by-headings}

To split a document into chapters by headings, use the **HEADING_PARAGRAPH** value of the **document_split_criteria** property.

If you need to split a document by a specific level of heading paragraphs, such as headings 1, 2, and 3, use also the [document_split_heading_level](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/document_split_heading_level/) property. The output will be divided by paragraphs formatted with the specified heading level.

The following code example shows how to split a document into smaller parts by heading:

{{< gist "aspose-words-gists" "c5d01a71f65e540e5e77650b846b24cc" "split-document-by-headings.py" >}}

Please note that for this criteria, Aspose.Words only supports saving to HTML format when splitting.

When saving to EPUB, the document is not split into several files, and there will be only one output file.

### Split a Document by Sections {#split-a-document-by-sections}

Aspose.Words also enables you to use section breaks to split documents and save them to HTML. For this purpose, use **SECTION_BREAK** as the **document_split_criteria**:

{{< gist "aspose-words-gists" "fec4c47291463c8d8d8a6684ffb23d64" "split-document-by-sections-html.py" >}}

There is another way to split the source document into multiple output documents, and you can choose any output format supported by Aspose.Words.

The following code example shows how to split a document into smaller parts by section breaks (without using the `DocumentSplitCriteria` property):

{{< gist "aspose-words-gists" "fec4c47291463c8d8d8a6684ffb23d64" "split-document-by-sections.py" >}}

## Split by Pages {#splitting-by-pages}

You can also split a document page by page, by page ranges, or starting with the specified page numbers. In such case the [extract_pages](https://reference.aspose.com/words/python-net/aspose.words/document/extract_pages/) method can do the job.

This section describes several use cases of dividing documents by paged using the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) class and the **extract_pages** method.

{{% alert color="primary" %}}

You can use any [output format supported by Aspose.Words](/words/python-net/supported-document-formats/).

{{% /alert %}}

{{% alert color="primary" %}}

Due to the many nuances appearing while reducing the number of pages, a full match with the Microsoft Word layout is quite a complicated task. Therefore, depending on the document complexity, there may be slight differences in the resulting document layout from the original document.

{{% /alert %}}

### Split a Document Page by Page {#split-a-document-page-by-page}

Aspose.Words enables you to split a multi-page document page by page.

The following code example shows how to divide a document and save each page as a separate document:

{{< gist "aspose-words-gists" "fec4c47291463c8d8d8a6684ffb23d64" "split-document-page-by-page.py" >}}

### Split a Document by Page Ranges {#split-a-document-by-page-ranges}

Aspose.Words allows splitting a multi-page document by page ranges. You can split one file into multiple files with various page ranges or just select one range and save only this part of the source document. Note that you can choose the page range according to the maximum and minimum page number of a document.

The following code example shows how to split a document into smaller parts by page range with specific start and end indexes:

{{< gist "aspose-words-gists" "fec4c47291463c8d8d8a6684ffb23d64" "split-document-by-page-range.py" >}}

## Callback Option to Save a Document {#callback-option-for-saving-a-document}

You can use the [document_part_saving_callback](https://reference.aspose.com/words/python-net/aspose.words.saving/htmlsaveoptions/document_part_saving_callback/) property to control how Aspose.Words saves document parts when this document is exported into HTML format. This property allows you to rename output files or even to redirect them into custom streams.

Please note that this callback is not useful when saving to EPUB because all output parts must be saved into a single container – the .epub file. So, stream redirection is not supported, and the effect of renaming is not visible since files are renamed inside the container.

## Merge the Split Document with Another Document {#merge-the-split-document-with-another-file}

Aspose.Words enables you to merge the output split document with another document to form a new document. This can be called document merging.

The following code example shows how to merge a split document with another document:

{{< gist "aspose-words-gists" "fec4c47291463c8d8d8a6684ffb23d64" "merge-split-documents.py" >}}

## FAQ

1. **Q:** How can I split a document by a specific heading level (e.g., only Heading 2)?
   **A:** Set the `document_split_criteria` to `HEADING_PARAGRAPH` and assign the desired level to the `document_split_heading_level` property of `HtmlSaveOptions`. Only paragraphs formatted with that heading level will be used as split points.

2. **Q:** Which output formats support splitting by headings?
   **A:** Splitting with `document_split_criteria` is supported when saving to HTML and EPUB (for EPUB, the parts are packed into one file); MHTML cannot be split. For other formats, split the document yourself, for example by sections or with `extract_pages`.

3. **Q:** Can I split a document into separate files by page ranges in one operation?
   **A:** Yes. Use the `Document.extract_pages(index, count)` method (zero-based index of the first page and the number of pages) to obtain a sub‑document for each range, then save each sub‑document using any supported format.

4. **Q:** Is it possible to split a document while preserving the original layout and styles?
   **A:** Aspose.Words retains the original layout, styles, and formatting for each split part. However, minor differences may appear for complex layouts, especially when converting to formats other than the source.

5. **Q:** How do I split a document that contains section breaks without using `document_split_criteria`?
   **A:** Load the document, iterate through its `sections` collection, clone each section into a new `Document` object, and save each clone. This approach works for any output format supported by Aspose.Words.