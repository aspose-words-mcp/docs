---
title: Working with Paragraphs in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Paragraphs
linktitle: Working with Paragraphs
description: "Insert paragraph and specify its formatting in a document using Python."
type: docs
weight: 210
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-paragraphs/
aliases: [/python/working-with-paragraphs/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page shows how to work with paragraphs in Aspose.Words for Python via .NET, including inserting paragraphs, formatting them, applying styles and style separators, and adding borders and shading, with code examples for each task.

{{% /alert %}}

A paragraph is a set of characters combined into a logical block and ending with a special character – a *paragraph break*. In Aspose.Words, a paragraph is represented by the [Paragraph](https://reference.aspose.com/words/python-net/aspose.words/paragraph/) class.

## Insert a Paragraph

To insert a new paragraph into the document, in fact, you need to insert a paragraph break character into it. [DocumentBuilder.writeln](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/writeln/) inserts not only a string of text into the document, but also adds a paragraph break.

The current font formatting is also specified by the [font](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/font/) property, and the current paragraph formatting is determined by the [paragraph_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/paragraph_format/) property. In the next section, we will go into more detail about paragraph formatting.

The following code example shows how to insert a paragraph into a document:

{{< gist "aspose-words-gists" "e934a01a96022d1546d17c47a5ab3904" "insert-paragraph.py" >}}

## Format Paragraph

Current paragraph formatting is represented by the [ParagraphFormat](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/) object that is returned by the [paragraph_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/paragraph_format/) property. This object encapsulates various paragraph formatting properties available in Microsoft Word. You can easily reset a paragraph's formatting to its default – Normal style, left-aligned, no indentation, no spacing, no borders, no shading – by calling [clear_formatting](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/clear_formatting/).

The following code example shows how to set paragraph formatting:

{{< gist "aspose-words-gists" "3782e77b237fd3303b01a130ae46f958" "paragraph-formatting.py" >}}

## Apply Paragraph Style

Some formatting objects, such as **Font** or **ParagraphFormat**, support styles. One built-in or user-defined style is represented by a [Style](https://reference.aspose.com/words/python-net/aspose.words/style/) object, which contains the appropriate style properties like name, base style, font, style paragraph formatting, and so on.

In addition, the **Style** object exposes the [StyleIdentifier](https://reference.aspose.com/words/python-net/aspose.words/styleidentifier/) property, which returns the locale-independent style identifier represented by the [Style.style_identifier](https://reference.aspose.com/words/python-net/aspose.words/style/style_identifier/) enumeration value. The fact is that the names of the built-in styles in Microsoft Word are localized for different languages. Using the style identifier, you can find the correct style regardless of the document language. The enumeration values correspond to the built-in Microsoft Word styles such as *Normal*, *Heading 1*, *Heading 2*  and so on. All user-defined styles are set to the **StyleIdentifier.USER** enumeration value.

The following code example shows how to apply a paragraph style:

{{< gist "aspose-words-gists" "3782e77b237fd3303b01a130ae46f958" "apply-paragraph-style.py" >}}

### Insert Style Separator to Put Different Paragraph Styles

A style separator can be added to the end of a paragraph using the keyboard shortcut Ctrl+Alt+Enter in Microsoft Word. This feature allows you to use two different paragraph styles in the same logical printed paragraph. If you want some text from the beginning of a particular heading to appear in the table of contents, but do not want the entire heading to show in the table of contents, you can use this function.

The following code example shows how to insert a style separator to accommodate different paragraph styles:

{{< gist "aspose-words-gists" "3782e77b237fd3303b01a130ae46f958" "insert-style-separator.py" >}}

### Identify Paragraph Style Separator

Aspose.Words exposes the [break_is_style_separator](https://reference.aspose.com/words/python-net/aspose.words/paragraph/break_is_style_separator/) public property on the `Paragraph` class to identify a paragraph with a style separator, as shown in the example below:

{{< gist "aspose-words-gists" "3782e77b237fd3303b01a130ae46f958" "get-paragraph-style-separator.py" >}}

## Apply Borders and Shading to a Paragraph

Borders in Aspose.Words are represented by the [BorderCollection](https://reference.aspose.com/words/python-net/aspose.words/bordercollection/) class – this is a collection of [Border](https://reference.aspose.com/words/python-net/aspose.words/border/) objects that are accessed by index or by border type. The border type is in turn represented by the [BorderType](https://reference.aspose.com/words/python-net/aspose.words/bordertype/) enumeration. Some enumeration values apply to multiple or only one document element. For example, **BorderType.BOTTOM** applies to a paragraph or table cell, while **BorderType.DIAGONAL_DOWN** specifies a diagonal border in a table cell only.

Both the border collection and each separate border have similar attributes such as color, line style, line width, distance from text, and optional shadow. They are represented by properties of the same name. You can get different border types by combining property values. In addition, the **BorderCollection** and **Border** objects allow you to reset these values to their default values by calling the [clear_formatting](https://reference.aspose.com/words/python-net/aspose.words/border/clear_formatting/) method.

{{% alert color="primary" %}}

Note that when the border properties are reset to their default values, the border becomes invisible.

{{% /alert %}}

Aspose.Words also has the [Shading](https://reference.aspose.com/words/python-net/aspose.words/shading/) class that contains shading attributes for document elements. You can set the desired shading texture and colors that are applied to the background and foreground of an element using the [TextureIndex](https://reference.aspose.com/words/python-net/aspose.words/textureindex/) enumeration value. **TextureIndex** also allows you to apply different patterns to the **Shading** object. For example, to set the background color for a document element, use the **TextureIndex.TEXTURE_SOLID** value and set the foreground shading color as appropriate.

The following code example shows how to apply borders and shading to a paragraph:

{{< gist "aspose-words-gists" "3782e77b237fd3303b01a130ae46f958" "apply-borders-and-shading-to-paragraph.py" >}}

## Count Paragraph Lines

If you want to count the number of lines in a paragraph for any Word document, the following code sample can be used:

{{< gist "aspose-words-gists" "3782e77b237fd3303b01a130ae46f958" "get-paragraph-lines.py" >}}