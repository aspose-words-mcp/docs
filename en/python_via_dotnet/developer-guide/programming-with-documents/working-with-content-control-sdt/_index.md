---
title: Working with Content Control SDT
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Content Control SDT
linktitle: Working with Content Control SDT
description: "Using python you can embed customer-defined semantics as well as its behaviour and appearance into a document."
type: docs
weight: 390
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-content-control-sdt/
aliases: [/python/working-with-content-control-sdt/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to create, modify, bind, clear, style, and work with repeating section content controls (Structured Document Tags) using Aspose.Words for Python via .NET, providing code examples for each operation.

{{% /alert %}}

In Microsoft Word, you can create a form by starting with a template and adding content controls, including checkboxes, text boxes, date pickers, and drop-down lists. In Aspose.Words, a Structured Document Tag or content control from any document loaded into Aspose.Words is imported as a StructuredDocumentTag node. Structured document tags (SDT or content control) allow embedding customer-defined semantics as well as its behaviour and appearance into a document.

StructuredDocumentTag can occur in a document in the following places:

- Block-level – Among paragraphs and tables, as a child of a Body, HeaderFooter, Comment, Footnote or a Shape node
- Row-level – Among rows in a table, as a child of a Table node
- Cell-level – Among cells in a table row, as a child of a Row node
- Inline-level – Among inline content inside, as a child of a Paragraph
- Nested inside another StructuredDocumentTag

## Inserting Content Controls into a Document

In this version of Aspose.Words, the following types of SDT or content control can be created:

- Checkbox
- DropDownList
- ComboBox
- Date
- BuildingBlockGallery
- Group
- `Picture`
- RichText
- PlainText

The following code example shows how to create content control of type checkbox:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "sdt-check-box.py" >}}

The following code example shows how to create content control of type rich text box:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "sdt-rich-text-box.py" >}}

The following code example shows how to create content control of the type combo box:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "sdt-combo-box.py" >}}

## How to Update Content Controls

This section explains how to update the values of SDT or content control programmatically.

The following code example shows how to set the current state of the checkbox:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "current-state-of-check-box.py" >}}

The following code example shows how to modify content controls of type plain text box, drop-down list and picture:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "modify-sdt.py" >}}

## Binding Content Control to Custom XML Parts

You can bind content controls with XML data (*custom XML part*) in Word documents.

The following code example shows how to bind content control to custom XML parts:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "bind-sdt-to-custom-xml-part.py" >}}

## XMLMapping of Structured Document Tag Range

You can get the mapping of this structured document tag range to XML data in a custom XML part of the current document using the **StructuredDocumentTagRangeStart.xml_mapping property**. However, the [set_mapping](https://reference.aspose.com/words/python-net/aspose.words.markup/xmlmapping/set_mapping/) method can be used to map a structured document tag range to XML data.

The following code example shows how to set XML mapping:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "sdt-range-start-xml-mapping.py" >}}

## Clear Contents of a Content Control

You can clear the contents of a content control with displaying a placeholder. The **StructuredDocumentTag.clear** method clears contents of this structured document tag and displays a placeholder if it is defined. However, It is not possible to clear the contents of a content control if it has revisions. If a content control has no placeholder, five spaces are inserted like in Microsoft Word (except repeating sections, repeating section items, groups, check-boxes, citations). If a content control is mapped to custom XML, the referenced XML node is cleared.

The following code example shows how to clear the content of content control:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "clear-sdt.py" >}}

## Change Content Control Background and Border Colors

The [StructuredDocumentTag.color](https://reference.aspose.com/words/python-net/aspose.words.markup/structureddocumenttag/color/) property allows you to get or set the color of content control. The color affects content control in two situations:

1. MS Word highlights the background of the content control when the mouse moves over the content control. This helps to identify the content control. The color of highlighting is a bit "softer" than the *color*. For example, MS Word highlights the background with the pink color, when *color* is red.
2. When you interact (editing, picking etc) with the content control, the border of content control is colored with the *color*.

The following code example shows how to change the color of content control:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "sdt-color.py" >}}

## How to Set Style to Format Text Typed into the Content Control

If you want to set the style of content control, you can use [StructuredDocumentTag.style](https://reference.aspose.com/words/python-net/aspose.words.markup/structureddocumenttag/style/) or [StructuredDocumentTag.style_name](https://reference.aspose.com/words/python-net/aspose.words.markup/structureddocumenttag/style_name/) properties. When you type the text into content control in the output document, the typed text will have the style "Quote".

{{% alert color="primary" %}}

Note that only Linked and Character styles can be applied to content control. An InvalidOperationException ("Cannot apply this style to the SDT") is thrown when a style that exists but is not Linked or Character style is being applied.

{{% /alert %}}

The following code example shows how to set the style of content control:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "sdt-style.py" >}}

## Working with Repeating Section Content Control

The repeating section content control allows repeating the content contained within it. Using Aspose.Words, the structured document tag nodes of the repeating section and repeating section item types can be created and for this purpose, [SdtType](https://reference.aspose.com/words/python-net/aspose.words.markup/sdttype/) provides **REPEATING_SECTION_ITEM** property.

The following code example shows how to bind a repeating section content control to a table:

{{< gist "aspose-words-gists" "2da81a821a2e21b8e35dee1396ed59ba" "repeating-section-mapped-to-custom-xml-part.py" >}} 

## FAQ

1. **Q:** How can I apply a style to the text that a user types into a content control?  
   **A:** Use the `StructuredDocumentTag.style` or `StructuredDocumentTag.style_name` property. Only linked or character styles are supported; attempting to apply a paragraph style will raise an exception.

2. **Q:** Does `doc.get_child_nodes(aw.NodeType.PARAGRAPH, True)` return paragraphs that are inside headers and footers?  
   **A:** Yes. When the `include_child_nodes` argument is set to `True`, the method traverses the entire document tree, including `HeaderFooter` sections, and returns all descendant paragraph nodes.

3. **Q:** How do I bind a content control to a custom XML part?  
   **A:** Retrieve the `StructuredDocumentTag.xml_mapping` property of the control and call its `set_mapping(custom_xml_part, x_path, prefix_mapping)` method (pass `""` as `prefix_mapping` if the XPath uses no namespace prefixes) to associate the control with the desired XML node.

4. **Q:** Why can't I clear a content control that contains revisions?  
   **A:** The `StructuredDocumentTag.clear()` method does not work on controls that have pending revisions. Accept or reject the revisions first, then call `clear()` to remove the content.