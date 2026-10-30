---
title: Working with Content Control SDT in Java
second_title: Aspose.Words for Java
articleTitle: Working with Content Control SDT
linktitle: Working with Content Control SDT
description: "Advanced document content management, how to create and manipulate content controls (Structured Document Tags) using Java."
type: docs
weight: 390
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-content-control-sdt/
timestamp: 2024-01-31-14-23-37
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with content controls (SDTs) through the Aspose.Words API.

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

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "sdt-check-box.java" >}}

The following code example shows how to create content control of type rich text box:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "sdt-rich-text-box.java" >}}

The following code example shows how to create content control of the type combo box:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "sdt-combo-box.java" >}}

## How to Update Content Controls

This section explains how to update the values of SDT or content control programmatically.

The following code example shows how to set the current state of the checkbox:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "current-state-of-check-box.java" >}}

The following code example shows how to modify content controls of type plain text box, drop-down list and picture:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "modify-sdt.java" >}}

## Binding Content Control to Custom XML Parts

You can bind content controls with XML data (*custom XML part*) in Word documents.

The following code example shows how to bind content control to custom XML parts:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "bind-sdt-to-custom-xml-part.java" >}}

## XMLMapping of Structured Document Tag Range

You can get the mapping of this structured document tag range to XML data in a custom XML part of the current document using the **StructuredDocumentTagRangeStart.getXmlMapping()** property. However, the [setMapping()](https://reference.aspose.com/words/java/com.aspose.words/xmlmapping/#setMapping-com.aspose.words.CustomXmlPart-java.lang.String-java.lang.String) method can be used to map a structured document tag range to XML data.

The following code example shows how to set XML mapping:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "sdt-range-start-xml-mapping.java" >}}

## Clear Contents of a Content Control

You can clear the contents of a content control with displaying a placeholder. The **StructuredDocumentTag.clear** method clears contents of this structured document tag and displays a placeholder if it is defined. However, It is not possible to clear the contents of a content control if it has revisions. If a content control has no placeholder, five spaces are inserted like in Microsoft Word (except repeating sections, repeating section items, groups, check-boxes, citations). If a content control is mapped to custom XML, the referenced XML node is cleared.

The following code example shows how to clear the content of content control:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "clear-sdt.java" >}}

## Change Content Control Background and Border Colors

In Java, use the getColor() and setColor() methods of StructuredDocumentTag: "The StructuredDocumentTag.getColor() / setColor() methods allow you to get or set the color of a content control. The color affects the content control in two situations:"

1. MS Word highlights the background of the content control when the mouse moves over the content control. This helps to identify the content control. The color of highlighting is a bit "softer" than the *Color*. For example, MS Word highlights the background with the pink color, when *Color* is Red.
2. When you interact (editing, picking etc) with the content control, the border of content control is colored with the *Color*.

The following code example shows how to change the color of content control:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "sdt-color.java" >}}

## How to Set Style to Format Text Typed into the Content Control

If you want to set the style of a content control, use the `StructuredDocumentTag.setStyle(Style)` or `StructuredDocumentTag.setStyleName(String)` methods. When you type text into the content control in the output document, the typed text will have the style "Quote".

{{% alert color="primary" %}}

Note that only Linked and Character styles can be applied to content control. An IllegalStateException ("Cannot apply this style to the SDT") is thrown when a style that exists but is not Linked or Character style is being applied.

{{% /alert %}}

The following code example shows how to set the style of content control:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "sdt-style.java" >}}

## Working with Repeating Section Content Control

The repeating section content control allows repeating the content contained within it. Using Aspose.Words, the structured document tag nodes of the repeating section and repeating section item types can be created and for this purpose, [SdtType enumeration type](https://reference.aspose.com/words/java/com.aspose.words/sdttype/) provides **REPEATING_SECTION_ITEM** property.

The following code example shows how to bind a repeating section content control to a table:

{{< gist "aspose-words-gists" "e21394fa5fe859b6608b088a91bc7a7c" "repeating-section-mapped-to-custom-xml-part.java" >}}

------

## FAQ

1. **Q:** How can I create a checkbox content control in Java?  
   **A:** Instantiate a `StructuredDocumentTag` with `SdtType.CHECKBOX`, set its properties (e.g., title, placeholder), and insert it into the desired node (e.g., `Document.getFirstSection().getBody().appendChild(structuredDocumentTag);`).

2. **Q:** How do I set or read the checked state of a checkbox content control?  
   **A:** Use the `StructuredDocumentTag.setChecked(boolean)` method to set the state and `StructuredDocumentTag.getChecked()` to read the current state.

3. **Q:** How can I bind a content control to a custom XML part?  
   **A:** Create a `CustomXmlPart`, add it to the document (`document.getCustomXmlParts().add(customXmlPart);`), then call `structuredDocumentTag.getXmlMapping().setMapping(customXmlPart, "/Root/Element", "");` to map the control to the XML node.

4. **Q:** How can I change the background or border color of a content control?  
   **A:** Set the `StructuredDocumentTag.getColor()` / `StructuredDocumentTag.setColor(java.awt.Color)` properties. The color affects hover background and active border highlighting.

5. **Q:** How can I specify the display format for a date content control?  
   **A:** Use `structuredDocumentTag.setDateDisplayFormat("MM/dd/yyyy");` to define the format string that Word will use to display the date value. This does not affect the underlying date value stored in the XML.


6. **Q:** How can I clear the contents of a content control while preserving its placeholder? 
   **A:** Call `structuredDocumentTag.clear()`. If a placeholder is defined, it will be displayed; otherwise, five spaces are inserted (unless it's a repeating section, group, checkbox, or citation).

7. **Q:** Can I apply any style to a content control?  
   **A:** Only Linked or Character styles can be applied using `StructuredDocumentTag.setStyle(Style)` or `setStyleName(String)`. Attempting to apply non-linked/character styles throws an `IllegalStateException`.