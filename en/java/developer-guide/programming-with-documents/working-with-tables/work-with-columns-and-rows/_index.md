---
title: Work with Columns and Rows in Java
second_title: Aspose.Words for Java
articleTitle: Work with Columns and Rows
linktitle: Work with Columns and Rows
description: "Working with parts of a table – rows, columns, and cells using Java. Specify Header Row Java."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-columns-and-rows/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with table columns and rows programmatically.

{{% /alert %}}

For more control over how tables work, learn how to manipulate columns and rows.

## Find the Table Element Index {#find-the-index-of-table-elements}

Columns, rows and cells are managed by accessing the selected document node by its index. Finding the index of any node involves gathering all child nodes of the element type from the parent node, and then using the [indexOf()](https://reference.aspose.com/words/java/com.aspose.words/nodecollection/#indexOf-com.aspose.words.Node) method to find the index of the desired node in the collection.

### Find the Index of a Table in a Document {#find-the-index-of-table-in-a-document}

Sometimes you may need to make changes to a particular table in a document. To do this, you can refer to a table by its index.

The following code example shows how to retrieve the index of a table in a document:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "retrieve-table-index.java" >}}

### Find the Index of a Row in a Table {#find-the-index-of-a-row-in-a-table}

Similarly, you may need to make changes to a specific row in a selected table. To do this, you can also refer to a row by its index.

The following code example shows how to retrieve the index of a row in a table:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "retrieve-row-index.java" >}}

### Find the Index of a Cell in a Row {#find-the-index-of-a-cell-in-a-row}

Finally, you may need to make changes to a specific cell, and you can do this by cell index as well.

The following code example shows how to retrieve the index of a cell in a row:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "retrieve-cell-index.java" >}}

## Work with Columns {#work-with-columns}

In the Aspose.Words Document Object Model (DOM), the [Table](https://reference.aspose.com/words/java/com.aspose.words/table/) node consists of [Row](https://reference.aspose.com/words/java/com.aspose.words/row/) nodes and then [Cell](https://reference.aspose.com/words/java/com.aspose.words/cell/) nodes. Thus, in the `Document` Object Model of Aspose.Words, as in Word documents, there is no concept of a column.

By design, the table rows in Microsoft Word and Aspose.Words are completely independent, and the basic properties and operations are contained only in the rows and cells of the table. This gives tables the ability to have some interesting attributes:

- Each table row can have a completely different number of cells
- Vertically, the cells of each row can have different widths
- It is possible to join tables with different row formats and number of cells

Any operations performed on columns are actually "shortcuts" that perform the operation by collectively changing row cells in such a way that it looks like they are being applied to columns. That is, you can perform operations on columns by simply iterating over the same table row cell index.

The following code example simplifies such operations by proving a facade class that collects the cells that make up a "column" of a table:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "column-class.java" >}}

The following code example shows how to insert a blank column into a table:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "insert-blank-column.java" >}}

The following code example shows how to remove a column from a table in a document:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "remove-column.java" >}}

## Specify Rows as Header Rows

You can choose to repeat the first row in the table as the Header Row only on the first page or on each page if the table is split into several. In Aspose.Words, you can repeat the Header Row on every page using the [getHeadingFormat()](https://reference.aspose.com/words/java/com.aspose.words/rowformat/#getHeadingFormat) property.

You can also mark multiple header rows if such rows are located one after the other at the beginning of the table. To do this, you need to apply the **getHeadingFormat()** properties to these rows.

{{% alert color="primary" %}}

Note that Header Rows do not work in nested tables. That is, if you have a table inside another table, this setting will have no effect. It is a limitation of Microsoft Word that does not allow this, not Aspose.Words.

{{% /alert %}}

The following code example shows how to build a table which includes Header Rows that repeat on subsequent pages:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "repeat-rows-on-subsequent-pages.java" >}}

## Keep Tables and Rows from Breaking Across Pages {#keep-tables-and-rows-from-breaking-across-pages}

There are times where the contents of a table should not be split across pages. For instance, if a title is above a table, the title and table should always be kept together on the same page to preserve proper appearance.

There are two separate techniques that are useful to achieve this functionality:

- `Allow row break across pages`, which is applied to table rows
- `Keep with next`, which is applied to paragraphs in table cells

By default, the above properties are disabled.

### Keep a Row from Breaking Across Pages {#keep-a-row-from-breaking-across-pages}

This involves restricting content inside the cells of a row from being split across a page. In Microsoft Word, this can found under Table Properties as the option “Allow row to break across pages”. In Aspose.Words this is found under the [RowFormat](https://reference.aspose.com/words/java/com.aspose.words/rowformat/) object of a [Row](https://reference.aspose.com/words/java/com.aspose.words/row/) as the property [RowFormat.getAllowBreakAcrossPages()](https://reference.aspose.com/words/java/com.aspose.words/rowformat/#getAllowBreakAcrossPages).

The following code example shows how to disable breaking rows across pages for each row in a table:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "row-format-disable-break-across-pages.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Table%20spanning%20two%20pages.docx).

{{% /alert %}}

### Keep a Table from Breaking Across Pages {#keep-a-table-from-breaking-across-pages}

To stop the table from splitting across pages, we need to specify that we want the content contained within the table to stay together.

To do this, Aspose.Words uses a method, which allows users to select a table and enable the [getKeepWithNext()](https://reference.aspose.com/words/java/com.aspose.words/paragraphformat/#getKeepWithNext) parameter to true for each paragraph within the table cells. The exception is the last paragraph in the table, which should be set to false.

The following code example shows how to set a table to stay together on the same page:

{{< gist "aspose-words-gists" "14f5cea1b896ffd04f143627939e0878" "keep-table-together.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Table%20spanning%20two%20pages.docx).

{{% /alert %}}

## Related APIs

- [Table](https://reference.aspose.com/words/java/com.aspose.words/table/)
- [Row](https://reference.aspose.com/words/java/com.aspose.words/row/)
- [Cell](https://reference.aspose.com/words/java/com.aspose.words/cell/)
- [RowFormat.getHeadingFormat()](https://reference.aspose.com/words/java/com.aspose.words/rowformat/#getHeadingFormat)
- [RowFormat.getAllowBreakAcrossPages()](https://reference.aspose.com/words/java/com.aspose.words/rowformat/#getAllowBreakAcrossPages)
- [ParagraphFormat.getKeepWithNext()](https://reference.aspose.com/words/java/com.aspose.words/paragraphformat/#getKeepWithNext)
- [NodeCollection.indexOf](https://reference.aspose.com/words/java/com.aspose.words/nodecollection/#indexOf-com.aspose.words.Node)

## FAQ

1. **Q:** How can I insert a new blank column into an existing table?  
   **A:** Use a helper class that gathers cells by column index, then iterate through each row and insert a new `Cell` at the desired position. After insertion, you may need to adjust column widths to maintain layout.

2. **Q:** What is the recommended way to remove a column from a table?  
   **A:** Iterate over all rows of the table and call `Row.getCells().removeAt(columnIndex)` for the column you want to delete. Ensure that any merged cells spanning the removed column are handled appropriately.

3. **Q:** How do I make the first row of a table repeat as a header on every page?  
   **A:** Set `Row.getRowFormat().setHeadingFormat(true)` on the first row (or on multiple consecutive rows) before saving the document. This marks the rows as header rows that Word repeats on each page.

4. **Q:** How can I prevent a table row from breaking across pages?  
   **A:** Set `Row.getRowFormat().setAllowBreakAcrossPages(false)` for the rows you want to keep together. This disables the “Allow row to break across pages” option.

5. **Q:** How do I keep an entire table on the same page without splitting?  
   **A:** For each paragraph inside the table cells, set `Paragraph.getParagraphFormat().setKeepWithNext(true)`, except for the last paragraph in the table where it should be `false`. This forces Word to keep the table together when possible.