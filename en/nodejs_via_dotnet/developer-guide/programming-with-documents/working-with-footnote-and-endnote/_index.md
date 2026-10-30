---
title: Working with Footnote and Endnote
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Footnote and Endnote
linktitle: Working with Footnote and Endnote
description: "Insert ffotnotes or endnotes into a document and specify its options using Node.js."
type: docs
weight: 160
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-footnote-and-endnote/
timestamp: 2025-07-09-10-05-05
---

Aspose.Words also provides some classes, methods and properties for working with footnotes and endnotes.

## Insert Endnote and Set Numbering Options

If you want to insert footnote or endnote in Word document, please use [insertFootnote](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertfootnote/) method. This method inserts a footnote or endnote into the document.

[EndnoteOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.notes/endnoteoptions/) and [FootnoteOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.notes/footnoteoptions/) classes represent numbering options for footnote and endnote.

The following code example shows how to insert endnote into the document and set its numbering options:

{{< gist "aspose-words-gists" "7717b3a13cf86fabceb5860693073506" "set-endnote-options.js" >}}

## Set Number of Footnote Layout Columns

You can set the number of footnote layout columns using the [columns](https://reference.aspose.com/words/nodejs-net/aspose.words.notes/footnoteoptions/columns/) property. If this property has the value of 0, the footnotes area is formatted with a number of columns based on the number of columns on the displayed page.

The following code example shows how to set the number of columns for footnote layout:

{{< gist "aspose-words-gists" "7717b3a13cf86fabceb5860693073506" "set-footnote-columns.js" >}}

## Set the Position of Footnote and EndNote

The footnote position can be at the bottom of each page or beneath the text on each page. The endnote position can be at the end of the section or at the end of the document.

The following code example shows how to set the position of footnote and endnote:

{{< gist "aspose-words-gists" "7717b3a13cf86fabceb5860693073506" "set-footnote-and-endnote-position.js" >}}

------ 

## FAQ

1. **Q:** How do I insert a footnote or endnote with DocumentBuilder?  
   **A:** Use the `insertFootnote` method of `DocumentBuilder`. Pass the `FootnoteType.Footnote` or `FootnoteType.Endnote` enum value and the footnote text. The method returns a `Footnote` object that you can further customize.

2. **Q:** How can I change the numbering format of footnotes or endnotes?  
   **A:** Set the `numberStyle` property of the document's `footnoteOptions` or `endnoteOptions` object (e.g., `doc.footnoteOptions.numberStyle = aw.NumberStyle.LowercaseRoman;`).

3. **Q:** How do I set the number of columns for footnote layout?  
   **A:** Set the `columns` property of `FootnoteOptions`. A value of `0` lets Word decide based on the page layout; any positive integer forces that many columns.

4. **Q:** How can I control where footnotes and endnotes appear in the document?  
   **A:** Use the `position` property of `FootnoteOptions` (`FootnotePosition.BottomOfPage` or `FootnotePosition.BeneathText`) and the `position` property of `EndnoteOptions` (`EndnotePosition.EndOfSection` or `EndnotePosition.EndOfDocument`). Both objects are available through the document's `footnoteOptions` and `endnoteOptions` properties.

5. **Q:** I have HTML that contains `<sup>` endnote tags—how can I convert them to Word endnotes?  
   **A:** Load the HTML into a `Document`, then iterate through the `Paragraph` nodes looking for `Superscript` runs that contain the endnote marker. Replace each marker with an `Endnote` using `DocumentBuilder.insertFootnote(FootnoteType.Endnote, “text”)`. Finally, save the document in the desired format.