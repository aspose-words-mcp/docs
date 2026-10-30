---
title: Join Tables in C#
second_title: Aspose.Words for .NET
articleTitle: Join Tables
linktitle: Join Tables
description: "Join tables in C#. How to merge two tables into one C#."
type: docs
weight: 90
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/table-join/
aliases: [/net/joining-and-splitting-tables/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to join tables programmatically.

{{% /alert %}}

A table, represented in the Aspose.Words Document Object Model, is made up of independent rows and cells, making it easy to join tables.

To manipulate a table to join with another table, we just need to move the rows from the second table to the end of the first one and remove the second table's container.

The following code example shows how to merge rows from two tables into one:

{{< gist "aspose-words-gists" "b0735c64408bcb2c063f96f7c9d5af75" "combine-rows.cs" >}}

## Related APIs


- `Aspose.Words.Tables.Table` — Represents a table in the document.
- `Aspose.Words.Tables.Row` — Represents a table row.
- `Document.ImportNode(Node, bool)` — Imports a node from another document; `true` imports its child nodes as well.
- `RowCollection.Add(Node)` — Adds a row to the table's row collection.
- `Node.Remove()` — Removes the node from the document.

## FAQ

1. **Q:** How do I join two tables in a Word document using Aspose.Words for .NET?  
   **A:** Load the document, locate the two `Table` nodes, move each `Row` from the second table into the first with `firstTable.Rows.Add(secondTable.FirstRow)` until the second table is empty, and finally call `secondTable.Remove()` to delete the empty container.

2. **Q:** Will the original formatting of rows (borders, shading, cell width) be preserved after moving them?  
   **A:** Yes. A moved row keeps its cells and their formatting. `ImportNode` is needed only when the tables are in different documents; there, `ImportNode(row, true)` imports the row together with its cells.

3. **Q:** Can I join tables that have a different number of columns?  
   **A:** Yes. Each row keeps its own cells, so the joined table contains rows with different numbers of cells; nothing is truncated or added.

4. **Q:** After moving rows, the second table is still visible as an empty placeholder. How do I remove it?  
   **A:** Call `secondTable.Remove();` after all rows have been transferred. This deletes the table node from the document tree, eliminating the empty placeholder.

5. **Q:** Is there a way to join tables without losing any cell borders or shading that are defined on the table level?  
   **A:** Ensure that the first table already has the desired borders and shading before moving rows. Since row‑level formatting is preserved, the joined table will inherit the first table's overall border and shading settings. If needed, you can copy table‑level formatting from the second table to the first before the merge.