---
title: How to Create a Table in Java
second_title: Aspose.Words for Java
articleTitle: Create a Table
linktitle: Create a Table
description: "A guide on how to make a table in Java in various ways. Create table in Java for your document."
type: docs
aliases:
 - /java/tables-overview/
 - /java/creating-tables/
 - /java/introduction-and-creating-tables/
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/create-a-table/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to create a table in a Word document programmatically and discusses styling, formatting, and content population.

{{% /alert %}}

Aspose.Words allows users to create tables in a document from scratch and provides several different methods for doing so. This article presents details on how to add formatted tables to your document using each method, as well as a comparison of each method at the end of the article.

## Default Table Styles

The newly created table is given default values similar to those used in Microsoft Word:

| Table Property | Default in Aspose.Words |
| :--------------------- | :---------------------- |
| `Border Style` | `Single` |
| `Border Width` | `1/2 pt` |
| `Border Color` | `Black` |
| `Left and Right Padding` | `5.4 pts` |
| `AutoFit Mode` | `AutoFit to Window` |
| `Allow AutoFit` | `True` |

{{% alert color="primary" %}}

A table can be inline if it is tightly positioned, or floating if it can be positioned anywhere on the page. By default, Aspose.Words always creates inline tables.

{{% /alert %}}

## Create a Table with DocumentBuilder

In Aspose.Words, users can create a table in a document using the [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/). The basic algorithm for creating a table is as follows:

1. Start the table with [startTable()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#startTable)
2. Add a cell to the table using [insertCell()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertCell) – this automatically starts a new row
3. Optionally, use the [getCellFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCellFormat) property to specify cell formatting
4. Insert the cell content using the appropriate **DocumentBuilder** methods such as [writeln()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#writeln), [InsertImage](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertImage-byte), and others
5. Repeat steps 2-4 until the row is complete
6. Call [endRow()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endRow) to end the current row
7. Optionally, use the [getRowFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getRowFormat) property to specify row formatting
8. Repeat steps 2-7 until the table is complete
9. Call [endTable()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endTable) to finish building the table

{{% alert color="primary" %}}

Important details:

* [startTable()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#startTable) can also be called inside a cell, in which case it starts the creation of a nested table within the cell.
* After calling [insertCell()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertCell), a new cell is created, and any content you add using other methods of the [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) class will be added to the current cell. To create a new cell on the same row, call **insertCell()** again.
* If **insertCell()** is called immediately after [endRow()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endRow) and the end of a row, the table will continue on a new row.
* The [endTable()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endTable) method to end the table should only be called once after calling **endRow()**. Calling **endTable()** moves the cursor from the current cell to the position immediately after the table.

{{% /alert %}}

The process of creating a table can be clearly seen in the following picture:

![creating-table-process](creating-table-process.jpg)

The following code example shows how to create a simple table using **DocumentBuilder** with default formatting:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "create-simple-table.java" >}}

The following code example shows how to create a formatted table using DocumentBuilder:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "formatted-table.java" >}}

The following code example shows how to insert a nested table using DocumentBuilder:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "nested-table.java" >}}

## Create a Table via DOM (Document Object Model)

You can insert tables directly into the DOM by adding a new [Table](https://reference.aspose.com/words/java/com.aspose.words/table/) node at a specific position.

Please note that immediately after the table node creation, the table itself will be completely empty, that is it does not yet contain rows and cells. To insert rows and cells into a table, add the appropriate [Row](https://reference.aspose.com/words/java/com.aspose.words/row/) and [Cell](https://reference.aspose.com/words/java/com.aspose.words/cell/) child nodes to the DOM.

{{% alert color="primary" %}}

This method of creating a table uses the same table defaults as when using the **DocumentBuilder**.

{{% /alert %}}

The following code example shows how to build a new table from scratch by adding the appropriate child nodes to the document tree:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "insert-table-directly.java" >}}

## Create a Table from HTML

Aspose.Words supports inserting content into a document from an HTML source using the [insertHtml()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHtml-java.lang.String) method. The input can be a complete HTML page or just a partial snippet.

Using the **insertHtml()** method, users can insert tables into the document via table tags like `<table>`, `<tr>`, `<td>`.

The following code example shows how to insert a table into a document from a string containing HTML tags:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "insert-table-from-html.java" >}}

## Insert a Copy of an Existing Table

There are often times when you need to create a table based on an already existing table in a document. The easiest way to duplicate a table while retaining all formatting is to clone the Table node using the [deepClone](https://reference.aspose.com/words/java/com.aspose.words/node/#deepClone-boolean) method.

The same technique can be used to add copies of an existing row or cell to a table.

The following code example shows how to duplicate a table using node constructors:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "clone-complete-table.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Tables.docx).

{{% /alert %}}

The following code example shows how to clone the last row of a table and append it to the table:

{{< gist "aspose-words-gists" "68616fbf7f092a743b66d4491578d18c" "clone-last-row.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Tables.docx).

{{% /alert %}}

If you are looking at creating tables in a document that grow dynamically with each record from your data source, then the above method is not advised. Instead, the desired output is more easily achieved by using Mail merge with regions. You can learn more about this technique in the [Mail Merge with Regions](/words/java/types-of-mail-merge-operations/#mail-merge-with-regions) section.

## Compare Ways to Create a Table

Aspose.Words provides several methods to create new tables in a document. Each method has its own advantages and disadvantages, so the choice of which to use often depends on the specific situation.

Let's take a closer look at these ways of creating tables and compare their pros and cons:

| Method | Advantages | Disadvantages |
| :- | :- | :- |
| Via `DocumentBuilder` | The standard method for inserting tables and other document content | Sometimes difficult to create many varieties of tables at the same time with the same builder instance |
| Via DOM | Fits in better with surrounding code that creates and inserts nodes directly into the DOM without using a **DocumentBuilder** | The table is created "empty": before performing most operations, you must call [ensureMinimum()](https://reference.aspose.com/words/java/com.aspose.words/table/#ensureMinimum) to create any missing child nodes |
| From HTML | Can create a new table from HTML source using tags like `<table>`, `<tr>`, `<td>` | Not all possible Microsoft Word table formats can be applied to HTML |
| Cloning an existing table | You can create a copy of an existing table while retaining all row and cell formatting | The appropriate child nodes must be removed before the table is ready for use |

## Related APIs

- [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/)
- [Table](https://reference.aspose.com/words/java/com.aspose.words/table/)
- [Row](https://reference.aspose.com/words/java/com.aspose.words/row/)
- [Cell](https://reference.aspose.com/words/java/com.aspose.words/cell/)
- [Node.deepClone(boolean)](https://reference.aspose.com/words/java/com.aspose.words/node/#deepClone-boolean)
- [DocumentBuilder.insertHtml](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHtml-java.lang.String)
- [Table.ensureMinimum](https://reference.aspose.com/words/java/com.aspose.words/table/#ensureMinimum)
