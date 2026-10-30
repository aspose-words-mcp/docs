---
title: Working with Sections in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Sections
linktitle: Working with Sections
description: "Understanding document section concepts and manipulation practices using C#. Insert section into a document C#. Remove section C#. Copy sections between Documents."
type: docs
weight: 120
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-sections/
timestamp: 2024-09-25-11-08-55
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with document sections.

{{% /alert %}}

Sometimes you want a document that does not have the same formatting across all pages. For example, you may need to modify page number formats, have different page size and orientation, or have the first document page as a cover page without any numbering. You can achieve that with sections.

Sections are level nodes that control headers and footers, orientation, columns, margins, page number formatting, and others.

Aspose.Words allows you to manage sections, divide a document into sections, and make formatting changes that apply only to a specific section. Aspose.Words stores information about section formatting such as headers and footers, page setup, and column settings in the section break.

This article explains how to work with sections and section breaks.

## What Section and Section Break Is

Document sections are represented by the [Section](https://reference.aspose.com/words/net/aspose.words/section/) and [SectionCollection](https://reference.aspose.com/words/net/aspose.words/sectioncollection/) classes. Section objects are immediate children of the [Document](https://reference.aspose.com/words/net/aspose.words/document/) node and can be accessed via the [Sections](https://reference.aspose.com/words/net/aspose.words/document/sections/) property. You can manage those nodes by using some methods such as [Remove](https://reference.aspose.com/words/net/aspose.words/nodecollection/remove/), [Add](https://reference.aspose.com/words/net/aspose.words/nodecollection/add/), [IndexOf](https://reference.aspose.com/words/net/aspose.words/nodecollection/indexof/), and others.

Section break is an option that divides document pages into sections with customizable layouts.

## Types of a Section Break

Aspose.Words allows you to split and format documents using different section breaks of the [BreakType](https://reference.aspose.com/words/net/aspose.words/breaktype/) enumeration:

* SectionBreakContinuous
* SectionBreakNewColumn
* SectionBreakNewPage
* SectionBreakEvenPage
* SectionBreakOddPage

You can also use the [SectionStart](https://reference.aspose.com/words/net/aspose.words/sectionstart/) enumeration to choose a break type that applies only for the first section such as NewColumn, NewPage, EvenPage, and OddPage.

## Manage a Section

Since a section is a normal composite node, the entire node manipulation API can be used to manipulate sections: to add, remove, and other operations on sections. You can read more about nodes in the article [Aspose.Words Document Object Model (DOM)](/words/net/aspose-words-document-object-model/).

On the other hand, you can also use the `DocumentBuilder` API to work with sections. In this article, we will focus on this particular way of working with sections.

## Insert or Remove a Section Break

Aspose.Words allows you to insert a section break into text using the [InsertBreak](https://reference.aspose.com/words/net/aspose.words/documentbuilder/insertbreak/) method.

The following code example shows how to insert a section break into a document:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "insert-section-breaks.cs" >}}

Use the [Remove](https://reference.aspose.com/words/net/aspose.words/node/remove/) method to delete a section break. If you do not need to remove a specific section break and instead delete the content of that section, you can use the [ClearContent](https://reference.aspose.com/words/net/aspose.words/section/clearcontent/) method.

The following code example shows how to remove sections breaks: 

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "remove-section-breaks.cs" >}}

{{% alert color="primary" %}}

Note that a section break has information about the section that goes before it, not the section that goes after it. So if you remove a section break, the text before the removed break will get the properties of the section break following it. This can cause the entire document to becoming landscape, or headers and footers to change or fully disappear.

{{% /alert %}}

## Move a Section

If you want to move a section from one position to another in your document, you need to get the index of that section. Aspose.Words allows you to get a section position from a [SectionCollection](https://reference.aspose.com/words/net/aspose.words/sectioncollection/) by using the [Item](https://reference.aspose.com/words/net/aspose.words/sectioncollection/item/) property. You can use the [Sections](https://reference.aspose.com/words/net/aspose.words/document/sections/) property to get all sections in your document. But if you want to get only the first section, you can use the [FirstSection](https://reference.aspose.com/words/net/aspose.words/document/firstsection/) property.

The following code example shows how to access the first section and iterate through the children of a composite node:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "section-child-nodes.cs" >}}

## Specify a Section Layout

Sometimes you want your document to look better by making creative layouts for different document sections. If you want to specify the type of the current section grid, you can choose a section layout mode using the [SectionLayoutMode](https://reference.aspose.com/words/net/aspose.words/sectionlayoutmode/) enumeration:

* Default
* Grid
* LineGrid
* SnapToChars

The following code example shows how to limit the number of lines that each page may have:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "line-grid-section-layout-mode.cs" >}}

## Edit a Section

When you add a new section to your document, there will be no body or paragraph that you can edit. Aspose.Words allows you to guarantee that a section contains a body with at least one paragraph using the [EnsureMinimum](https://reference.aspose.com/words/net/aspose.words/section/ensureminimum/) method – it will automatically add a Body (or HeaderFooter) node to the document and then add a Paragraph to it.

The following code example shows how to prepare a new section node using **EnsureMinimum**:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "ensure-minimum.cs" >}}

### Append or Prepend Content

If you want to draw some shape or add text or image at the beginning/end of a section, you can use the [AppendContent](https://reference.aspose.com/words/net/aspose.words/section/appendcontent/) and [PrependContent](https://reference.aspose.com/words/net/aspose.words/section/prependcontent/) methods of the [Section](https://reference.aspose.com/words/net/aspose.words/section/) class.

The following code example shows how to append content of an existing section:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "append-section-content.cs" >}}

### Clone a Section

Aspose.Words allows you to duplicate a section by creating a full copy of it using the [Clone](https://reference.aspose.com/words/net/aspose.words/section/clone/) method.

The following code example shows how to clone the first section in your document:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "clone-section.cs" >}}

### Copy Sections between Documents

In some cases, you may have large documents with many sections and you want to copy the content of a section from one document to another.

Aspose.Words allows you to copy sections between documents using the [ImportNode](https://reference.aspose.com/words/net/aspose.words/nodeimporter/importnode/) method.

The following code example shows how to copy sections between documents:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "copy-section.cs" >}}

### Work with Section Header and Footer

The basic rules for displaying a header or footer for each section are quite simple:

1. If the section does not have its own headers/footers of a certain type, then it is taken from the previous section.
2. The type of header/footer displayed on the page is controlled by the "Different First Page" and "Different Odd & Even pages" section settings – if they are disabled, then the section's own titles are ignored.

The following code example shows how to create 2 sections with different headers:

{{< gist "aspose-words-gists" "84cab3a22008f041ee6c1e959da09949" "link-to-previous-header-footer.cs" >}}

If you want to remove the text of headers and footers without removing [HeaderFooter](https://reference.aspose.com/words/net/aspose.words/headerfooter/) objects in your document, you can use the [ClearHeadersFooters](https://reference.aspose.com/words/net/aspose.words/section/clearheadersfooters/) method. In addition, you can use the [DeleteHeaderFooterShapes](https://reference.aspose.com/words/net/aspose.words/section/deleteheaderfootershapes/) method to remove all shapes from headers and footers in your document.

The following code example shows how to clear content of all headers and footers in a section:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "delete-header-footer-content.cs" >}}

The following code example how to remove all shapes from all headers footers in a section:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "delete-header-footer-shapes.cs" >}}

## Customize Page Properties in a Section

Before printing a page or a document you may want to customize and modify the size and layout of a single page or the whole document. With page setup, you can change the settings of document pages such as margins, orientation, and size for printing different first pages or odd pages.

Aspose.Words allows you to customize page and section properties using the [PageSetup](https://reference.aspose.com/words/net/aspose.words/pagesetup/) class.

The following code example shows how to set such properties as page size and orientation for the current section:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "page-setup-and-section-formatting.cs" >}}

The following code example shows how to modify the page properties in all sections:

{{< gist "aspose-words-gists" "1afca4d3da7cb4240fb91c3d93d8c30d" "modify-page-setup-in-all-sections.cs" >}}

## See Also

* [Logical Levels of Nodes in a Document](/words/net/logical-levels-of-nodes-in-a-document/#document-and-section-logical-level)
* [Insert and Append Documents](/words/net/insert-and-append-documents/)

## Limitations and Considerations

- When removing a section break, the section *before* the break adopts the formatting (including page setup, headers, and footers) of the section *after* the break. This is the opposite of what many developers expect. To avoid unintended layout changes, ensure you understand the section order before removal.

- The `EnsureMinimum()` method only ensures the presence of a `Body` and at least one `Paragraph`. It does *not* create `HeaderFooter` nodes.

- `Section.Clone()` copies the section together with its `HeaderFooter` nodes. To insert the copy into another document, import it with `ImportNode` or `NodeImporter`. To stop a section from using the headers and footers of the previous section, call `section.HeadersFooters.LinkToPrevious(false)`.

- When copying sections between documents using `NodeImporter.ImportNode()`, specify `ImportFormatMode.KeepSourceFormatting` to preserve source formatting. Without it, the section may adopt formatting from the target document, potentially causing layout shifts.

- Headers and footers are inherited from the previous section *unless* the current section has its own `HeaderFooter` nodes. To break the inheritance and enable independent editing, create or import a `HeaderFooter` for the desired type (e.g., `HeaderFooterType.HeaderPrimary`) and ensure the section's `PageSetup.DifferentFirstPageHeaderFooter` and `PageSetup.OddAndEvenPagesHeaderFooter` settings match your intent.

- `PageSetup.LayoutMode` (see `SectionLayoutMode`) defines the document grid behavior of a section.

{{% alert color="primary" %}}

For additional details, see the official documentation:
- [Section Class](https://reference.aspose.com/words/net/aspose.words/section/)
- [SectionCollection Class](https://reference.aspose.com/words/net/aspose.words/sectioncollection/)
- [PageSetup Class](https://reference.aspose.com/words/net/aspose.words/pagesetup/)
- [HeaderFooter Class](https://reference.aspose.com/words/net/aspose.words/headerfooter/)

{{% /alert %}}

------

## FAQ

1. **Q:** How can I insert a section break at a specific location in a document?  
   **A:** Use `DocumentBuilder.InsertBreak` with the desired `BreakType`. Position the builder where you want the break, then call the method. The new section will inherit the formatting of the preceding section unless you modify its `PageSetup` afterwards.  

   ```csharp
   Document doc = new Document();
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.Writeln("First part of the document.");
   builder.InsertBreak(BreakType.SectionBreakNewPage); // inserts a new section
   builder.Writeln("Content of the new section.");
   ```

2. **Q:** How can I copy a section from one document into another document?  
   **A:** Import the section node using `NodeImporter.ImportNode` with `ImportFormatMode.KeepSourceFormatting`. Then add the imported node to the target document's `Sections` collection.  

   ```csharp
   Document source = new Document("Source.docx");
   Document target = new Document();

   Section sourceSection = source.Sections[0];
   Section importedSection = (Section)target.ImportNode(sourceSection, true, ImportFormatMode.KeepSourceFormatting);
   target.Sections.Add(importedSection);

   target.Save("Target.docx");
   ```