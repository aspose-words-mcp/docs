---
title: Translate Markdown to DOM
second_title: Aspose.Words for Java
articleTitle: Translate Markdown to Document Object Model (DOM)
linktitle: Translate Markdown to Document Object Model (DOM)
type: docs
description: "Translate a Markdown document to Document Object Model and back using Java. So you can work with complex existing Markdown and programmatically create a Markdown document from scratch."
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/translate-markdown-to-document-object-model/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to translate Markdown into the Document Object Model and how Aspose.Words interprets Markdown structures.

{{% /alert %}}

To programmatically read, manipulate, and modify the content and formatting of a document, you need to translate it to the Aspose.Words Document Object Model (DOM).

In contrast to Word documents, Markdown does not conform to the DOM described in the [Aspose.Words Document Object Model (DOM)](/words/java/aspose-words-document-object-model/) article. However, Aspose.Words provides its own mechanism for translating Markdown documents to DOM and back, so that we can successfully work with their elements such as text formatting, tables, headers, and others.

This article explains how the various markdown features can be translated into Aspose.Words DOM and back to Markdown format.

## Complexity of Translation Markdown – DOM – Markdown

The main difficulty of this mechanism is not only to translate Markdown to DOM, but also to do the reverse transformation – to save the document back to Markdown format with minimal loss. There are elements, such as multilevel quotes, for which the reverse transformation is not trivial.

Our translation engine allows users not only to work with complex elements in an existing Markdown document, but also to create their own document in Markdown format with the original structure from scratch. To create various elements, you need to use styles with specific names according to certain rules described later in this article. Such styles can be created programmatically.

## Common Translation Principles

We use [Font](https://reference.aspose.com/words/java/com.aspose.words/font/) formatting for inline blocks. When there is no direct correspondence for a Markdown feature in Aspose.Words DOM, we use a character style with a name that starts from some special words.

For container blocks, we use style inheritance to denote nested Markdown features. In this case, even when there are no nested features, we also use paragraph styles with a name that starts from some special words.

Bulleted and ordered lists are container blocks in Markdown as well. Their nesting is represented in DOM the same way as for all other container blocks using style inheritance. However, additionally, lists in DOM have corresponded number formatting in either list style or paragraph formatting.

## Inline Blocks

We use [Font](https://reference.aspose.com/words/java/com.aspose.words/font/) formatting when translating **Bold**, *Italic* or ~~Strikethrough~~ inline markdown features.

| Markdown feature              | Aspose.Words       |
| ----------------------------- | ------------------ |
| **Bold**<br />`**bold text**` | `Font.setBold(true)` |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "bold-text.java" >}} |  |
| **Italic**<br />`*italic text*` | `Font.setItalic(true)` |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "italic-text.java" >}} |  |
| **Strikethrough**<br />`~Strikethrough text~` | `Font.setStrikeThrough(true)` |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "strikethrough.java" >}} |  |

We use a character style with a name that starts from the word `InlineCode`, followed by an optional dot `(.)` and a number of backticks ```(`)``` for the `InlineCode` feature. If a number of backticks is missed, then one backtick will be used by default.

| Markdown feature              | Aspose.Words       |
| ----------------------------- | ------------------ |
| **InlineCode**<br />`**inline code**` | `Font.setStyleName(“InlineCode[.][N]”)` |
| {{< gist "aspose-words-gists" "642767bbe8d8bec8eab080120b707990" "inline-code.java" >}} |  |
| **Autolink**<br />`<scheme://domain.com>`<br />`<email@domain.com>` | The [FieldHyperlink](https://reference.aspose.com/words/java/com.aspose.words/fieldhyperlink/) class. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "autolink.java" >}} |  |
| **Link**<br />`[link text](url)`<br />`[link text](<url> "title")`<br />`[link text](url 'title')`<br />`[link text](url (title))` | The [FieldHyperlink](https://reference.aspose.com/words/java/com.aspose.words/fieldhyperlink/) class. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "link.java" >}} |  |
| **Image**<br />`![](url)`<br />`![alt text](<url> “title”)`<br />`![alt text](url ‘title')`<br />`![alt text](url (title))` | The [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/) class. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "image.java" >}} |  |

## Container Blocks

A document is a sequence of container blocks such as headings, paragraphs, lists, quotes, and others. Container blocks can be divided into 2 classes: Leaf blocks and Complex Containers. Leaf blocks can only contain inline content. Complex containers, in turn, can contain other container blocks, including Leaf blocks.

### Leaf Blocks

The table below shows examples of using Markdown Leaf blocks in Aspose.Words:

| Markdown feature                                             | Aspose.Words                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **HorizontalRule**<br />`-----`                              | This is a simple paragraph with a corresponding HorizontalRule shape:<br />`documentBuilder.insertHorizontalRule();` |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "horizontal-rule.java" >}} | |
| **ATX Heading**<br />`# H1, ## H2, ### H3…`                  | `paragraph.getParagraphFormat().setStyleName("Heading N");` where (1 ≤ N ≤ 9). This is translated into a built‑in style and must match the exact pattern (no suffixes or prefixes). Otherwise it will be a regular paragraph with the specified style. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "heading.java" >}} | |
| **Setext Heading**<br />`===` (if Heading level 1),<br />`---` (if Heading level 2) | `paragraph.getParagraphFormat().setStyleName("SetextHeading" + suffix);` based on the "Heading N" style. If N ≥ 2, "Heading 2" is used, otherwise "Heading 1". Any suffix is allowed; the importer uses numbers "1" and "2" respectively. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "setext-heading.java" >}} |
| **Indented Code**                                            | `paragraph.getParagraphFormat().setStyleName("IndentedCode" + suffix);` |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "indented-code.java" >}} | |
| **Fenced Code**<br />{{< highlight java >}}``` java
if (condition) {
    // then
} else {
    // else
}
```{{< /highlight >}} | `paragraph.getParagraphFormat().setStyleName("FencedCode" + optionalDot + optionalInfoString);` The optional dot and info string are optional. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "fenced-code.java" >}} |

### Complex Containers

The table below shows examples of using Markdown Complex Containers in Aspose.Words:

| Markdown feature                                             | Aspose.Words                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Quote**<br />`> quote,`<br />`>> nested quote`             | `paragraph.getParagraphFormat().setStyleName(“Quote[some suffix]”);`<br />The suffix in style name is optional, but Aspose.Words importer uses the ordered numbers 1, 2, 3, …. in case of nested quotes.<br />The nesting is defined via the inherited styles. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "quote.java" >}} |
| **BulletedList**<br />`- Item 1`<br />`- Item 2`<br />	`   - Item 2a`<br />	`   - Item 2b` | Bulleted lists are represented using paragraph numbering:<br />`ListFormat.applyBulletDefault()`<br />There can be 3 types of bulleted lists. They are only diff in a numbering format of the very first level. These are: `‘-'`, `‘+'` or `‘*'` respectively. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "bulleted-list.java" >}} |                                                              |
| **OrderedList**<br />`1. Item 1`<br />`2. Item 2`<br />	`1) Item 2a`<br />	`2) Item 2b` | Ordered lists are represented using paragraph numbering:<br />`ListFormat.applyNumberDefault()`<br />There can be 2 number format markers: ‘.' and ‘)'. The default marker is ‘.'. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "ordered-list.java" >}} |                                                              |

### Tables

Aspose.Words also allows to translate tables into DOM, as shown below:

| Markdown feature                                             | Aspose.Words                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `Table`<br />`a|b`<br />`-|-`<br />`c|d`                     | [Table](https://reference.aspose.com/words/java/com.aspose.words/table/), [Row](https://reference.aspose.com/words/java/com.aspose.words/row/) and [Cell](https://reference.aspose.com/words/java/com.aspose.words/cell/) classes. |
{{< gist "aspose-words-gists" "4d42109bdf7df29c28ebfe1550c8e259" "table.java" >}} |                                                              |

## See Also

* [Working with Markdown Features](/words/java/working-with-markdown-features/)


## FAQ

1. **Q:** How can I convert a Markdown file to a Word document using Aspose.Words for Java?  
   **A:** Load the Markdown file with `Document doc = new Document("input.md");` and then save it in a Word format, e.g., `doc.save("output.docx");`. The library automatically parses the Markdown and builds the corresponding DOM.

2. **Q:** Is it possible to convert a Word document back to Markdown?  
   **A:** Yes. After loading a Word document (`Document doc = new Document("input.docx");`), call `doc.save("output.md");`. Aspose.Words will translate the DOM back to Markdown, preserving supported elements.

3. **Q:** Which style names are used for Markdown headings when they are imported?  
   **A:** Headings are mapped to built‑in styles named `Heading 1` … `Heading 9`. The importer expects the exact pattern without extra prefixes or suffixes; otherwise the text is treated as a normal paragraph.

4. **Q:** How are bulleted and ordered lists represented in the DOM?  
   **A:** Bulleted lists use `ListFormat.applyBulletDefault();` while ordered lists use `ListFormat.applyNumberDefault();`. The first‑level marker can be `-`, `+`, `*` for bullets and `.` or `)` for numbers.

5. **Q:** What classes are used for images and hyperlinks during conversion?  
   **A:** Images become `Shape` objects (`Shape shape = new Shape(doc, ShapeType.IMAGE);`). Hyperlinks and autolinks are represented by `FieldHyperlink` fields, which you can get from `doc.getRange().getFields()` by casting each `Field` whose `getType()` is `FieldType.FIELD_HYPERLINK` to `FieldHyperlink`.