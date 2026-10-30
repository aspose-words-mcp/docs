---
title: Working with Footnote and Endnote in Java
second_title: Aspose.Words for Java
articleTitle: Working with Footnote and Endnote
linktitle: Working with Footnote and Endnote
description: "How to manipulate footnotes and endnotes using Java."
type: docs
weight: 160
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-footnote-and-endnote/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with footnotes and endnotes.

{{% /alert %}}

Aspose.Words also provides some classes, methods and properties for working with footnotes and endnotes.

## Insert Endnote and Set Numbering Options

If you want to insert footnote or endnote into Word document, please use the [insertFootnote()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertFootnote-int-java.lang.String) method. This method inserts a footnote or endnote into the document.

[EndnoteOptions](https://reference.aspose.com/words/java/com.aspose.words/endnoteoptions/) and [FootnoteOptions](https://reference.aspose.com/words/java/com.aspose.words/footnoteoptions/) classes represent numbering options for footnote and endnote.

The following code example shows how to insert endnote into the document and set its numbering options:

{{< gist "aspose-words-gists" "1cb8150f6ed075f764a1b8f2928f318e" "set-endnote-options.java" >}}

## Set Number of Footnote Layout Columns

You can set the number of footnote layout columns using the [getColumns()](https://reference.aspose.com/words/java/com.aspose.words/footnoteoptions/#getColumns) property. If this property has the value of 0, the footnotes area is formatted with a number of columns based on the number of columns on the displayed page.

The following code example shows how to set the number of columns for footnote layout:

{{< gist "aspose-words-gists" "1cb8150f6ed075f764a1b8f2928f318e" "set-footnote-columns.java" >}}

## Set the Position of Footnote and EndNote

The footnote position can be at the bottom of each page or beneath the text on each page. The endnote position can be at the end of the section or at the end of the document.

The following code example shows how to set the position of footnote and endnote:

{{< gist "aspose-words-gists" "1cb8150f6ed075f764a1b8f2928f318e" "set-footnote-and-endnote-position.java" >}}

## FAQ

1. **Q:** How do I insert a footnote or an endnote with DocumentBuilder?  
   **A:** Use `DocumentBuilder.insertFootnote(FootnoteType type, String text)`. Pass `FootnoteType.FOOTNOTE` for a footnote or `FootnoteType.ENDNOTE` for an endnote, and provide the content string.

2. **Q:** Can I change the numbering style (e.g., Roman, Arabic) of footnotes or endnotes?  
   **A:** Yes. Access the options via `Document.getFootnoteOptions()` or `Document.getEndnoteOptions()` and call `setNumberStyle` with a `NumberStyle` value (e.g., `NumberStyle.LOWERCASE_ROMAN` or `NumberStyle.ARABIC`) to set the desired numbering format.

3. **Q:** How do I control how many columns footnotes are displayed in?  
   **A:** Set the `Columns` property on the document's `FootnoteOptions`: `document.getFootnoteOptions().setColumns(int columns)`. A value of `0` lets Word decide based on page layout.

4. **Q:** What properties determine where footnotes and endnotes appear in the document?  
   **A:** Use `FootnoteOptions.setPosition(FootnotePosition position)` to choose between `BOTTOM_OF_PAGE` or `BENEATH_TEXT`. For endnotes, use `EndnoteOptions.setPosition(EndnotePosition position)` with values `END_OF_SECTION` or `END_OF_DOCUMENT`.

5. **Q:** How can I retrieve existing footnotes or endnotes from a loaded document?  
   **A:** Footnotes and endnotes are both `Footnote` nodes. Get them with `document.getChildNodes(NodeType.FOOTNOTE, true)` and tell them apart with `getFootnoteType()` (`FootnoteType.FOOTNOTE` or `FootnoteType.ENDNOTE`), e.g., `for (Footnote footnote : (Iterable<Footnote>) document.getChildNodes(NodeType.FOOTNOTE, true)) { /* process */ }`. This lets you read, modify, or remove individual notes.