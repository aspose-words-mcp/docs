---
title: Work with Columns and Rows
second_title: Aspose.Words for Node.js via .NET
articleTitle: Work with Columns and Rows
linktitle: Work with Columns and Rows
description: "Working with parts of a table – rows, columns, and cells using Node.js. Specify Header Row Node.js."
type: docs
weight: 30
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-columns-and-rows/
timestamp: 2025-07-09-10-05-05
---

For more control over how tables work, learn how to manipulate columns and rows.

## Finding the Table Element Index

Columns, rows and cells are managed by accessing the selected document node by its index. Finding the index of any node involves gathering all child nodes of the element type from the parent node, and then using the [indexOf](https://reference.aspose.com/words/nodejs-net/aspose.words/nodecollection/indexof/) method to find the index of the desired node in the collection.

### Finding the Index of a Table in a Document

Sometimes you may need to make changes to a particular table in a document. To do this, you can refer to a table by its index.

The following code example shows how to retrieve the index of a table in a document:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "retrieve-table-index.js" >}}

### Finding the Index of a Row in a Table

Similarly, you may need to make changes to a specific row in a selected table. To do this, you can also refer to a row by its index.

The following code example shows how to retrieve the index of a row in a table:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "retrieve-row-index.js" >}}

### Finding the Index of a Cell in a Row

Finally, you may need to make changes to a specific cell, and you can do this by cell index as well.

The following code example shows how to retrieve the index of a cell in a row:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "retrieve-cell-index.js" >}}

## Work with Columns

In the Aspose.Words Document Object Model (DOM), the **Table** node consists of [Row](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/row/) nodes and then [Cell](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/cell/) nodes. Thus, in the `Document` Object Model of Aspose.Words, as in Word documents, there is no concept of a column.

By design, the table rows in Microsoft Word and Aspose.Words are completely independent, and the basic properties and operations are contained only in the rows and cells of the table. This gives tables the ability to have some interesting attributes:

- Each table row can have a completely different number of cells
- Vertically, the cells of each row can have different widths
- It is possible to join tables with different row formats and number of cells

Any operations performed on columns are actually "shortcuts" that perform the operation by collectively changing row cells in such a way that it looks like they are being applied to columns. That is, you can perform operations on columns by simply iterating over the same table row cell index.

The following code example simplifies such operations by proving a facade class that collects the cells that make up a "column" of a table:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "column-class.js" >}}

The following code example shows how to insert a blank column into a table:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "insert-blank-column.js" >}}

The following code example shows how to remove a column from a table in a document:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "remove-column.js" >}}

## Specify Rows as Header Rows

You can choose to repeat the first row in the table as the Header Row only on the first page or on each page if the table is split into several. In Aspose.Words, you can repeat the Header Row on every page using the [headingFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/rowformat/headingformat/) property.

You can also mark multiple header rows if such rows are located one after the other at the beginning of the table. To do this, you need to apply the **headingFormat** properties to these rows.

{{% alert color="primary" %}}

Note that Header Rows do not work in nested tables. That is, if you have a table inside another table, this setting will have no effect. It is a limitation of Microsoft Word that does not allow this, not Aspose.Words.

{{% /alert %}}

The following code example shows how to build a table which includes Header Rows that repeat on subsequent pages:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "repeat-rows-on-subsequent-pages.js" >}}

## Keep Tables and Rows from Breaking across Pages

There are times where the contents of a table should not be split across pages. For instance, a title is above a table, the title and table should always be kept together on the same page to preserve proper appearance.

There are two separate techniques that are useful to achieve this functionality:

- `Allow row break across pages`, which is applied to table rows
- `Keep with next`, which is applied to paragraphs in table cells

By default, the above properties are disabled.

### Keep a Row from Breaking across Pages

This involves restricting content inside the cells of a row from being split across a page. In Microsoft Word, this can found under Table Properties as the option “Allow row to break across pages”. In Aspose.Words this is found under the [RowFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/rowformat/) object of a [Row](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/row/) as the property [RowFormat.allowBreakAcrossPages](https://reference.aspose.com/words/nodejs-net/aspose.words.tables/rowformat/allowbreakacrosspages/).

The following code example shows how to disable breaking rows across pages for each row in a table:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "row-format-disable-break-across-pages.js" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Table%20spanning%20two%20pages.docx).

{{% /alert %}}

### Keep a Table from Breaking across Pages

To stop the table from splitting across pages, we need to specify that we want the content contained within the table to stay together.

To do this, Aspose.Words uses a method, which allows users to select a table and enable the [keepWithNext](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/keepWithNext/) parameter to true for each paragraph within the table cells. The exception is the last paragraph in the table, which should be set to false.

The following code example shows how to set a table to stay together on the same page:

{{< gist "aspose-words-gists" "0b4aa2dc6bae9b78989a4a7283d7c8da" "keep-table-together.js" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Table%20spanning%20two%20pages.docx).

{{% /alert %}}

------ 

## FAQ

1. **Q:** How can I insert a new blank column into an existing table?  
   **A:** Use the helper `Column` class to collect cells at the same index across all rows, then call its `insertColumnBefore` method. The sample `insert-blank-column.js` demonstrates creating a new `Cell` and inserting it at the desired column index for each row.

2. **Q:** What is the recommended way to delete a column from a table?  
   **A:** Iterate through each row, retrieve the cell at the column index you want to remove, and call `remove()` on that cell. The `remove-column.js` example shows this approach, ensuring the table structure stays consistent.

3. **Q:** How do I make the first row of a table repeat as a header on every page?  
   **A:** Set the `headingFormat` property of the row's `RowFormat` to `true`. For multiple header rows, set this property on each consecutive row at the top of the table. See `repeat-rows-on-subsequent-pages.js` for a complete example.

4. **Q:** How can I prevent a row from breaking across pages?  
   **A:** Set `RowFormat.allowBreakAcrossPages` to `false` for the row. This disables the “Allow row to break across pages” option. The `row-format-disable-break-across-pages.js` snippet illustrates the setting.

5. **Q:** How do I keep an entire table together on a single page?  
   **A:** Enable `keepWithNext` for every paragraph inside the table cells, except the last paragraph of the table. The `keep-table-together.js` example shows how to traverse the table's paragraphs and apply the property.