---
title: Working with Sections in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Sections
linktitle: Working with Sections
description: "Create and manage sections and section breaks in a document using Node.js. Insert section into a document Node.js. Remove section Node.js. Copy sections between Documents."
type: docs
weight: 120
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-sections/
timestamp: 2024-09-25-11-08-55
---

Sometimes you want a document that does not have the same formatting across all pages. For example, you may need to modify page number formats, have different page size and orientation, or have the first document page as a cover page without any numbering. You can achieve that with sections.

Sections are level nodes that control headers and footers, orientation, columns, margins, page number formatting, and others.

Aspose.Words allows you to manage sections, divide a document into sections, and make formatting changes that apply only to a specific section. Aspose.Words stores information about section formatting such as headers and footers, page setup, and column settings in the section break.

This article explains how to work with sections and section breaks.

## What Section and Section Break Is

Document sections are represented by the [Section](https://reference.aspose.com/words/nodejs-net/aspose.words/section/) and [SectionCollection](https://reference.aspose.com/words/nodejs-net/aspose.words/sectioncollection/) classes. Section objects are immediate children of the [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/) node and can be accessed via the [sections](https://reference.aspose.com/words/nodejs-net/aspose.words/document/sections/) property. You can manage those nodes by using some methods such as [remove](https://reference.aspose.com/words/nodejs-net/aspose.words/nodecollection/remove/#node), [add](https://reference.aspose.com/words/nodejs-net/aspose.words/nodecollection/add/), [indexOf](https://reference.aspose.com/words/nodejs-net/aspose.words/nodecollection/indexof/), and others.

Section break is an option that divides document pages into sections with customizable layouts.

## Types of a Section Break

Aspose.Words allows you to split and format documents using different section breaks of the [BreakType](https://reference.aspose.com/words/nodejs-net/aspose.words/breaktype/) enumeration:

- SectionBreakContinuous
- SectionBreakNewColumn
- SectionBreakNewPage
- SectionBreakEvenPage
- SectionBreakOddPage

You can also use the [SectionStart](https://reference.aspose.com/words/nodejs-net/aspose.words/sectionstart/) enumeration to choose a break type that applies only for the first section such as NewColumn, NewPage, EvenPage, and OddPage.

## Manage a Section

Since a section is a normal composite node, the entire node manipulation API can be used to manipulate sections: to add, remove, and other operations on sections. You can read more about nodes in the article [Aspose.Words Document Object Model (DOM)](/words/nodejs-net/aspose-words-document-object-model/).

On the other hand, you can also use the `DocumentBuilder` API to work with sections. In this article, we will focus on this particular way of working with sections.

## Insert or Remove a Section Break

Aspose.Words allows you to insert a section break into text using the [insertBreak](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertbreak/) method.

The following code example shows how to insert a section break into a document:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "insert-section-breaks.js" >}}

Use the [remove](https://reference.aspose.com/words/nodejs-net/aspose.words/node/remove/) method to delete a section break. If you do not need to remove a specific section break and instead delete the content of that section, you can use the [clearContent](https://reference.aspose.com/words/nodejs-net/aspose.words/section/clearcontent/) method.

The following code example shows how to remove sections breaks: 

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "remove-section-breaks.js" >}}

{{% alert color="primary" %}}

Note that a section break has information about the section that goes before it, not the section that goes after it. So if you remove a section break, the text before the removed break will get the properties of the section break following it. This can cause the entire document to becoming landscape, or headers and footers to change or fully disappear.

{{% /alert %}}

## Move a Section

If you want to move a section from one position to another in your document, you need to get the index of that section. Aspose.Words allows you to get a section position from a [SectionCollection](https://reference.aspose.com/words/nodejs-net/aspose.words/sectioncollection/). You can use the [sections](https://reference.aspose.com/words/nodejs-net/aspose.words/document/sections/) property to get all sections in your document. But if you want to get only the first section, you can use the [firstSection](https://reference.aspose.com/words/nodejs-net/aspose.words/document/firstsection/) property.

The following code example shows how to access the first section and iterate through the children of a composite node:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "section-child-nodes.js" >}}

## Specify a Section Layout

Sometimes you want your document to look better by making creative layouts for different document sections. If you want to specify the type of the current section grid, you can choose a section layout mode using the [SectionLayoutMode](https://reference.aspose.com/words/nodejs-net/aspose.words/sectionlayoutmode/) enumeration:

- Default
- Grid
- LineGrid
- SnapToChars

The following code example shows how to limit the number of lines that each page may have:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "line-grid-section-layout-mode.js" >}}

## Edit a Section

When you add a new section to your document, there will be no body or paragraph that you can edit. Aspose.Words allows you to guarantee that a section contains a body with at least one paragraph using the [ensureMinimum](https://reference.aspose.com/words/nodejs-net/aspose.words/section/ensureminimum/) method – it will automatically add a Body (or HeaderFooter) node to the document and then add a Paragraph to it.

The following code example shows how to prepare a new section node using **ensureMinimum**:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "ensure-minimum.js" >}}

### Append or Prepend Content

If you want to draw some shape or add text or image at the beginning/end of a section, you can use the [appendContent](https://reference.aspose.com/words/nodejs-net/aspose.words/section/appendcontent/) and [prependContent](https://reference.aspose.com/words/nodejs-net/aspose.words/section/prependcontent/) methods of the [Section](https://reference.aspose.com/words/nodejs-net/aspose.words/section/) class.

The following code example shows how to append content of an existing section:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "append-section-content.js" >}}

### Clone a Section

Aspose.Words allows you to duplicate a section by creating a full copy of it using the [clone](https://reference.aspose.com/words/nodejs-net/aspose.words/section/clone/) method.

The following code example shows how to clone the first section in your document:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "clone-section.js" >}}

### Copy Sections between Documents

In some cases, you may have large documents with many sections and you want to copy the content of a section from one document to another.

Aspose.Words allows you to copy sections between documents using the [importNode](https://reference.aspose.com/words/nodejs-net/aspose.words/nodeimporter/importnode/) method.

The following code example shows how to copy sections between documents:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "copy-section.js" >}}

### Work with Section Header and Footer

The basic rules for displaying a header or footer for each section are quite simple:

1. If the section does not have its own headers/footers of a certain type, then it is taken from the previous section.
2. The type of header/footer displayed on the page is controlled by the "Different First Page" and "Different Odd & Even pages" section settings – if they are disabled, then the section's own titles are ignored.

The following code example shows how to create 2 sections with different headers:

{{< gist "aspose-words-gists" "af238004afed43ffa79beb305a41e642" "link-to-previous-header-footer.js" >}}

If you want to remove the text of headers and footers without removing [HeaderFooter](https://reference.aspose.com/words/nodejs-net/aspose.words/headerfooter/) objects in your document, you can use the [clearHeadersFooters](https://reference.aspose.com/words/nodejs-net/aspose.words/section/clearheadersfooters/) method. In addition, you can use the [deleteHeaderFooterShapes](https://reference.aspose.com/words/nodejs-net/aspose.words/section/deleteheaderfootershapes/) method to remove all shapes from headers and footers in your document.

The following code example shows how to clear content of all headers and footers in a section:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "delete-header-footer-content.js" >}}

The following code example how to remove all shapes from all headers footers in a section:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "delete-header-footer-shapes.js" >}}

## Customize Page Properties in a Section

Before printing a page or a document you may want to customize and modify the size and layout of a single page or the whole document. With page setup, you can change the settings of document pages such as margins, orientation, and size for printing different first pages or odd pages.

Aspose.Words allows you to customize page and section properties using the [PageSetup](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/) class.

The following code example shows how to set such properties as page size and orientation for the current section:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "page-setup-and-section-formatting.js" >}}

The following code example shows how to modify the page properties in all sections:

{{< gist "aspose-words-gists" "5331edc61a2137fd92565f1e0c953887" "modify-page-setup-in-all-sections.js" >}}

## See Also

- [Logical Levels of Nodes in a Document](/words/nodejs-net/logical-levels-of-nodes-in-a-document/#document-and-section-logical-level)
- [Insert and Append Documents](/words/nodejs-net/insert-and-append-documents/)
