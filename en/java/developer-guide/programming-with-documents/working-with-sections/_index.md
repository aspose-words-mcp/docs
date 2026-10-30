---
title: Working with Sections in Java
second_title: Aspose.Words for Java
articleTitle: Working with Sections
linktitle: Working with Sections
description: "Understanding document section concepts and manipulation practices using Java. Insert section into a document Java. Remove section Java. Copy sections between Documents."
type: docs
weight: 120
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-sections/
aliases: [/java/how-to-remove-page-and-section-breaks/]
timestamp: 2024-01-31-14-23-37
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

Document sections are represented by the [Section](https://reference.aspose.com/words/java/com.aspose.words/section/) and [SectionCollection](https://reference.aspose.com/words/java/com.aspose.words/sectioncollection/) classes. Section objects are immediate children of the [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) node and can be accessed via the [getSections()](https://reference.aspose.com/words/java/com.aspose.words/document/#getSections) property. You can manage those nodes by using some methods such as [remove()](https://reference.aspose.com/words/java/com.aspose.words/nodecollection/#remove-com.aspose.words.Node), [add()](https://reference.aspose.com/words/java/com.aspose.words/nodecollection/#add-com.aspose.words.Node), [indexOf()](https://reference.aspose.com/words/java/com.aspose.words/nodecollection/#indexOf-com.aspose.words.Node), and others.

Section break is an option that divides document pages into sections with customizable layouts.

## Types of a Section Break

Aspose.Words allows you to split and format documents using different section breaks of the [BreakType](https://reference.aspose.com/words/java/com.aspose.words/breaktype/) enumeration:

* SectionBreakContinuous
* SectionBreakNewColumn
* SectionBreakNewPage
* SectionBreakEvenPage
* SectionBreakOddPage

You can also use the [SectionStart](https://reference.aspose.com/words/java/com.aspose.words/sectionstart/) enumeration to choose a break type that applies only for the first section such as NewColumn, NewPage, EvenPage, and OddPage.

## Manage a Section

Since a section is a normal composite node, the entire node manipulation API can be used to manipulate sections: to add, remove, and other operations on sections. You can read more about nodes in the article [Aspose.Words Document Object Model (DOM)](/words/java/aspose-words-document-object-model/).

On the other hand, you can also use the `DocumentBuilder` API to work with sections. In this article, we will focus on this particular way of working with sections.

## Insert or Remove a Section Break

Aspose.Words allows you to insert a section break into text using the [insertBreak()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertBreak-int) method.

The following code example shows how to insert a section break into a document:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "insert-section-breaks.java" >}}

Use the [remove()](https://reference.aspose.com/words/java/com.aspose.words/node/#remove) method to delete a section break. If you do not need to remove a specific section break and instead delete the content of that section, you can use the [clearContent()](https://reference.aspose.com/words/java/com.aspose.words/section/#clearContent) method.

The following code example shows how to remove sections breaks: 

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "remove-section-breaks.java" >}}

{{% alert color="primary" %}}

Note that a section break has information about the section that goes before it, not the section that goes after it. So if you remove a section break, the text before the removed break will get the properties of the section break following it. This can cause the entire document to becoming landscape, or headers and footers to change or fully disappear.

{{% /alert %}}

## Move a Section

If you want to move a section from one position to another in your document, you need to get the index of that section. Aspose.Words allows you to get a section position from a [SectionCollection](https://reference.aspose.com/words/java/com.aspose.words/sectioncollection/) by using the [getSections()](https://reference.aspose.com/words/java/com.aspose.words/document/#getSections) property. You can use the [getFirstSection()](https://reference.aspose.com/words/java/com.aspose.words/document/#getFirstSection) property to get all sections in your document. But if you want to get only the first section, you can use the [getFirstSection()](https://reference.aspose.com/words/java/com.aspose.words/document/#getFirstSection) property.

The following code example shows how to access the first section and iterate through the children of a composite node:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "section-child-nodes.java" >}}

## Specify a Section Layout

Sometimes you want your document to look better by making creative layouts for different document sections. If you want to specify the type of the current section grid, you can choose a section layout mode using the [SectionLayoutMode](https://reference.aspose.com/words/java/com.aspose.words/sectionlayoutmode/) enumeration:

* Default
* Grid
* LineGrid
* SnapToChars

The following code example shows how to limit the number of lines that each page may have:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "line-grid-section-layout-mode.java" >}}

## Edit a Section

When you add a new section to your document, there will be no body or paragraph that you can edit. Aspose.Words allows you to guarantee that a section contains a body with at least one paragraph using the [ensureMinimum()](https://reference.aspose.com/words/java/com.aspose.words/section/#ensureMinimum) method – it will automatically add a Body (or HeaderFooter) node to the document and then add a Paragraph to it.

The following code example shows how to prepare a new section node using **ensureMinimum()**:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "ensure-minimum.java" >}}

### Append or Prepend Content

If you want to draw some shape or add text or image at the beginning/end of a section, you can use the [appendContent()](https://reference.aspose.com/words/java/com.aspose.words/section/#appendContent-com.aspose.words.Section) and [prependContent()](https://reference.aspose.com/words/java/com.aspose.words/section/#prependContent-com.aspose.words.Section) methods of the [Section](https://reference.aspose.com/words/java/com.aspose.words/section/) class.

The following code example shows how to append content of an existing section:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "append-section-content.java" >}}

### Clone a Section

Aspose.Words allows you to duplicate a section by creating a full copy of it using the [deepClone](https://reference.aspose.com/words/java/com.aspose.words/section/#deepClone) method.

The following code example shows how to clone the first section in your document:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "clone-section.java" >}}

### Copy Sections between Documents

In some cases, you may have large documents with many sections and you want to copy the content of a section from one document to another.

Aspose.Words allows you to copy sections between documents using the [importNode()](https://reference.aspose.com/words/java/com.aspose.words/documentbase/#importNode-com.aspose.words.Node-boolean) method.

The following code example shows how to copy sections between documents:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "copy-section.java" >}}

### Work with Section Header and Footer

The basic rules for displaying a header or footer for each section are quite simple:

1. If the section does not have its own headers/footers of a certain type, then it is taken from the previous section.
2. The type of header/footer displayed on the page is controlled by the "Different First Page" and "Different Odd & Even pages" section settings – if they are disabled, then the section's own titles are ignored.

The following code example shows how to create 2 sections with different headers:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "link-to-previous-header-footer.java" >}}

If you want to remove the text of headers and footers without removing [HeaderFooter](https://reference.aspose.com/words/java/com.aspose.words/headerfooter/) objects in your document, you can use the [clearHeadersFooters()](https://reference.aspose.com/words/java/com.aspose.words/section/#clearHeadersFooters) method. In addition, you can use the [deleteHeaderFooterShapes()](https://reference.aspose.com/words/java/com.aspose.words/section/#deleteHeaderFooterShapes) method to remove all shapes from headers and footers in your document.

The following code example shows how to clear content of all headers and footers in a section:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "delete-header-footer-content.java" >}}

The following code example how to remove all shapes from all headers footers in a section:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "delete-header-footer-shapes.java" >}}

## Customize Page Properties in a Section

Before printing a page or a document you may want to customize and modify the size and layout of a single page or the whole document. With page setup, you can change the settings of document pages such as margins, orientation, and size for printing different first pages or odd pages.

Aspose.Words allows you to customize page and section properties using the [PageSetup](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/) class.

The following code example shows how to set such properties as page size and orientation for the current section:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "page-setup-and-section-formatting.java" >}}

The following code example shows how to modify the page properties in all sections:

{{< gist "aspose-words-gists" "7c0668453e53ed7a57d3ea3a05520f21" "modify-page-setup-in-all-sections.java" >}}

## See Also

* [Logical Levels of Nodes in a Document](/words/java/logical-levels-of-nodes-in-a-document/#document-and-section-logical-level)
* [Insert and Append Documents](/words/java/insert-and-append-documents/)

## Limitations and Considerations

- When removing a section break, the section *before* the break adopts the formatting (including page setup, headers, and footers) of the section *after* the break. This is the opposite of what many developers expect. To avoid unintended layout changes, ensure you understand the section order before removal.

- The `ensureMinimum()` method only ensures the presence of a `Body` and at least one `Paragraph`. It does *not* create `HeaderFooter` nodes. To add a header or footer, create it and add it to the section, e.g., `section.getHeadersFooters().add(new HeaderFooter(doc, HeaderFooterType.HEADER_PRIMARY))`.

`Section.deepClone()` copies the section together with its `HeaderFooter` nodes. To insert the copy into another document, import it with `importNode` or `NodeImporter`. To stop a section from using the headers and footers of the previous section, call `section.getHeadersFooters().linkToPrevious(false)`.

When copying sections between documents using `NodeImporter.importNode()`, specify `ImportFormatMode.KEEP_SOURCE_FORMATTING` to preserve source formatting. Without it, the section may adopt formatting from the target document, potentially causing layout shifts.

Headers and footers are inherited from the previous section unless the current section has its own HeaderFooter nodes. To break the inheritance and enable independent editing, create or import a HeaderFooter for the desired type (e.g., HeaderFooterType.HEADER_PRIMARY) and ensure the section's PageSetup settings match your intent, e.g.:
```java
Section section = ...;
section.getPageSetup().setDifferentFirstPageHeaderFooter(true);
section.getPageSetup().setOddAndEvenPagesHeaderFooter(true);
```

- `PageSetup.getLayoutMode()` (see `SectionLayoutMode`) defines the document grid behavior of a section.

{{% alert color="primary" %}}

For additional details, see the official documentation:
- [Section Class](https://reference.aspose.com/words/java/com.aspose.words/section/)
- [SectionCollection Class](https://reference.aspose.com/words/java/com.aspose.words/sectioncollection/)
- [PageSetup Class](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/)
- [HeaderFooter Class](https://reference.aspose.com/words/java/com.aspose.words/headerfooter/)

{{% /alert %}}

## FAQ

1. **Q:** How can I insert a section break at a specific location in a Java document?  
   **A:** Use `DocumentBuilder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE)` (or another `BreakType`) at the desired cursor position. Create a `DocumentBuilder` for the document, move the cursor to the target node, then call `insertBreak`.  

2. **Q:** What is the safest way to remove a section break without losing the formatting of surrounding sections?  
   **A:** Copy the content of the section before the break to the beginning of the next section with `nextSection.prependContent(section)`, then remove the copied section with `section.remove()`, as in the code example above. Removing the section alone deletes its content. After the break is removed, the content before it takes the page setup of the following section, so copy the required `PageSetup` settings first if you need them.  

3. **Q:** How do I clone a section and insert the clone into the same document or another document?  
   **A:** Call `Section clonedSection = (Section) originalSection.deepClone();` and then add it to the target document's `Sections` collection with `targetDoc.getSections().add(clonedSection);`. If the target document is different, import the cloned node first using `targetDoc.importNode(clonedSection, true)`.  

4. **Q:** How can I set different headers or footers for the first page and for odd/even pages within a section?  
   **A:** Access the `Section` object and set `section.getPageSetup().setDifferentFirstPageHeaderFooter(true);` and `section.getPageSetup().setOddAndEvenPagesHeaderFooter(true);`. Then create or modify the `HeaderFooter` objects for `HeaderFooterType.HEADER_FIRST`, `HEADER_EVEN`, and `HEADER_PRIMARY` as needed.  

5. **Q:** How can I change the page size and orientation for only one section?  
   **A:** Retrieve the `Section` you want to modify and use its `PageSetup` property:  

   ```java
   Section section = doc.getSections().get(2); // example index
   PageSetup setup = section.getPageSetup();
   setup.setPaperSize(PaperSize.A4);
   setup.setOrientation(Orientation.LANDSCAPE);
   ```  

   This affects only the selected section, leaving other sections unchanged.