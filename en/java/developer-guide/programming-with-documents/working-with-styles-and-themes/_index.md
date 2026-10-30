---
title: Working with Styles and Themes in Java
second_title: Aspose.Words for Java
articleTitle: Working with Styles and Themes
linktitle: Working with Styles and Themes
description: "Advanced Microsoft Word formatting features, working with styles and themes using Java."
type: docs
weight: 110
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-styles-and-themes/
aliases:
- /java/how-to-extract-content-based-on-styles/
- /java/working-with-styles/
- /java/working-with-themes/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with styles and themes.

{{% /alert %}}

The [StyleCollection](https://reference.aspose.com/words/java/com.aspose.words/stylecollection/) class is used to manage built-in and apply user-defined settings to styles.

## Accessing Styles

You can get a collection of styles defined in the document using the [Document.getStyles()](https://reference.aspose.com/words/java/com.aspose.words/document/#getStyles) property. This collection holds both the built-in and user-defined styles in a document. A particular style could be obtained by its name/alias, style identifier, or index. The following code example demonstrates how to get access to the collection of styles defined in the document.

{{< gist "aspose-words-gists" "f1e523d4c5e156a1e42b86f56c70bf53" "access-styles.java" >}}

## How to Extract Content Based on Styles

At a simple level, retrieving the content based on styles from a Word document can be useful to identify, list and count paragraphs and runs of text formatted with a specific style. For example, you may need to identify particular kinds of content in the document, such as examples, titles, references, keywords, figure names, and case studies.

To take this a few steps further, this can also be used to leverage the structure of the document, defined by the styles it uses, to re-purpose the document for another output, such as HTML. This is in fact how the Aspose documentation is built, putting Aspose.Words to the test. A tool built using Aspose.Words takes the source Word documents and splits them into topics at certain heading levels. An XML file is produced using Aspose.Words which is used to build the navigation tree you can see on the left. And then Aspose.Words converts each topic into HTML.

The solution for retrieving text formatted with specific styles in a Word document is typically economical and straightforward using Aspose.Words.

### The Solution

To illustrate how easily Aspose.Words handles retrieving content based on styles, let's look at an example. In this example, we're going to retrieve text formatted with a specific paragraph style and a character style from a sample Word document. At a high level, this will involve:# Opening a Word document using the [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) class.# Getting collections of all paragraphs and all runs in the document.# Selecting only the required paragraphs and runs. Specifically, we'll retrieve text formatted with the ‘Heading 1' paragraph style and the ‘Intense Emphasis' character style from this sample Word document.

![working-with-styles-and-themes-aspose-words-net](working-with-styles-and-themes-1.png)

In this sample document, the text formatted with the ‘Heading 1' paragraph style is ‘Insert Tab', ‘Quick Styles' and ‘Theme', and the text formatted with the ‘Intense emphasis' character style is the several instances of blue, italicized, bold text such as ‘galleries' and ‘overall look'.

### The Code

The implementation of a style-based query is quite simple in the Aspose.Words document object model, as it simply uses tools that are already in place. Two class methods are implemented for this solution: **ParagraphsByStyleName** – This method retrieves an array of those paragraphs in the document that have a specific style name. **RunsByStyleName** – This method retrieves an array of those runs in the document that have a specific style name. Both these methods are very similar, the only differences being the node types and the representation of the style information within the paragraph and run nodes. Here is an implementation of ParagraphsByStyleName : Below example find all paragraphs formatted with the specified style.

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "paragraphs-by-style-name.java" >}}

{{% alert color="primary" %}}

This implementation also uses the `Document.getChildNodes` method of the `Document` class, which returns a collection of all nodes with the specified type, which in this case in all paragraphs.

Note that the second parameter of the **Document.getChildNodes** method is set to true. This forces the **Document.getChildNodes** method to select from all child nodes recursively, rather than selecting the immediate children only.

{{% /alert %}}

It's also worth pointing out that the paragraphs collection does not create an immediate overhead because paragraphs are loaded into this collection only when you access items in them. Then, all you need to do is to go through the collection, using the standard foreach operator and add paragraphs that have the specified style to the paragraphsWithStyle array. The `Paragraph` style name can be found in the [Style.getName()](https://reference.aspose.com/words/java/com.aspose.words/style/#getName) property of the object returned by [Paragraph.getParagraphFormat()](https://reference.aspose.com/words/java/com.aspose.words/paragraph/#getParagraphFormat). The implementation of RunsByStyleName is almost the same, although we're obviously using [NodeType.RUN](https://reference.aspose.com/words/java/com.aspose.words/nodetype/#RUN) to retrieve run nodes. The [Font.getStyle()](https://reference.aspose.com/words/java/com.aspose.words/font/#getStyle) property of a [Run](https://reference.aspose.com/words/java/com.aspose.words/run/) object is used to access style information in the **Run** nodes. Below example find all runs formatted with the specified style.

{{< gist "aspose-words-gists" "f1e523d4c5e156a1e42b86f56c70bf53" "runs-by-style-name.java" >}}

When both queries are implemented, all you need to do is to pass a document object and specify the style names of the content you want to retrieve: Below example run queries and display results. You can download the template file of this example from [here](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Styles.docx).

{{< gist "aspose-words-gists" "f1e523d4c5e156a1e42b86f56c70bf53" "extract-content-based-on-styles.java" >}}

### End Result

When everything is done, running the sample will display the following output:

![styles-and-themes-aspose-words-net](working-with-styles-and-themes-2.png)

As you can see, this is a very simple example, showing the number and text of the collected paragraphs and runs in the sample Word document.

## Copy All Styles from Template

There are cases when you want to copy all styles from one document into another. You can use `Document.copyStylesFromTemplate` method to copy styles from the specified template to a document. When styles are copied from a template to a document, like-named styles in the document are redefined to match the style descriptions in the template. Unique styles from the template are copied to the document. Unique styles in the document remain intact. Below code example shows how to copy styles from one document into another.

{{< gist "aspose-words-gists" "f1e523d4c5e156a1e42b86f56c70bf53" "copy-styles.java" >}}

## How to Manipulate Theme Properties

We have added basic API in Aspose.Words to access document theme properties. For now, this API includes following public objects:

- Theme
- ThemeFonts
- ThemeColors

Here is how you can get theme properties:

{{< gist "aspose-words-gists" "f1e523d4c5e156a1e42b86f56c70bf53" "get-theme-properties.java" >}}

And here is how you can set theme properties:

{{< gist "aspose-words-gists" "f1e523d4c5e156a1e42b86f56c70bf53" "set-theme-properties.java" >}}

## Related APIs

- [StyleCollection](https://reference.aspose.com/words/java/com.aspose.words/stylecollection/) - Manages built-in and user-defined styles in a document.
- [Document.getStyles()](https://reference.aspose.com/words/java/com.aspose.words/document/#getStyles) - Gets the collection of styles defined in the document.
- [Document.copyStylesFromTemplate()](https://reference.aspose.com/words/java/com.aspose.words/document/#copyStylesFromTemplate-com.aspose.words.Document) - Copies all styles from a template document to the current document.
- [Theme](https://reference.aspose.com/words/java/com.aspose.words/theme/) - Represents the theme settings of a document.
- [ThemeFonts](https://reference.aspose.com/words/java/com.aspose.words/themefonts/) - Represents the fonts used in the document theme.
- [ThemeColors](https://reference.aspose.com/words/java/com.aspose.words/themecolors/) - Represents the color scheme used in the document theme.
- [ParagraphFormat.getStyle()](https://reference.aspose.com/words/java/com.aspose.words/paragraphformat/#getStyle) - Gets or sets the paragraph style applied to the paragraph.
- [Font.getStyleName()](https://reference.aspose.com/words/java/com.aspose.words/font/#getStyleName) - Gets or sets the name of the character style applied to the run.

------

## FAQ

1. **Q:** How can I retrieve all paragraphs that use a specific style?  
   **A:** Use `Document.getChildNodes(NodeType.PARAGRAPH, true)` to obtain all paragraphs, then filter them by checking `paragraph.getParagraphFormat().getStyle().getName()` against the desired style name. The helper method `ParagraphsByStyleName` in the article demonstrates this approach.

2. **Q:** How do I get all runs (character formatting) that have a particular style?  
   **A:** Call `Document.getChildNodes(NodeType.RUN, true)` to collect all runs, and filter with `run.getFont().getStyle().getName()`. The `RunsByStyleName` method in the article provides a ready‑to‑use example.

3. **Q:** How can I insert a style separator so that a single line contains two different paragraph styles?  
   **A:** Insert a style separator at the desired position. In Java, move a `DocumentBuilder` to that position, call `builder.insertStyleSeparator()`, and then write the second run with the alternate style after the separator.

4. **Q:** How do I copy all styles from a template document into another document?  
   **A:** Load the template with `Document template = new Document("Template.docx");` and the target document with `Document target = new Document("Target.docx");`. Then call `target.copyStylesFromTemplate(template);`. This copies matching styles and adds any unique styles from the template.

5. **Q:** How can I read or modify the theme colors, fonts, or other theme properties of a document?  
   **A:** Access the theme via `Theme theme = document.getTheme();`. You can read colors with `theme.getColors().getAccent1()` and fonts with `theme.getMajorFonts().getLatin()`. To change a property, call its setter, e.g., `theme.getColors().setAccent1(Color.BLUE);` and then save the document. The code snippets in the “How to Manipulate Theme Properties” section illustrate both reading and setting these values.