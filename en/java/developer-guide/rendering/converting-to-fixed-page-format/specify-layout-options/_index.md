---
title: Specify Layout Options in Java
second_title: Aspose.Words for Java
articleTitle: Specify Layout Options
linktitle: Specify Layout Options
description: "Create output documents with various layouts, depending on the parameters specified in the Document using Java."
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/specify-layout-options/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to configure layout options that affect pagination and rendering.

{{% /alert %}}

Aspose.Words enables you to create output documents with various layouts, depending on the parameters specified in properties of the [LayoutOptions](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/) class. Some of these properties resemble some of the Microsoft Word user interface menu options – they will be described in this article.

For a complete list of parameters such as [getContinuousSectionPageNumberingRestart()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getContinuousSectionPageNumberingRestart) to calculate page numbers in a continuous section that restarts page numbering, or [getIgnorePrinterMetrics()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getIgnorePrinterMetrics) to ignore the "Use printer metrics to lay out document" compatibility option, see the [LayoutOptions](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/) class page.

## Formatting Marks

Aspose.Words allows to manage formatting marks using the following properties:

- [getShowHiddenText()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getShowHiddenText) – a `Boolean` value, which specifies whether the hidden text is rendered.
- [getShowParagraphMarks()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getShowParagraphMarks) – a `Boolean` value, which specifies whether paragraph mark characters are rendered.

The page depicted in the example below contains three paragraphs. The second one is hidden. A user can change the **getShowHiddenText()** option to display this hidden text on the page. Also, each paragraph has a paragraph mark at the end. The paragraph mark usually is not visible unless the **getShowParagraphMarks()** property is set to render it.

![specify-layout-options_1_java](specify-layout-options-1.png)

In Microsoft Word, these parameters are set using the "File → Options → Display" dialog box as follows:

![specify-layout-options_2_java](specify-layout-options-2.jpg)

## Comments and Revisions

With Aspose.Words, you can render document comments that will look the same as in Microsoft Word. To specify whether comments are rendered, use the [CommentDisplayMode](https://reference.aspose.com/words/java/com.aspose.words/commentdisplaymode/) property.

In Microsoft Word, this parameter is set using the "Track Changes Options" dialog box, as shown below:

![specify-layout-options_3_java](specify-layout-options-3.jpg)

Also, Aspose.Words allows you to display revisions in a document. Use the [getRevisionOptions()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getRevisionOptions) property of the **LayoutOptions** class to define whether the document revisions are displayed. To control their appearance (revision highlighting color, revision bar color, etc.), use the [RevisionOptions](https://reference.aspose.com/words/java/com.aspose.words/revisionoptions/) class.

You can also have revisions displayed as comments to the content. For this purpose, use the [getCommentDisplayMode()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getCommentDisplayMode) property and [ShowInBalloons](https://reference.aspose.com/words/java/com.aspose.words/commentdisplaymode/) value.

The following code example shows how to customize revisions display:

{{< gist "aspose-words-gists" "7c6d4aa20f88d174b3676a704a7b088f" "show-revisions-in-balloons.java" >}}

The image below shows how Aspose.Words renders comments and the Delete revisions:

<img src="specify-layout-options-4.png" alt="comments_and_revisions_example_aspose_words_java" style="width:800px"/>

## Text Shaper for Advanced Typography Rendering

The [getTextShaperFactory()](https://reference.aspose.com/words/java/com.aspose.words/layoutoptions/#getTextShaperFactory) property enables you to set the text shaping functionality, as well as the `OpenType` features support.

Use text shaping for document processing in the following main cases:

- A document uses Kerning, Numeral Shaping, Numeral Forms, or Ligatures.
- A document uses Complex Scripts, such as Arabic, Khmer, Thai, etc.

{{% alert color="primary" %}}

Text shaping will be enabled only when exporting a document to PDF or XPS.

{{% /alert %}}
