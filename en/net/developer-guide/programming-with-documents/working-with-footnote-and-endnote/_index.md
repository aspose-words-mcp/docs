---
title: Working with Footnote and Endnote in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Footnote and Endnote
linktitle: Working with Footnote and Endnote
description: "How to manipulate footnotes and endnotes using C#."
type: docs
weight: 160
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-footnote-and-endnote/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with footnotes and endnotes.

{{% /alert %}}

Aspose.Words also provides some classes, methods and properties for working with footnotes and endnotes.

## Insert Endnote and Set Numbering Options

If you want to insert footnote or endnote into Word document, please use the [InsertFootnote](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertfootnote/) method. This method inserts a footnote or endnote into the document.

[EndnoteOptions](https://reference.aspose.com/words/net/aspose.words.notes/endnoteoptions/) and [FootnoteOptions](https://reference.aspose.com/words/net/aspose.words.notes/footnoteoptions/) classes represent numbering options for footnote and endnote.

The following code example shows how to insert endnote into the document and set its numbering options:

{{< gist "aspose-words-gists" "3b39c2019380ee905e7d9596494916a4" "set-endnote-options.cs" >}}

## Set Number of Footnote Layout Columns

You can set the number of footnote layout columns using the [Columns](https://reference.aspose.com/words/net/aspose.words.notes/footnoteoptions/columns/) property. If this property has the value of 0, the footnotes area is formatted with a number of columns based on the number of columns on the displayed page.

The following code example shows how to set the number of columns for footnote layout:

{{< gist "aspose-words-gists" "3b39c2019380ee905e7d9596494916a4" "set-footnote-columns.cs" >}}

## Set the Position of Footnote and EndNote

The footnote position can be at the bottom of each page or beneath the text on each page. The endnote position can be at the end of the section or at the end of the document.

The following code example shows how to set the position of footnote and endnote:

{{< gist "aspose-words-gists" "3b39c2019380ee905e7d9596494916a4" "set-footnote-and-endnote-position.cs" >}}

------

## FAQ

1. **Q:** How do I insert a footnote or an endnote with DocumentBuilder?  
   **A:** Use the `DocumentBuilder.InsertFootnote` method: pass the `FootnoteType` enumeration value (`FootnoteType.Footnote` or `FootnoteType.Endnote`) and the note text. The method returns the inserted `Footnote` object.

   ```csharp
   Document doc = new Document();
   DocumentBuilder builder = new DocumentBuilder(doc);
   // Insert a footnote
   Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "This is a footnote.");
   // Insert an endnote
   Footnote endnote = builder.InsertFootnote(FootnoteType.Endnote, "This is an endnote.");
   ```

2. **Q:** How can I change the numbering style of footnotes or endnotes?  
   **A:** Modify the `NumberStyle` property of `FootnoteOptions` or `EndnoteOptions` on the `Document` object. Supported styles include Arabic, UppercaseRoman, LowercaseRoman, UppercaseLetter, and LowercaseLetter.

   ```csharp
   doc.FootnoteOptions.NumberStyle = NumberStyle.UppercaseRoman;
   doc.EndnoteOptions.NumberStyle = NumberStyle.LowercaseLetter;
   ```

3. **Q:** What property controls the number of columns used for footnote layout?  
   **A:** The `FootnoteOptions.Columns` property defines how many columns the footnote area uses. Setting it to `0` lets Word decide based on the page layout.

   ```csharp
   doc.FootnoteOptions.Columns = 2; // Two‑column footnote area
   ```

4. **Q:** How do I set where footnotes and endnotes appear in the document?  
   **A:** Use the `FootnoteOptions.Position` and `EndnoteOptions.Position` properties. For footnotes you can choose `FootnotePosition.BottomOfPage` or `FootnotePosition.BeneathText`. For endnotes you can choose `EndnotePosition.EndOfSection` or `EndnotePosition.EndOfDocument`.

   ```csharp
   doc.FootnoteOptions.Position = FootnotePosition.BottomOfPage;
   doc.EndnoteOptions.Position = EndnotePosition.EndOfDocument;
   ```

5. **Q:** Can I convert an existing footnote to an endnote (or vice‑versa) without recreating it?  
   **A:** Not directly: `Footnote.FootnoteType` is read-only. Insert a note of the other type at the same position with the same text, then remove the original note. The new note gets the plain text only; formatting inside the original note is not copied.

   ```csharp
   // Convert the first footnote to an endnote
   Footnote footnote = (Footnote)doc.GetChild(NodeType.Footnote, 0, true);
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.MoveTo(footnote);
   builder.InsertFootnote(FootnoteType.Endnote, footnote.ToString(SaveFormat.Text).Trim());
   footnote.Remove();
   ```