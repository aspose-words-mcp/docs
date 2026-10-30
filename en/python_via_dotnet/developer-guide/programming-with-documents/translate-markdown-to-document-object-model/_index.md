---
title: Translate Markdown to DOM
second_title: Aspose.Words for Python via .NET
articleTitle: Translate Markdown to Document Object Model (DOM)
linktitle: Translate Markdown to Document Object Model (DOM)
type: docs
description: "Tarnslate a Markdown document to Document Object Model and back using Python. So you can work with complex existing Markdown and programmatically create a Markdown document from scratch."
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/translate-markdown-to-document-object-model/
aliases: [/python/translate-markdown-to-document-object-model/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains how to translate Markdown documents to the Aspose.Words Document Object Model (DOM) and back using Python via .NET, detailing the mapping of Markdown features to DOM elements and providing code examples.
{{% /alert %}}

To programmatically read, manipulate, and modify the content and formatting of a document, you need to translate it to the Aspose.Words Document Object Model (DOM).

In contrast to Word documents, Markdown does not conform to the DOM described in the [Aspose.Words Document Object Model (DOM)](/words/python-net/aspose-words-document-object-model/) article. However, Aspose.Words provides its own mechanism for translating Markdown documents to DOM and back, so that we can successfully work with their elements such as text formatting, tables, headers, and others.

This article explains how the various markdown features can be translated into Aspose.Words DOM and back to Markdown format.

## Complexity of Translation Markdown – DOM – Markdown

The main difficulty of this mechanism is not only to translate Markdown to DOM, but also to do the reverse transformation – to save the document back to Markdown format with minimal loss. There are elements, such as multilevel quotes, for which the reverse transformation is not trivial.

Our translation engine allows users not only to work with complex elements in an existing Markdown document, but also to create their own document in Markdown format with the original structure from scratch. To create various elements, you need to use styles with specific names according to certain rules described later in this article. Such styles can be created programmatically.

## Common Translation Principles

We use [Font](https://reference.aspose.com/words/python-net/aspose.words/font/) formatting for inline blocks. When there is no direct correspondence for a Markdown feature in Aspose.Words DOM, we use a character style with a name that starts from some special words.

For container blocks, we use style inheritance to denote nested Markdown features. In this case, even when there are no nested features, we also use paragraph styles with a name that starts from some special words.

Bulleted and ordered lists are container blocks in Markdown as well. Their nesting is represented in DOM the same way as for all other container blocks using style inheritance. However, additionally, lists in DOM have corresponded number formatting in either list style or paragraph formatting.

## Inline Blocks

We use [Font](https://reference.aspose.com/words/python-net/aspose.words/font/) formatting when translating **Bold**, *Italic* or ~~Strikethrough~~ inline markdown features.

| Markdown feature              | Aspose.Words       |
| ----------------------------- | ------------------ |
| **Bold**<br />`**bold text**` | `Font.bold = true` |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "bold-text.py" >}} |  |
| **Italic**<br />`*italic text*` | `Font.italic = true` |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "italic-text.py" >}} |  |
| **Strikethrough**<br />`~Strikethrough text~` | `Font.strike_through = true` |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "strikethrough.py" >}} |  |

We use a character style with a name that starts from the word `InlineCode`, followed by an optional dot `(.)` and a number of backticks ```(`)``` for the `InlineCode` feature. If a number of backticks is missed, then one backtick will be used by default.

| Markdown feature              | Aspose.Words       |
| ----------------------------- | ------------------ |
| **InlineCode**<br />`**inline code**` | `Font.style.name = “InlineCode[.][N]”` |
| {{< gist "aspose-words-gists" "461290170d82b0922d265fa7bc854942" "inline-code.py" >}} |  |
| **Autolink**<br />`<scheme://domain.com>`<br />`<email@domain.com>` | The [FieldHyperlink](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldhyperlink/) class. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "autolink.py" >}} |  |
| **Link**<br />`[link text](url)`<br />`[link text](<url> "title")`<br />`[link text](url 'title')`<br />`[link text](url (title))` | The [FieldHyperlink](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldhyperlink/) class. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "link.py" >}} |  |
| **Image**<br />`![](url)`<br />`![alt text](<url> “title”)`<br />`![alt text](url ‘title’)`<br />`![alt text](url (title))` | The [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) class. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "image.py" >}} |  |

## Container Blocks

A document is a sequence of container blocks such as headings, paragraphs, lists, quotes, and others. Container blocks can be divided into 2 classes: Leaf blocks and Complex Containers. Leaf blocks can only contain inline content. Complex containers, in turn, can contain other container blocks, including Leaf blocks.

### Leaf Blocks

The table below shows examples of using Markdown Leaf blocks in Aspose.Words:

| Markdown feature                                             | Aspose.Words                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **HorizontalRule**<br />`-----`                              | This is a simple paragraph with a corresponding HorizontalRule shape:<br />`DocumentBuilder.insert_horizontal_rule()` |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "horizontal-rule.py" >}} |                                                              |
| **ATX Heading**<br />`# H1, ## H2, ### H3…`                  | `ParagraphFormat.style.name = "Heading N"`, where (1<= N <= 9).<br />This is translated into a built-in style and should be exactly of the specified pattern (no suffixes or prefixes are allowed).<br />Otherwise, it will be just a regular paragraph with a corresponding style. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "heading.py" >}} |                                                              |
| **Setext Heading**<br />`===` (if Heading level 1),<br />`---` (if Heading level 2) | `ParagraphFormat.style.name = “SetextHeading[some suffix]”`, based on 'Heading N' style.<br />If (N >= 2), then 'Heading 2' will be used, otherwise 'Heading 1'.<br />Any suffix is allowed, but Aspose.Words importer uses numbers “1” and “2” respectively. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "setext-heading.py" >}} |
| **Indented Code**                                            | `ParagraphFormat.style.name = “IndentedCode[some suffix]”`    |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "indented-code.py" >}} |                                                              |
| **Fenced Code**<br />{{< highlight python >}}```
if ()
then
else
```{{< /highlight >}} | `ParagraphFormat.style.name = “FencedCode[.][info string]”`<br />The `[.]` and `[info string]` are optional. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "fenced-code.py" >}} |                                                              |

### Complex Containers

The table below shows examples of using Markdown Complex Containers in Aspose.Words:

| Markdown feature                                             | Aspose.Words                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Quote**<br />`> quote,`<br />`>> nested quote`             | `ParagraphFormat.style.name = “Quote[some suffix]”`<br />The suffix in style name is optional, but Aspose.Words importer uses the ordered numbers 1, 2, 3, …. in case of nested quotes.<br />The nesting is defined via the inherited styles. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "quote.py" >}} |
| **BulletedList**<br />`- Item 1`<br />`- Item 2`<br />	`   - Item 2a`<br />	`   - Item 2b` | Bulleted lists are represented using paragraph numbering:<br />`ListFormat.apply_bullet_default()`<br />There can be 3 types of bulleted lists. They are only diff in a numbering format of the very first level. These are: `‘-’`, `‘+’` or `‘*’` respectively. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "bulleted-list.py" >}} |                                                              |
| **OrderedList**<br />`1. Item 1`<br />`2. Item 2`<br />	`1) Item 2a`<br />	`2) Item 2b` | Ordered lists are represented using paragraph numbering:<br />`ListFormat.apply_number_default()`<br />There can be 2 number format markers: ‘.’ and ‘)’. The default marker is ‘.’. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "ordered-list.py" >}} |

### Tables

Aspose.Words also allows to translate tables into DOM, as shown below:

| Markdown feature                                             | Aspose.Words                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `Table`<br />`a|b`<br />`-|-`<br />`c|d`                     | [Table](https://reference.aspose.com/words/python-net/aspose.words.tables/table/), [Row](https://reference.aspose.com/words/python-net/aspose.words.tables/row/) and [Cell](https://reference.aspose.com/words/python-net/aspose.words.tables/cell/) classes. |
{{< gist "aspose-words-gists" "9d58f66f28ab6fd0b0b6ae4222cc71a4" "table.py" >}} |                                                              |

## See Also

* [Working with Markdown Features](/words/python-net/working-with-markdown-features/)

## FAQ

1. **Q:** How should heading styles be named when translating Markdown headings to the Aspose.Words DOM?  
   **A:** Use built‑in heading styles with the exact pattern `Heading N` where **N** is the level (1‑9). Do not add any prefixes or suffixes to `Heading N`; otherwise the paragraph will be treated as a normal paragraph. For Setext headings the importer creates a `SetextHeading` style with a suffix (it uses `1` and `2`; any suffix is allowed) that is based on the corresponding `Heading N` style.

2. **Q:** How can I change the bullet or number format of a Markdown list after it has been imported?  
   **A:** After creating the list with `builder.list_format.apply_bullet_default()` or `apply_number_default()`, modify the first level’s `number_format` property. For example, `builder.list_format.list.list_levels[0].number_format = "-"` changes a bulleted list to use a hyphen, and `builder.list_format.list.list_levels[0].number_format = "\x00)"` (`\x00` is the placeholder for the level number) changes an ordered list to use a closing parenthesis.

3. **Q:** What is the recommended way to represent nested blockquotes in the DOM?  
   **A:** Create a paragraph style named `Quote` for the first level. For each deeper level, add a new paragraph style (e.g., `Quote1`, `Quote2`) and set its `base_style_name` to the style of the previous level. The importer will then map nested `>` symbols to these inherited styles.

4. **Q:** How can I adjust the font size of Markdown content that has been imported into a document?  
   **A:** Use `DocumentBuilder` to set the font size before writing the text, e.g., `builder.font.size = 14`. If the content is already present, retrieve the relevant paragraphs and set `run.font.size = 14` for the runs of each paragraph that needs resizing (or change `font.size` of the paragraph style).

5. **Q:** How are indented and fenced code blocks represented, and can I customize their appearance?  
   **A:** Indented code blocks use a paragraph style `IndentedCode[...]`; fenced code blocks use `FencedCode[.][info]`. You can create or modify these styles, e.g., `style = doc.styles.add(aw.StyleType.PARAGRAPH, "IndentedCode")` (or `"FencedCode.C#"` for a fenced block with the `C#` info string), then adjust properties such as `style.font.name`, `style.font.size`, or `style.paragraph_format.shading` to change the visual appearance of the code blocks.