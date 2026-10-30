---
title: Specify Layout Options in C++
second_title: Aspose.Words for C++
articleTitle: Specify Layout Options
linktitle: Specify Layout Options
description: "Specify Layout Options for various document layouts."
type: docs
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/specify-layout-options/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to configure layout options that affect pagination and rendering.

{{% /alert %}}

Aspose.Words enables you to create output documents with various layouts, depending on the parameters specified in properties of the [LayoutOptions](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/) class. Some of these properties resemble some of the Microsoft Word user interface menu options – they will be described in this article.

For a complete list of parameters such as [get_ContinuousSectionPageNumberingRestart()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_continuoussectionpagenumberingrestart/) to calculate page numbers in a continuous section that restarts page numbering, or [get_IgnorePrinterMetrics()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_ignoreprintermetrics/) to ignore the "Use printer metrics to lay out document" compatibility option, see the [LayoutOptions](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/) class page.

## Formatting Marks

Aspose.Words allows to manage formatting marks using the following properties:

- [get_ShowHiddenText()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_showhiddentext/) – a `Boolean` value, which specifies whether the hidden text is rendered.
- [get_ShowParagraphMarks()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_showparagraphmarks/) – a `Boolean` value, which specifies whether paragraph mark characters are rendered.

The page depicted in the example below contains three paragraphs. The second one is hidden. A user can change the **get_ShowHiddenText()** option to display this hidden text on the page. Also, each paragraph has a paragraph mark at the end. The paragraph mark usually is not visible unless the **get_ShowParagraphMarks()** property is set to render it.

![specify-layout-options_1-cpp](specify-layout-options-1.png)

In Microsoft Word, these parameters are set using the "File → Options → Display" dialog box as follows:

![specify-layout-options_2-cpp](specify-layout-options-2.jpg)

## Comments and Revisions

With Aspose.Words, you can render document comments that will look the same as in Microsoft Word. To specify whether comments are rendered, use the [get_CommentDisplayMode()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_commentdisplaymode/) property.

In Microsoft Word, this parameter is set using the "Track Changes Options" dialog box, as shown below:

![specify-layout-options_3-cpp](specify-layout-options-3.jpg)

Also, Aspose.Words allows you to display revisions in a document. Use the [get_RevisionOptions()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_revisionoptions/) property of the **LayoutOptions** class to define whether the document revisions are displayed. To control their appearance (revision highlighting color, revision bar color, etc.), use the [get_RevisionOptions()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_revisionoptions/) class.

You can also have revisions displayed as comments to the content. For this purpose, use the [set_CommentDisplayMode()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/set_commentdisplaymode/) property and [ShowInBalloons](https://reference.aspose.com/words/cpp/aspose.words.layout/commentdisplaymode/) value.

The following code example shows how to customize revisions display:

{{< gist "aspose-words-gists" "3c74bb3e27a4d8aa21114f5e8a3b0c7a" "show-revisions-in-balloons.h" >}}

The image below shows how Aspose.Words renders comments and the Delete revisions:

<img src="specify-layout-options-4.png" alt="comments_and_revisions_example_aspose_words_net-cpp" style="width:800px"/>

## Text Shaper for Advanced Typography Rendering

The [get_TextShaperFactory()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_textshaperfactory/) property enables you to set the text shaping functionality, as well as the `OpenType` features support.

Use text shaping for document processing in the following main cases:

- A document uses Kerning, Numeral Shaping, Numeral Forms, or Ligatures.
- A document uses Complex Scripts, such as Arabic, Khmer, Thai, etc.

{{% alert color="primary" %}}

Text shaping will be enabled only when exporting a document to PDF or XPS.

{{% /alert %}}

## Related APIs

- [LayoutOptions](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/)
- [RevisionOptions](https://reference.aspose.com/words/cpp/aspose.words.layout/revisionoptions/)
- [CommentDisplayMode](https://reference.aspose.com/words/cpp/aspose.words.layout/commentdisplaymode/)
- [get_TextShaperFactory()](https://reference.aspose.com/words/cpp/aspose.words.layout/layoutoptions/get_textshaperfactory/)
