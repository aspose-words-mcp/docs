---
title: Working with Headers and Footers
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Headers and Footers
linktitle: Working with Headers and Footers
description: "Create, manage, and remove headers and footers in a document using Python."
type: docs
weight: 150
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-headers-and-footers/
aliases: [/python/working-with-headers-and-footers/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to create, customize, and remove headers and footers in Word documents using Aspose.Words for Python via .NET, covering header/footer types, image insertion, font and paragraph settings, page numbers, and handling different page orientations and sections.
{{% /alert %}}

Aspose.Words allows users to work with headers and footers in a document. A header is text that is placed at the top of a page, and a footer is text at the bottom of a page. Typically, these areas are used to insert information that should be repeated on all or some pages of the document, such as page numbers, creation date, company information, and so on.

## Create Headers or Footers using DocumentBuilder

If you want to add a document header or footer programmatically, the easiest way is to use the [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) class to do it.

The following code example shows how to add a header and footer for document pages:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "create-header-footer.py" >}}

## Specify Header or Footer Options

When you add a header or footer to a document, you can set some advanced properties. Aspose.Words provides users with the [HeaderFooter](https://reference.aspose.com/words/python-net/aspose.words/headerfooter/) and [HeaderFooterCollection](https://reference.aspose.com/words/python-net/aspose.words/headerfootercollection/) classes, as well as [HeaderFooterType](https://reference.aspose.com/words/python-net/aspose.words/headerfootertype/) enumeration that give you more control over the header and footer customization process.

### Specify Header or Footer Type

You can specify three different header types and three different footer types for one document:
1. Header and/or footer for the first page
2. Header and/or footer for even pages
3. Header and/or footer for odd pages

The following code example shows how to add a header for odd document pages:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "header-footer-type.py" >}}

### Specify Whether to Display Different Headers or Footers for the First Page

As said above, you can also set a different header or footer for the first page. To do this, you need to set the [different_first_page_header_footer](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/different_first_page_header_footer/) flag to `true` and then specify the **HEADER_FIRST** or **FOOTER_FIRST** value.

The following code example shows how to set the header for the first page only:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "different-first-page.py" >}}

### Specify Whether to Display Different Headers or Footers for Odd or Even Pages

 Next, you will want to set different headers or footers for odd and even pages in a document. To do this, you need to set the [odd_and_even_pages_header_footer](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/odd_and_even_pages_header_footer/) flag to `true` and then specify the values **HEADER_PRIMARY** and **HEADER_EVEN**, or **FOOTER_PRIMARY** and **FOOTER_EVEN**.

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "odd-even-pages.py" >}}

### Insert an Absolutely Positioned Image into the Header

To place an image in a header or footer, use the **HEADER_PRIMARY** header type or the **FOOTER_PRIMARY** footer type and the [insert_image](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_image/) method.

The following code example shows how to add an image to a header:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "insert-image.py" >}}

### Set Font and Paragraph Properties for Header or Footer Text

With Aspose.Words you can set the font and paragraph properties, use the **HEADER_PRIMARY** header type or the **FOOTER_PRIMARY** footer type, as well as methods and properties for working with the fonts and paragraphs you use for the document body.

The following code example shows how to set the text in the header to Arial, bold, size 14, and center alignment:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "font-props.py" >}}

### Insert Page Numbers into the Header or Footer

If necessary, you can add page numbers to the header or footer. To do this, use the **HEADER_PRIMARY** header type or the **FOOTER_PRIMARY** footer type and the [insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/) method to add the required field.

The following code example shows how to add page numbers to the footer on the right:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "page-numbers.py" >}}

### Use Headers or Footers Defined in the Previous Section

If you need to copy the header or footer from the previous section, you can do that too.

The following code example shows how to copy the header or footer from the previous section:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "copy-headers-footers-from-previous-section.py" >}}

### Ensure Header or Footer appearance when Using Different Page Orientations and Page Size

Aspose.Words allows you to provide the appearance of a header or footer when using different orientations and page sizes.

The following example shows how to do this:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "link-to-previous-header-footer.py" >}}

## How to Remove Only Headers or Only Footers

Each section in a document can have up to three headers and up to three footers (for first, even, and odd pages). If you want to remove all headers or all footers in a document, you need to loop through all the sections and remove each corresponding header node or footer node.

The following code example shows how to remove all footers from all sections but leave headers intact. You can remove only headers in a similar way:

{{< gist "aspose-words-gists" "2e1b2b28253780881d116e3a873ee668" "remove-footers.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Header%20and%20footer%20types.docx).

{{% /alert %}} 

## FAQ

1. **Q:** Does `Document.get_child_nodes(NodeType.PARAGRAPH, True)` include paragraphs that are inside headers or footers?  
   **A:** Yes. When `is_deep` is set to `True`, the method traverses the entire document tree, including `HeaderFooter` nodes. To obtain only body paragraphs you must filter out nodes whose `parent_node` is a `HeaderFooter` object.

2. **Q:** How can I retrieve all paragraphs from a specific header, for example the odd‑page header?  
   **A:** Access the header through the section's `headers_footers` collection and then iterate its `paragraphs` collection:  

   ```python
   from aspose.words import Document
   doc = Document("input.docx")
   header = doc.sections[0].headers_footers.header_primary
   for paragraph in header.paragraphs:
       print(paragraph.get_text())
   ```

3. **Q:** What is the recommended way to copy a header from the previous section into the current one?  
   **A:** Clone the header node from the previous section and assign it to the current section's `headers_footers` collection:  

   ```python
   from aspose.words import Document
   doc = Document("input.docx")
   prev_header = doc.sections[0].headers_footers.header_primary
   cloned_header = prev_header.clone(True)
   doc.sections[1].headers_footers.add(cloned_header)
   ```

4. **Q:** How do I set different headers for the first page, odd pages, and even pages?  
   **A:** Enable the corresponding flags on `PageSetup` and then create headers of the appropriate `HeaderFooterType`:  

   ```python
   from aspose.words import Document, DocumentBuilder, HeaderFooterType
   doc = Document()
   section = doc.sections[0]
   section.page_setup.different_first_page_header_footer = True
   section.page_setup.odd_and_even_pages_header_footer = True

   builder = DocumentBuilder(doc)
   # First page header
   builder.move_to_header_footer(HeaderFooterType.HEADER_FIRST)
   builder.writeln("First page header")
   # Odd page header
   builder.move_to_header_footer(HeaderFooterType.HEADER_PRIMARY)
   builder.writeln("Odd page header")
   # Even page header
   builder.move_to_header_footer(HeaderFooterType.HEADER_EVEN)
   builder.writeln("Even page header")
   ```

5. **Q:** After inserting a PAGE field for page numbers in a footer, the numbers do not appear when I open the document.  
   **A:** The field must be evaluated. Call `Document.update_fields()` before saving, or open the document in a viewer that updates fields automatically:  

   ```python
   from aspose.words import Document, DocumentBuilder, HeaderFooterType
   doc = Document()
   builder = DocumentBuilder(doc)
   builder.move_to_header_footer(HeaderFooterType.FOOTER_PRIMARY)
   builder.insert_field("PAGE", "")
   doc.update_fields()
   doc.save("output.docx")
   ```