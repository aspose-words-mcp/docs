---
title: Working with Sections in C++
second_title: Aspose.Words for C++
articleTitle: Working with Sections
linktitle: Working with Sections
description: "Understanding document section concepts and manipulation practices using C++. Insert section into a document C++. Remove section C++. Copy sections between Documents."
type: docs
weight: 120
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-sections/
aliases: [/cpp/how-to-remove-page-and-section-breaks/]
timestamp: 2024-01-31-14-23-37
---

Sometimes you want a document that does not have the same formatting across all pages. For example, you may need to modify page number formats, have different page size and orientation, or have the first document page as a cover page without any numbering. You can achieve that with sections.

Sections are level nodes that control headers and footers, orientation, columns, margins, page number formatting, and others.

Aspose.Words allows you to manage sections, divide a document into sections, and make formatting changes that apply only to a specific section. Aspose.Words stores information about section formatting such as headers and footers, page setup, and column settings in the section break.

This article explains how to work with sections and section breaks.

## What Section and Section Break Is

Document sections are represented by the [Section](https://reference.aspose.com/words/cpp/aspose.words/section/) and [SectionCollection](https://reference.aspose.com/words/cpp/aspose.words/sectioncollection/) classes. Section objects are immediate children of the [Document](https://reference.aspose.com/words/cpp/aspose.words/document/) node and can be accessed via the [get_Sections()](https://reference.aspose.com/words/cpp/aspose.words/document/get_sections/) property. You can manage those nodes by using some methods such as [Remove](https://reference.aspose.com/words/cpp/aspose.words/nodecollection/remove/), [Add](https://reference.aspose.com/words/cpp/aspose.words/nodecollection/add/), [IndexOf](https://reference.aspose.com/words/cpp/aspose.words/nodecollection/indexof/), and others.

Section break is an option that divides document pages into sections with customizable layouts.

## Types of a Section Break

Aspose.Words allows you to split and format documents using different section breaks of the [BreakType](https://reference.aspose.com/words/cpp/aspose.words/breaktype/) enumeration:

- SectionBreakContinuous
- SectionBreakNewColumn
- SectionBreakNewPage
- SectionBreakEvenPage
- SectionBreakOddPage

You can also use the [SectionStart](https://reference.aspose.com/words/cpp/aspose.words/sectionstart/) enumeration to choose a break type that applies only for the first section such as NewColumn, NewPage, EvenPage, and OddPage.

## Manage a Section

Since a section is a normal composite node, the entire node manipulation API can be used to manipulate sections: to add, remove, and other operations on sections. You can read more about nodes in the article [Aspose.Words Document Object Model (DOM)](/words/cpp/aspose-words-document-object-model/).

On the other hand, you can also use the `DocumentBuilder` API to work with sections. In this article, we will focus on this particular way of working with sections.

## Insert or Remove a Section Break

Aspose.Words allows you to insert a section break into text using the [InsertBreak](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertbreak/) method.

The following code example shows how to insert a section break into a document:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "insert-section-breaks.cpp" >}}

Use the [Remove](https://reference.aspose.com/words/cpp/aspose.words/node/remove/) method to delete a section break. If you do not need to remove a specific section break and instead delete the content of that section, you can use the [ClearContent](https://reference.aspose.com/words/cpp/aspose.words/section/clearcontent/) method.

The following code example shows how to remove sections breaks: 

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "remove-section-breaks.h" >}}

{{% alert color="primary" %}}

Note that a section break has information about the section that goes before it, not the section that goes after it. So if you remove a section break, the text before the removed break will get the properties of the section break following it. This can cause the entire document to becoming landscape, or headers and footers to change or fully disappear.

{{% /alert %}}

## Move a Section

If you want to move a section from one position to another in your document, you need to get the index of that section. Aspose.Words allows you to get a section position from a [SectionCollection](https://reference.aspose.com/words/cpp/aspose.words/sectioncollection/). You can use the [get_Sections()](https://reference.aspose.com/words/cpp/aspose.words/document/get_sections/) property to get all sections in your document. But if you want to get only the first section, you can use the [get_FirstSection()](https://reference.aspose.com/words/cpp/aspose.words/document/get_firstsection/) property.

The following code example shows how to access the first section and iterate through the children of a composite node:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "section-child-nodes.h" >}}

## Specify a Section Layout

Sometimes you want your document to look better by making creative layouts for different document sections. If you want to specify the type of the current section grid, you can choose a section layout mode using the [SectionLayoutMode](https://reference.aspose.com/words/cpp/aspose.words/sectionlayoutmode/) enumeration:

- Default
- Grid
- LineGrid
- SnapToChars

The following code example shows how to limit the number of lines that each page may have:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "line-grid-section-layout-mode.h" >}}

## Edit a Section

When you add a new section to your document, there will be no body or paragraph that you can edit. Aspose.Words allows you to guarantee that a section contains a body with at least one paragraph using the [EnsureMinimum](https://reference.aspose.com/words/cpp/aspose.words/section/ensureminimum/) method – it will automatically add a Body (or HeaderFooter) node to the document and then add a Paragraph to it.

The following code example shows how to prepare a new section node using **EnsureMinimum**:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "ensure-minimum.h" >}}

### Append or Prepend Content

If you want to draw some shape or add text or image at the beginning/end of a section, you can use the [AppendContent](https://reference.aspose.com/words/cpp/aspose.words/section/appendcontent/) and [PrependContent](https://reference.aspose.com/words/cpp/aspose.words/section/prependcontent/) methods of the [Section](https://reference.aspose.com/words/cpp/aspose.words/section/) class.

The following code example shows how to append content of an existing section:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "append-section-content.h" >}}

### Clone a Section

Aspose.Words allows you to duplicate a section by creating a full copy of it using the [Clone](https://reference.aspose.com/words/cpp/aspose.words/section/clone/) method.

The following code example shows how to clone the first section in your document:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "clone-section.h" >}}

### Copy Sections between Documents

In some cases, you may have large documents with many sections and you want to copy the content of a section from one document to another.

Aspose.Words allows you to copy sections between documents using the [ImportNode](https://reference.aspose.com/words/cpp/aspose.words/documentbase/importnode/) method.

The following code example shows how to copy sections between documents:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "copy-section.h" >}}

### Work with Section Header and Footer

The basic rules for displaying a header or footer for each section are quite simple:

1. If the section does not have its own headers/footers of a certain type, then it is taken from the previous section.
2. The type of header/footer displayed on the page is controlled by the "Different First Page" and "Different Odd & Even pages" section settings – if they are disabled, then the section's own titles are ignored.

The following code example shows how to create 2 sections with different headers:

{{< gist "aspose-words-gists" "e26133cadfcbe798f1ae301e2941f5ff" "link-to-previous-header-footer.h" >}}

If you want to remove the text of headers and footers without removing [HeaderFooter](https://reference.aspose.com/words/cpp/aspose.words/headerfooter/) objects in your document, you can use the [ClearHeadersFooters](https://reference.aspose.com/words/cpp/aspose.words/section/clearheadersfooters/) method. In addition, you can use the [DeleteHeaderFooterShapes](https://reference.aspose.com/words/cpp/aspose.words/section/deleteheaderfootershapes/) method to remove all shapes from headers and footers in your document.

The following code example shows how to clear content of all headers and footers in a section:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "delete-header-footer-content.h" >}}

The following code example how to remove all shapes from all headers footers in a section:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "delete-header-footer-shapes.h" >}}

## Customize Page Properties in a Section

Before printing a page or a document you may want to customize and modify the size and layout of a single page or the whole document. With page setup, you can change the settings of document pages such as margins, orientation, and size for printing different first pages or odd pages.

Aspose.Words allows you to customize page and section properties using the [PageSetup](https://reference.aspose.com/words/cpp/aspose.words/pagesetup/) class.

The following code example shows how to set such properties as page size and orientation for the current section:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "page-setup-and-section-formatting.h" >}}

The following code example shows how to modify the page properties in all sections:

{{< gist "aspose-words-gists" "11904531c9095a3c413adf28dbe3fe8d" "modify-page-setup-in-all-sections.h" >}}

## See Also

- [Logical Levels of Nodes in a Document](/words/cpp/logical-levels-of-nodes-in-a-document/)
- [Insert and Append Documents](/words/cpp/insert-and-append-documents/)

------ 

## FAQ

1. **Q:** How can I insert a section break at a specific location in a document?  
   **A:** Use `DocumentBuilder::InsertBreak` with the appropriate `BreakType` value (e.g., `BreakType::SectionBreakNewPage`). Position the builder where you want the break, then call the method.  

   ```cpp
   auto doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   auto builder = System::MakeObject<Aspose::Words::DocumentBuilder>(doc);
   // Move to the desired location
   builder->MoveToParagraph(5, 0);
   // Insert a new page section break
   builder->InsertBreak(Aspose::Words::BreakType::SectionBreakNewPage);
   doc->Save(u"output.docx");
   ```

2. **Q:** What is the recommended way to remove an entire section or just its content?  
   **A:** To delete a whole section, remove it from the `Sections` collection: `doc->get_Sections()->RemoveAt(index)`. To keep the section but clear its body, call `section->ClearContent()`.  

   ```cpp
   auto doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   // Remove the third section completely
   doc->get_Sections()->RemoveAt(2);
   // Or clear content of the first section
   System::SharedPtr<Aspose::Words::Section> firstSection = doc->get_FirstSection();
   firstSection->ClearContent();
   doc->Save(u"output.docx");
   ```

3. **Q:** How can I copy a section from one document into another document?  
   **A:** Import the source section node into the target document with `DocumentBase::ImportNode`, then add it to the target's `Sections` collection.  

   ```cpp
   auto sourceDoc = System::MakeObject<Aspose::Words::Document>(u"source.docx");
   auto targetDoc = System::MakeObject<Aspose::Words::Document>(u"target.docx");
   System::SharedPtr<Aspose::Words::Section> sourceSection = sourceDoc->get_Sections()->idx_get(0);
   System::SharedPtr<Aspose::Words::Node> imported = targetDoc->ImportNode(sourceSection, true);
   targetDoc->get_Sections()->Add(System::ExplicitCast<Aspose::Words::Section>(imported));
   targetDoc->Save(u"merged.docx");
   ```

4. **Q:** How do I duplicate a section within the same document?  
   **A:** Call `Section::Clone(true)` to create a deep copy, then insert the cloned section at the desired position in the `Sections` collection.  

   ```cpp
   auto doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   System::SharedPtr<Aspose::Words::Section> original = doc->get_Sections()->idx_get(0);
   System::SharedPtr<Aspose::Words::Section> clone = System::ExplicitCast<Aspose::Words::Section>(original->Clone(true));
   doc->get_Sections()->Insert(1, clone); // Insert after the first section
   doc->Save(u"output.docx");
   ```

5. **Q:** How can I clear all headers and footers (including shapes) from a specific section?  
   **A:** Use `Section::ClearHeadersFooters()` to remove header/footer text, then `Section::DeleteHeaderFooterShapes()` to delete any shapes inside them.  

   ```cpp
   auto doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   System::SharedPtr<Aspose::Words::Section> sec = doc->get_Sections()->idx_get(0);
   sec->ClearHeadersFooters();
   sec->DeleteHeaderFooterShapes();
   doc->Save(u"output.docx");
   ```