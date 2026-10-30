---
title: Working with Headers and Footers in Java
second_title: Aspose.Words for Java
articleTitle: Working with Headers and Footers
linktitle: Working with Headers and Footers
description: "How to manipulate headers and footers using Java. Create headers and footers Java. Remove headers or footers Java."
type: docs
weight: 150
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-headers-and-footers/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with headers and footers using Aspose.Words.

{{% /alert %}}

Aspose.Words allows users to work with headers and footers in a document. A header is text that is placed at the top of a page, and a footer is text at the bottom of a page. Typically, these areas are used to insert information that should be repeated on all or some pages of the document, such as page numbers, creation date, company information, and so on.

## Create Headers or Footers using DocumentBuilder

If you want to add a document header or footer programmatically, the easiest way is to use the [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) class to do it.

The following code example shows how to add a header and footer for document pages:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "create-header-footer.java" >}}

## Specify Header or Footer Options

When you add a header or footer to a document, you can set some advanced properties. Aspose.Words provides users with the [HeaderFooter](https://reference.aspose.com/words/java/com.aspose.words/headerfooter/) and [HeaderFooterCollection](https://reference.aspose.com/words/java/com.aspose.words/headerfootercollection/) classes, as well as [HeaderFooterType](https://reference.aspose.com/words/java/com.aspose.words/headerfootertype/) enumeration that give you more control over the header and footer customization process.

### Specify Header or Footer Type

You can specify three different header types and three different footer types for one document:
1. Header and/or footer for the first page
2. Header and/or footer for even pages
3. Header and/or footer for odd pages

The following code example shows how to add a header for odd document pages:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "header-footer-type.java" >}}

### Specify Whether to Display Different Headers or Footers for the First Page

As said above, you can also set a different header or footer for the first page. To do this, you need to set the [getDifferentFirstPageHeaderFooter()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getDifferentFirstPageHeaderFooter) flag to `true` and then specify the **HEADER_FIRST** or **FOOTER_FIRST** value.

The following code example shows how to set the header for the first page only:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "different-first-page.java" >}}

### Specify Whether to Display Different Headers or Footers for Odd or Even Pages

 Next, you will want to set different headers or footers for odd and even pages in a document. To do this, you need to set the [getOddAndEvenPagesHeaderFooter()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getOddAndEvenPagesHeaderFooter) flag to `true` and then specify the values **HEADER_PRIMARY** and **HEADER_EVEN**, or **FOOTER_PRIMARY** and **FOOTER_EVEN**.

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "odd-even-pages.java" >}}

### Insert an Absolutely Positioned Image into the Header

To place an image in a header or footer, use the **HEADER_PRIMARY** header type or the **FOOTER_PRIMARY** footer type and the [InsertImage](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertImage-byte) method.

The following code example shows how to add an image to a header:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "insert-image.java" >}}

### Set Font and Paragraph Properties for Header or Footer Text

With Aspose.Words you can set the font and paragraph properties, use the **HEADER_PRIMARY** header type or the **FOOTER_PRIMARY** footer type, as well as methods and properties for working with the fonts and paragraphs you use for the document body.

The following code example shows how to set the text in the header to Arial, bold, size 14, and center alignment:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "font-props.java" >}}

### Insert Page Numbers into the Header or Footer

If necessary, you can add page numbers to the header or footer. To do this, use the **HEADER_PRIMARY** header type or the **FOOTER_PRIMARY** footer type and the [insertField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertField-int-boolean) method to add the required field.

The following code example shows how to add page numbers to the footer on the right:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "page-numbers.java" >}}

### Use Headers or Footers Defined in the Previous Section

If you need to copy the header or footer from the previous section, you can do that too.

The following code example shows how to copy the header or footer from the previous section:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "copy-headers-footers-from-previous-section.java" >}}

### Ensure Header or Footer appearance when Using Different Page Orientations and Page Size

Aspose.Words allows you to provide the appearance of a header or footer when using different orientations and page sizes.

The following example shows how to do this:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "link-to-previous-header-footer.java" >}}

## How to Remove Only Headers or Only Footers

Each section in a document can have up to three headers and up to three footers (for first, even, and odd pages). If you want to remove all headers or all footers in a document, you need to loop through all the sections and remove each corresponding header node or footer node.

The following code example shows how to remove all footers from all sections but leave headers intact. You can remove only headers in a similar way:

{{< gist "aspose-words-gists" "58431f54e34e5597f8cbaf97481d5321" "remove-footers.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Footer.docx).

{{% /alert %}}

## FAQ

1. **Q:** How can I set a different header or footer only for the first page of a document?  
   **A:** Set `PageSetup.setDifferentFirstPageHeaderFooter(true)` on the section. Then use `HeaderFooterType.HEADER_FIRST` or `FOOTER_FIRST` to access and edit the first‑page header/footer.

2. **Q:** What steps are required to have separate headers/footers for odd and even pages?  
   **A:** Enable `PageSetup.setOddAndEvenPagesHeaderFooter(true)`. After that, create or modify `HEADER_PRIMARY`/`FOOTER_PRIMARY` for odd pages and `HEADER_EVEN`/`FOOTER_EVEN` for even pages.

3. **Q:** How do I copy the header/footer from the previous section without recreating it manually?  
   **A:** Set `section.getHeadersFooters().linkToPrevious(true)`. The section will automatically use the header/footer objects from the preceding section.

4. **Q:** Can I use `DocumentBuilder` to move directly to a header or footer of a specific section?  
   **A:** Yes. Call `builder.moveToSection(sectionIndex)` and then `builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY)`. After moving, you can insert text, images, or fields.

5. **Q:** How can I remove only the footers (or only the headers) from every section in a document?  
   **A:** Iterate through `document.getSections()`. For each section, get each footer with `section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY)` (and `FOOTER_FIRST`, `FOOTER_EVEN`, or the corresponding header types) and call `remove()` on it if it is not `null`. This deletes only the unwanted parts.