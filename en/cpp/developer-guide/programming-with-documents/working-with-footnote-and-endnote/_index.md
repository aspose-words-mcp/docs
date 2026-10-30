---
title: Working with Footnote and Endnote
second_title: Aspose.Words for C++
articleTitle: Working with Footnote and Endnote
linktitle: Working with Footnote and Endnote
description: "How to manipulate footnotes and endnotes using C++."
type: docs
weight: 160
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-footnote-and-endnote/
timestamp: 2024-01-27-14-07-04
---

Aspose.Words also provides some classes, methods and properties for working with footnotes and endnotes.

## Insert Endnote and Set Numbering Options

If you want to insert a footnote or endnote in a Word document, please use the [InsertFootnote](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertfootnote/) method. This method inserts a footnote or endnote into the document.

[EndnoteOptions](https://reference.aspose.com/words/cpp/aspose.words.notes/endnoteoptions/) and [FootnoteOptions](https://reference.aspose.com/words/cpp/aspose.words.notes/footnoteoptions/) classes represent numbering options for footnote and endnote.

The following code example shows how to insert endnote into the document and set its numbering options:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-WorkingWithFootnote-SetEndnoteOptions.cpp" >}}

## Set Number of Footnote Layout Columns

You can set the number of footnote layout columns using the [get_Columns()](https://reference.aspose.com/words/cpp/aspose.words.notes/footnoteoptions/get_columns/) property. If this property has a value of 0, the footnotes area is formatted with a number of columns based on the number of columns on the displayed page.

The following code example shows how to set the number of columns for footnote layout:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-WorkingWithFootnote-SetFootNoteColumns.cpp" >}}

## Set the Position of Footnote and EndNote

The footnote position can be at the bottom of each page or beneath the text on each page. The endnote position can be at the end of the section or at the end of the document.

The following code example shows how to set the position of footnote and endnote:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-WorkingWithFootnote-SetFootnoteAndEndNotePosition.cpp" >}}

------ 

## FAQ

1. **Q:** How can I change the numbering format of footnotes or endnotes?  
   **A:** Use the `FootnoteOptions::set_NumberStyle` or `EndnoteOptions::set_NumberStyle` property on the document's `FootnoteOptions`/`EndnoteOptions` object. For example:  

   ```cpp
   System::SharedPtr<Aspose::Words::Notes::FootnoteOptions> footnoteOpts = doc->get_FootnoteOptions();
   footnoteOpts->set_NumberStyle(Aspose::Words::NumberStyle::UppercaseRoman);
   ```

2. **Q:** How can I retrieve all footnotes or endnotes from a document?  
   **A:** Get all notes with `doc->GetChildNodes(NodeType::Footnote, true)` (endnotes are `Footnote` nodes too) and check `Footnote::get_FootnoteType()` to tell footnotes from endnotes:  

   ```cpp
   for (auto footnote : System::IterateOver<Aspose::Words::Notes::Footnote>(doc->GetChildNodes(Aspose::Words::NodeType::Footnote, true)))
   {
       bool isEndnote = footnote->get_FootnoteType() == Aspose::Words::Notes::FootnoteType::Endnote;
       System::String text = footnote->GetText();
       // Process text...
   }
   ```

3. **Q:** How can I detect whether a document contains any footnotes or endnotes?  
   **A:** Count the `Footnote` nodes of each type. If the count is greater than zero, the document contains those notes:  

   ```cpp
   int32_t footnotes = 0, endnotes = 0;
   for (auto note : System::IterateOver<Aspose::Words::Notes::Footnote>(doc->GetChildNodes(Aspose::Words::NodeType::Footnote, true)))
   {
       (note->get_FootnoteType() == Aspose::Words::Notes::FootnoteType::Footnote ? footnotes : endnotes)++;
   }
   bool hasFootnotes = footnotes > 0;
   bool hasEndnotes  = endnotes > 0;
   ```

4. **Q:** Can I convert an existing endnote to a footnote (or vice‑versa) after it has been inserted?  
   **A:** Aspose.Words does not provide a direct conversion method. Remove the original note using `Remove()` and re‑insert a new note of the desired type with `DocumentBuilder::InsertFootnote`, specifying `FootnoteType::Footnote` or `FootnoteType::Endnote`.  

   ```cpp
   // Insert a footnote at the same location, then remove the endnote
   System::SharedPtr<Aspose::Words::DocumentBuilder> builder = System::MakeObject<Aspose::Words::DocumentBuilder>(doc);
   builder->MoveTo(endnote->get_ParentParagraph());
   builder->InsertFootnote(Aspose::Words::Notes::FootnoteType::Footnote, u"New footnote text");
   endnote->Remove();
   ```