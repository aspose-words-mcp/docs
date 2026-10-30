---
title: Table Overview
second_title: Aspose.Words for Python
articleTitle: Table Overview
linktitle: Table Overview
description: "Work with tables and their components such as cells, rows, columns in Aspose.Words for Python. How to work with tables in Python."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/table-overview/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page provides an overview of table handling in Aspose.Words for Python, describing the table structure, nodes (Table, Row, Cell), and how to work with them. It also explains nesting, the need for an empty paragraph between consecutive tables, and points to the Aspose.Words.Tables module for related classes and properties.
{{% /alert %}}

Aspose.Words is a class library designed for server-side processing of documents in various formats – PDF, HTML, different Microsoft Word formats and others – and supports tables in the following ways:

* tables in a document are preserved during open/save and conversions
* it is possible to edit table, content, and its formatting, and then export the changes to a file in a format that supports tables

In this article, we will learn more about table structure, cells, rows, and columns supported by Aspose.Words, and the details of working with such tables.

## Table Structure

As already mentioned, the table consists of such elements as **Cell**, **Row** and **Column**. These are concepts that are common to all tables in general, regardless of the document format.

This is a common example of a table found in a Microsoft Word document:

![tables-overview-aspose-words-net-1](tables-overview-1.png)

### Table Nodes

A table from any document loaded into Aspose.Words is imported as a **Table node**. The table can be found as a child of:

- main text
- an inline story such as a comment or a footnote
- cells when a table is nested within another table

{{% alert color="primary" %}}

Note that tables can be nested inside other tables to any depth.

{{% /alert %}}

### Table Content

The table node does not contain any real content – instead, it is a container for other such nodes that make up the content:

- **Table** contains many **Row** nodes. The table provides all the usual node elements, allowing you to freely move, modify, and remove the table in the document.
- **Row** represents a single table row and contains many **Cell** nodes. In addition, the **Row** provides elements that define how the row is displayed, such as height and alignment.
- **Cell** is what contains the true content visible in the table and is made up of a **Paragraph** and other block level nodes. Additionally, cells can contain nested tables.

![tables-overview-aspose-words-net-2](tables-overview-2.png)

{{% alert color="primary" %}}

You can check the structure of table nodes in a document using the **DocumentExplorer**.

{{% /alert %}}

### Empty Paragraph after Table

The picture above shows that the document contains a table of several rows, which in turn consists of two cells. Each of the two cells includes a paragraph, which is the container for the cell's formatted text.

It is also worth noting that separating two consecutive tables in a document requires at least one empty paragraph after the table. Without such a paragraph, consecutive tables would be joined together into one. This behavior is identical in both Microsoft Word and Aspose.Words.

In Aspose.Words, all classes and properties related to tables are contained in the [Aspose.Words.Tables](https://reference.aspose.com/words/python-net/aspose.words.tables/) namespace.

## See Also

* [Aspose.Words Document Object Model (DOM)](/words/python-net/aspose-words-document-object-model/)
* [Logical Levels of Nodes in a Document](/words/python-net/logical-levels-of-nodes-in-a-document/) 

## FAQ

1. **Q:** How can I retrieve all tables in a document, including those located in headers, footers, footnotes, or comments?  
   **A:** Use `Document.get_child_nodes(NodeType.TABLE, True)` which returns a collection of all `Table` nodes in the entire document tree. The `True` argument ensures that nodes from the main story, headers, footers, footnotes, and comments are included.

2. **Q:** How do I add a new row to an existing table?  
   **A:** Create a `Row` object, add the required number of `Cell` objects to it, and then append the row to the table with `Table.append_child(row)`. Each new cell can be populated with a `Paragraph` containing the desired text.

3. **Q:** What is the correct way to merge cells horizontally in a table?  
   **A:** Set the first cell's `cell_format.horizontal_merge` property to `HorizontalMerge.FIRST` and the subsequent cells that should be merged to `HorizontalMerge.PREVIOUS`. This merges the cells into a single larger cell while preserving the table layout.

4. **Q:** Why do two consecutive tables sometimes appear as a single table, and how can I prevent this?  
   **A:** Word treats adjacent tables as one unless there is at least one empty paragraph between them. Insert an empty `Paragraph` node after the first table (`table.parent_node.insert_after(aw.Paragraph(doc), table)`) to keep the tables separate.

5. **Q:** How can I access a specific cell by its row and column indexes?  
   **A:** Use `Table.rows[rowIndex].cells[cellIndex]` where `rowIndex` and `cellIndex` are zero‑based. This returns the `Cell` object, allowing you to read or modify its contents.