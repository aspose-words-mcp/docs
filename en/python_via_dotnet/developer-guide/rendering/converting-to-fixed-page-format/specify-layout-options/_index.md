---
title: Specify Layout Options in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Specify Layout Options
linktitle: Specify Layout Options
description: "Specify Layout Options for various document layouts using Python."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/specify-layout-options/
aliases: [/python/specify-layout-options/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use the `LayoutOptions` class in Aspose.Words for Python via .NET to control document layout features such as hidden text, paragraph marks, comment rendering, and revision display. It provides property descriptions, UI equivalents, and code examples.

{{% /alert %}}

Aspose.Words enables you to create output documents with various layouts, depending on the parameters specified in properties of the [LayoutOptions](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/) class. Some of these properties resemble some of the Microsoft Word user interface menu options – they will be described in this article.

For a complete list of parameters such as [continuous_section_page_numbering_restart](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/continuous_section_page_numbering_restart/) to calculate page numbers in a continuous section that restarts page numbering, or [ignore_printer_metrics](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/ignore_printer_metrics/) to ignore the "Use printer metrics to lay out document" compatibility option, see the [LayoutOptions](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/) class page.

## Formatting Marks

Aspose.Words allows to manage formatting marks using the following properties:

- [show_hidden_text](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/show_hidden_text/) – a `Boolean` value, which specifies whether the hidden text is rendered.
- [show_paragraph_marks](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/show_paragraph_marks/) – a `Boolean` value, which specifies whether paragraph mark characters are rendered.

The page depicted in the example below contains three paragraphs. The second one is hidden. A user can change the **show_hidden_text** option to display this hidden text on the page. Also, each paragraph has a paragraph mark at the end. The paragraph mark usually is not visible unless the **show_paragraph_marks** property is set to render it.

![specify-layout-options_1](specify-layout-options-1.png)

In Microsoft Word, these parameters are set using the "File → Options → Display" dialog box as follows:

![specify-layout-options_2](specify-layout-options-2.jpg)

## Comments and Revisions

With Aspose.Words, you can render document comments that will look the same as in Microsoft Word. To specify whether comments are rendered, use the [comment_display_mode](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/comment_display_mode/) property.

In Microsoft Word, this parameter is set using the "Track Changes Options" dialog box, as shown below:

![specify-layout-options_3](specify-layout-options-3.jpg)

Also, Aspose.Words allows you to display revisions in a document. Use the [revision_options](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/revision_options/) property of the **LayoutOptions** class to define whether the document revisions are displayed. To control their appearance (revision highlighting color, revision bar color, etc.), use the [LayoutOptions](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/) class.

You can also have revisions displayed as comments to the content. For this purpose, use the [comment_display_mode](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/comment_display_mode/) property and [SHOW_IN_BALLOONS](https://reference.aspose.com/words/python-net/aspose.words.layout/commentdisplaymode/#show_in_balloons) value.

The following code example shows how to customize revisions display:

{{< gist "aspose-words-gists" "eb9bb984280031c2644713d0030a7ec5" "show-revisions-in-balloons.py" >}}

The image below shows how Aspose.Words renders comments and the Delete revisions:

<img src="specify-layout-options-4.png" alt="comments_and_revisions_example_aspose_words_net" style="width:800px"/>

## Text Shaper for Advanced Typography Rendering

The [enable_text_shaping](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/enable_text_shaping/) property enables support for `OpenType` features using the HarfBuzz text shaping engine.

Use text shaping for document processing in the following main cases:

- A document uses Kerning, Numeral Shaping, Numeral Forms, or Ligatures.
- A document uses Complex Scripts, such as Arabic, Khmer, Thai, etc.

{{% alert color="primary" %}}

Text shaping will be enabled only when exporting a document to PDF or XPS.

{{% /alert %}}

## Related APIs

- [LayoutOptions](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/)
- [RevisionOptions](https://reference.aspose.com/words/python-net/aspose.words.layout/revisionoptions/)
- [CommentDisplayMode](https://reference.aspose.com/words/python-net/aspose.words.layout/commentdisplaymode/)
- [enable_text_shaping](https://reference.aspose.com/words/python-net/aspose.words.layout/layoutoptions/enable_text_shaping/) 

## FAQ

1. **Q:** How can I show hidden text in the rendered document?  
   **A:** Set the `show_hidden_text` property of the document’s `LayoutOptions` to `True`. Example:  
   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   doc.layout_options.show_hidden_text = True
   doc.save("output.pdf")
   ```

2. **Q:** How do I display paragraph marks (¶) when rendering a document?  
   **A:** Enable the `show_paragraph_marks` property on `LayoutOptions`. Example:  
   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   doc.layout_options.show_paragraph_marks = True
   doc.save("output.pdf")
   ```

3. **Q:** Which setting controls whether comments are rendered in the output?  
   **A:** Use the `comment_display_mode` property. Set it to `CommentDisplayMode.SHOW_IN_BALLOONS` to display comments as balloons, or to `CommentDisplayMode.HIDE` to hide them. Example:  
   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   doc.layout_options.comment_display_mode = aw.layout.CommentDisplayMode.SHOW_IN_BALLOONS
   doc.save("output.pdf")
   ```

4. **Q:** How can I show revisions (track changes) in the generated document?  
   **A:** Enable `revision_options.show_revision_marks` and optionally configure colors via `RevisionOptions`. Example:  
   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   doc.layout_options.revision_options.show_revision_marks = True
   # Set custom colors if needed
   doc.layout_options.revision_options.inserted_text_color = aw.layout.RevisionColor.RED
   doc.layout_options.revision_options.deleted_text_color = aw.layout.RevisionColor.BLUE
   doc.save("output.pdf")
   ```

5. **Q:** What does the `ignore_printer_metrics` option do?  
   **A:** When set to `True`, Aspose.Words ignores the printer’s DPI and other metrics, laying out the document using screen metrics only. This can produce consistent layout across different printers. Example:  
   ```python
   import aspose.words as aw

   doc = aw.Document("input.docx")
   doc.layout_options.ignore_printer_metrics = True
   doc.save("output.pdf")
   ```
