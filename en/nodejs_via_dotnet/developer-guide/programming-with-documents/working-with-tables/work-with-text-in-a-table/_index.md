---
title: Work with Text in a Table
second_title: Aspose.Words for Node.js
articleTitle: Work with Text in a Table
linktitle: Work with Text in a Table
description: "Replace text in a table in Node.js. Extract Plain Text from Table or Cell using Node.js."
type: docs
weight: 60
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/work-with-text-in-a-table/
timestamp: 2025-07-09-10-05-05
---

As mentioned in previous articles, a table usually contains plain text, although other content such as images or even other tables can be placed in table cells.

Adding text or other content to the table is carried out using the appropriate methods of the [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) class and is described in the **"Create a Table"** article. In this article, we will talk about how to work with text in an already existing table.

## Replace Text in a Table

The table, like any other node in Aspose.Words, has access to the [Range](https://reference.aspose.com/words/nodejs-net/aspose.words/range/) object. Using the table range object, you can replace text in a table.

The ability to use special characters when replacing is currently supported, so it is possible to replace existing text with multi‑paragraph text. To do this, you need to use the special metacharacters described in the corresponding [replace](https://reference.aspose.com/words/nodejs-net/aspose.words/range/replace/) method.

{{% alert color="primary" %}}

Typically, text replacement should be done at the cell level (per cell) or at the paragraph level.

{{% /alert %}}

The following code example shows how to replace all instances of a string of text in the cells of an entire table:

{{< gist "aspose-words-gists" "1693b4ac01f19ec81c9618649b62acb8" "replace-text.js" >}}

## Extract Plain Text from Table or Cell

Using the **Range** object, you can also call methods on the entire table range and extract the table as plain text. To do this, use the [text](https://reference.aspose.com/words/nodejs-net/aspose.words/range/text/) property. 

The following code example shows how to print the text range of a table:

{{< gist "aspose-words-gists" "1693b4ac01f19ec81c9618649b62acb8" "extract-text.js" >}}

The same technique is used to extract content from individual table cells only.

The following code example shows how to print a text range of row and table elements:

{{< gist "aspose-words-gists" "1693b4ac01f19ec81c9618649b62acb8" "print-text-range-row-and-table.js" >}}

## Working with Alternative Table Text

Microsoft Word tables have a `table title` and `table description` that provide an alternative textual representation of the information contained in the table.

In Aspose.Words, you can also add a table title and description using the [title](https://reference.aspose.com/words/nodejs-net/aspose.words/table/title/) and [description](https://reference.aspose.com/words/nodejs-net/aspose.words/table/description/) properties. These properties are meaningful for DOCX documents conforming to the ISO/IEC 29500. When saving in formats earlier than ISO/IEC 29500, these properties are ignored.

The following code example shows how to set the title and description properties of a table:

{{< gist "aspose-words-gists" "1693b4ac01f19ec81c9618649b62acb8" "table-title-and-description.js" >}}

------  

## FAQ  

1. **Q:** How can I replace text throughout an entire table with a single call?  
   **A:** Obtain the table's `Range` object (`table.range`) and call `range.replace(oldText, newText)`. This replaces every occurrence of *oldText* in all cells of the table.  

2. **Q:** Can the replacement text contain line breaks or multiple paragraphs?  
   **A:** Yes. Use the metacharacters `&p` (paragraph break) and `&l` (manual line break) in the replacement string, as described in the `Range.replace` documentation.  

3. **Q:** What is the easiest way to get the plain text of a specific cell?  
   **A:** Access the cell's `Range` (`cell.range`) and read its `text` property. This returns the cell's content without any formatting tags.  

4. **Q:** How do I set a table title and description for accessibility purposes?  
   **A:** Use the `title` and `description` properties of the `Table` object (`table.title = "My Table"; table.description = "Summary of sales data";`). These are stored in the DOCX file and are visible to screen readers.  

5. **Q:** Is it possible to replace text only in certain columns while leaving others untouched?  
   **A:** Iterate through the desired columns, retrieve each cell's `Range`, and call `replace` on that range only. This gives fine‑grained control over which parts of the table are modified.  