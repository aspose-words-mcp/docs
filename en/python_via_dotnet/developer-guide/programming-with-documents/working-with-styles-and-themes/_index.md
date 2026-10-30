---
title: Working with Styles and Themes
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Styles and Themes
linktitle: Working with Styles and Themes
description: "Access and manage styles and themes in a document using Python."
type: docs
weight: 110
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-styles-and-themes/
aliases: [/python/working-with-styles-and-themes/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to access, modify, and query document styles and themes using Aspose.Words for Python via .NET, including examples for retrieving content by style, copying styles between documents, and getting/setting theme properties.

{{% /alert %}}

The [StyleCollection](https://reference.aspose.com/words/python-net/aspose.words/stylecollection/) class is used to manage built-in and apply user-defined settings to styles.

## Accessing Styles

You can get a collection of styles defined in the document using the [Document.styles](https://reference.aspose.com/words/python-net/aspose.words/documentbase/styles/) property. This collection holds both the built-in and user-defined styles in a document. A particular style could be obtained by its name/alias, style identifier, or index. The following code example demonstrates how to get access to the collection of styles defined in the document.

{{< gist "aspose-words-gists" "40c79033c4dec6fc8bd51ae6e841caaa" "access-styles.py" >}}

## How to Extract Content Based on Styles

At a simple level, retrieving the content based on styles from a Word document can be useful to identify, list and count paragraphs and runs of text formatted with a specific style. For example, you may need to identify particular kinds of content in the document, such as examples, titles, references, keywords, figure names, and case studies.

To take this a few steps further, this can also be used to leverage the structure of the document, defined by the styles it uses, to re-purpose the document for another output, such as HTML. This is in fact how the Aspose documentation is built, putting Aspose.Words to the test. A tool built using Aspose.Words takes the source Word documents and splits them into topics at certain heading levels. An XML file is produced using Aspose.Words which is used to build the navigation tree you can see on the left. And then Aspose.Words converts each topic into HTML.

The solution for retrieving text formatted with specific styles in a Word document is typically economical and straightforward using Aspose.Words.

### The Solution

To illustrate how easily Aspose.Words handles retrieving content based on styles, let’s look at an example. In this example, we’re going to retrieve text formatted with a specific paragraph style and a character style from a sample Word document. At a high level, this will involve:# Opening a Word document using the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) class.# Getting collections of all paragraphs and all runs in the document.# Selecting only the required paragraphs and runs. Specifically, we’ll retrieve text formatted with the ‘Heading 1’ paragraph style and the ‘Intense Emphasis’ character style from this sample Word document.

![working-with-styles-and-themes-aspose-words-python](working-with-styles-and-themes-1.png)

In this sample document, the text formatted with the ‘Heading 1’ paragraph style is ‘Insert Tab’, ‘Quick Styles’ and ‘Theme’, and the text formatted with the ‘Intense emphasis’ character style is the several instances of blue, italicized, bold text such as ‘galleries’ and ‘overall look’.

### The Code

The implementation of a style-based query is quite simple in the Aspose.Words document object model, as it simply uses tools that are already in place. Two class methods are implemented for this solution: **paragraphs_by_style_name** – This method retrieves an array of those paragraphs in the document that have a specific style name. **runs_by_style_name** – This method retrieves an array of those runs in the document that have a specific style name. Both these methods are very similar, the only differences being the node types and the representation of the style information within the paragraph and run nodes. Here is an implementation of ParagraphsByStyleName : Below example find all paragraphs formatted with the specified style.

{{< gist "aspose-words-gists" "399801c9a5e656ed05aa2d7ac5ebc41e" "paragraphs-by-style-name.py" >}}

{{% alert color="primary" %}}

This implementation also uses the [Document.get_child_nodes](https://reference.aspose.com/words/python-net/aspose.words/compositenode/get_child_nodes/) method of the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) class, which returns a collection of all nodes with the specified type, which in this case in all paragraphs.

Note that the second parameter of the [Document.get_child_nodes](https://reference.aspose.com/words/python-net/aspose.words/compositenode/get_child_nodes/) method is set to `True`. This forces the [Document.get_child_nodes](https://reference.aspose.com/words/python-net/aspose.words/compositenode/get_child_nodes/) method to select from all child nodes recursively, rather than selecting the immediate children only.

{{% /alert %}}

It’s also worth pointing out that the paragraphs collection does not create an immediate overhead because paragraphs are loaded into this collection only when you access items in them. Then, all you need to do is to go through the collection, using the standard foreach operator and add paragraphs that have the specified style to the paragraphs_with_style array. The `Paragraph` style name can be found in the [Style.name](https://reference.aspose.com/words/python-net/aspose.words/style/name/) property of the [Paragraph.paragraph_format](https://reference.aspose.com/words/python-net/aspose.words/paragraph/paragraph_format/) object. The implementation of **runs_by_style_name** is almost the same, although we’re obviously using [NodeType.RUN](https://reference.aspose.com/words/python-net/aspose.words/nodetype/#run) to retrieve run nodes. The [Font.style](https://reference.aspose.com/words/python-net/aspose.words/font/style/) property of a [Run](https://reference.aspose.com/words/python-net/aspose.words/run/) object is used to access style information in the [Run](https://reference.aspose.com/words/python-net/aspose.words/run/) nodes. Below example find all runs formatted with the specified style.

{{< gist "aspose-words-gists" "40c79033c4dec6fc8bd51ae6e841caaa" "runs-by-style-name.py" >}}

When both queries are implemented, all you need to do is to pass a document object and specify the style names of the content you want to retrieve: Below example run queries and display results. You can download the template file of this example from [here](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Styles.docx).

{{< gist "aspose-words-gists" "40c79033c4dec6fc8bd51ae6e841caaa" "extract-content-based-on-styles.py" >}}

### End Result

When everything is done, running the sample will display the following output:

![styles-and-themes-aspose-words-python](working-with-styles-and-themes-2.png)

As you can see, this is a very simple example, showing the number and text of the collected paragraphs and runs in the sample Word document.

## Copy All Styles from Template

There are cases when you want to copy all styles from one document into another. You can use [Document.copy_styles_from_template](https://reference.aspose.com/words/python-net/aspose.words/document/copy_styles_from_template/) method to copy styles from the specified template to a document. When styles are copied from a template to a document, like-named styles in the document are redefined to match the style descriptions in the template. Unique styles from the template are copied to the document. Unique styles in the document remain intact. Below code example shows how to copy styles from one document into another.

{{< gist "aspose-words-gists" "40c79033c4dec6fc8bd51ae6e841caaa" "copy-styles.py" >}}

## How to Manipulate Theme Properties

We have added basic API in Aspose.Words to access document theme properties. For now, this API includes following public objects:

- Theme
- ThemeFonts
- ThemeColors

Here is how you can get theme properties:

{{< gist "aspose-words-gists" "40c79033c4dec6fc8bd51ae6e841caaa" "get-theme-properties.py" >}}

And here is how you can set theme properties:

{{< gist "aspose-words-gists" "40c79033c4dec6fc8bd51ae6e841caaa" "set-theme-properties.py" >}}

## Related APIs

- [StyleCollection](https://reference.aspose.com/words/python-net/aspose.words/stylecollection/) – Manages built-in and user-defined styles in a document.
- [Document.styles](https://reference.aspose.com/words/python-net/aspose.words/documentbase/styles/) – Gets the collection of styles defined in the document.
- [Document.copy_styles_from_template](https://reference.aspose.com/words/python-net/aspose.words/document/copy_styles_from_template/) – Copies all styles from a template document to the current document.
- [Theme](https://reference.aspose.com/words/python-net/aspose.words.themes/theme/) – Represents the theme settings of a document.
- [ThemeFonts](https://reference.aspose.com/words/python-net/aspose.words.themes/themefonts/) – Represents the fonts used in the document theme.
- [ThemeColors](https://reference.aspose.com/words/python-net/aspose.words.themes/themecolors/) – Represents the color scheme used in the document theme.
- [Paragraph.paragraph_format.style](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/style/) – Gets or sets the paragraph style applied to the paragraph.
- [Run.font.style_name](https://reference.aspose.com/words/python-net/aspose.words/font/style_name/) – Gets or sets the name of the character style applied to the run.