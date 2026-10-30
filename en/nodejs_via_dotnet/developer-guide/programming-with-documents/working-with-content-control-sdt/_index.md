---
title: Working with Content Control SDT
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Content Control SDT
linktitle: Working with Content Control SDT
description: "using Node.js you can embed customer-defined semantics as well as its behaviour and appearance into a document."
type: docs
weight: 390
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-content-control-sdt/
timestamp: 2025-07-09-10-05-05
---

In Microsoft Word, you can create a form by starting with a template and adding content controls, including checkboxes, text boxes, date pickers, and drop-down lists. In Aspose.Words, a Structured Document Tag or content control from any document loaded into Aspose.Words is imported as a [StructuredDocumentTag](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/) node. Structured document tags (SDT or content control) allow embedding customer-defined semantics as well as its behaviour and appearance into a document. [StructuredDocumentTag](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/) can occur in a document in the following places:

- Block-level - Among paragraphs and tables, as a child of a [Body](https://reference.aspose.com/words/nodejs-net/aspose.words/body/), [HeaderFooter](https://reference.aspose.com/words/nodejs-net/aspose.words/headerfooter/), [Comment](https://reference.aspose.com/words/nodejs-net/aspose.words/comment/), [Footnote](https://reference.aspose.com/words/nodejs-net/aspose.words.notes/footnote/) or a [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) node
- Row-level - Among rows in a table, as a child of a **Table** node
- Cell-level - Among cells in a table row, as a child of a [Row](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/row/) node
- Inline-level - Among inline content inside, as a child of a [Paragraph](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraph/)
- Nested inside another [StructuredDocumentTag](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/)

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

The following code example demonstrates how to create content control of type checkbox.

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "sdt-check-box.js" >}}

The following code example demonstrates how to create content control of type rich text box.

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "sdt-rich-text-box.js" >}}

The following code example demonstrates how to create content control of the type combo box.

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "sdt-combo-box.js" >}}

## How to update Content Controls

This section explains how to update the values of SDT or content control programmatically.

The following code example shows how to set the current state of the checkbox:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "current-state-of-check-box.js" >}}

The following code example shows how to modify content controls of type plain text box, drop-down list and picture:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "modify-sdt.js" >}}

{{% alert color="primary" %}}

You can download the sample file of these examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/blob/main/Data/Structured%20document%20tags.docx).

{{% /alert %}}

## Binding Content Control to Custom XML Parts

You can bind content controls with XML data (*custom XML part*) in Word documents.

The following code example shows how to bind content control to custom XML parts:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "bind-sdt-to-custom-xml-part.js" >}}

## XMLMapping of Structured Document Tag Range

You can get the mapping of this structured document tag range to XML data in a custom XML part of the current document using the [StructuredDocumentTagRangeStart.xmlMapping](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttagrangestart/xmlmapping/) property. However, the [setMapping](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/xmlmapping/setMapping/) method can be used to map a structured document tag range to XML data.

The following code example shows how to set XML mapping:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "sdt-range-start-xml-mapping.js" >}}

## Clear Contents of a Content Control

You can clear the contents of a content control with displaying a placeholder. [StructuredDocumentTag.clear](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/clear/) method clears contents of this structured document tag and displays a placeholder if it is defined. However, It is not possible to clear the contents of a content control if it has revisions. If a content control has no placeholder, five spaces are inserted like in MS Word (except repeating sections, repeating section items, groups, check-boxes, citations). If a content control is mapped to custom XML, the referenced XML node is cleared.

The following code example shows how to clear the content of content control:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "clear-sdt.js" >}}

## Change Content Control Background and Border Colors

The [StructuredDocumentTag.color](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/color/) property allows you to get or set the color of content control. The color affects content control in two situations:

1. MS Word highlights the background of the content control when the mouse moves over the content control. This helps to identify the content control. The color of highlighting is a bit "softer" than the *color*. For example, MS Word highlights the background with the pink color, when *color* is red.
2. When you interact (editing, picking etc) with the content control, the border of content control is colored with the *color*.

The following code example shows how to change the color of content control:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "sdt-color.js" >}}

## How to Set Style to Format Text Typed into the Content Control

If you want to set the style of content control, you can use [StructuredDocumentTag.style](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/style/) or [StructuredDocumentTag.styleName](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/structureddocumenttag/stylename/) properties. When you type the text into content control in the output document, the typed text will have the style "Quote".

{{% alert color="primary" %}}

Note that only Linked and Character styles can be applied to content control. An exception ("Cannot apply this style to the SDT") is thrown when a style that exists but is not Linked or Character style is being applied.

{{% /alert %}}

The following code example shows how to set the style of content control:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "sdt-style.js" >}}

## Working with Repeating Section Content Control

The repeating section content control allows repeating the content contained within it. Using Aspose.Words, the structured document tag nodes of the repeating section and repeating section item types can be created and for this purpose, [SdtType](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/sdttype/) enumeration type provides [RepeatingSectionItem](https://reference.aspose.com/words/nodejs-net/aspose.words.markup/sdttype/) property.

The following code example shows how to bind a repeating section content control to a table:

{{< gist "aspose-words-gists" "625644238d5cac4a2215ccfe46030666" "repeating-section-mapped-to-custom-xml-part.js" >}}