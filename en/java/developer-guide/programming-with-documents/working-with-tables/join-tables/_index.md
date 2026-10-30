---
title: Join Tables in Java
second_title: Aspose.Words for Java
articleTitle: Join Tables
linktitle: Join Tables
description: "Join Tables in Java. Advanced table manipulations, join and split using Java."
type: docs
weight: 90
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/join-tables/
aliases: [/java/joining-and-splitting-tables/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to join tables programmatically.

{{% /alert %}}

A table, represented in the Aspose.Words Document Object Model, is made up of independent rows and cells, making it easy to join tables.

To manipulate a table to join with another table, we just need to move the rows from the second table to the end of the first one and remove the second table's container.

The following code example shows how to merge rows from two tables into one:

{{< gist "aspose-words-gists" "89807559333317718ba2e6084fdcb3e2" "combine-rows.java" >}}

## Related APIs

- `com.aspose.words.Table` — Represents a table in the document.
- `com.aspose.words.Row` — Represents a table row.
- `Document.importNode(Node, boolean)` — Imports a node from another document; `true` imports its child nodes as well.
- `RowCollection.add(Node)` — Adds a row to the table's row collection.
- `Node.remove()` — Removes the node from the document. 

## FAQ

1. **Q:** How can I join two tables in a Word document using Aspose.Words for Java?  
   **A:** Locate the two `Table` objects in the document, then move each `Row` from the second table into the first using `firstTable.appendChild(row.deepClone(true))`. After all rows are transferred, remove the now‑empty second table with `secondTable.remove()`. Finally, call `doc.updatePageLayout()` to refresh the layout.

2. **Q:** How do I split a joined table back into separate tables?  
   **A:** Create a new `Table` instance, move the rows you want to separate from the original table into the new one, and insert the new table at the desired position using `firstTable.getParentNode().insertAfter(newTable, firstTable)`. Adjust any required formatting on the new table's rows and cells.

3. **Q:** The joined table loses its original formatting after moving rows. What should I do?  
   **A:** Moving a row with `appendChild` keeps the row, its cells, and their formatting, so cloning is not needed. If the tables are in different documents, import the row with `firstTable.getDocument().importNode(row, true)`; `true` imports the row together with its cells.