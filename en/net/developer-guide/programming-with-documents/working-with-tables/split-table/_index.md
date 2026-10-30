---
title: Split Table in C#
second_title: Aspose.Words for .NET
articleTitle: Split Table
linktitle: Split Table
description: "Split table in C#. How to split one table into two separate tables C#."
type: docs
weight: 100
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/split-table/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to split a table into multiple tables.

{{% /alert %}}

A table, represented in the Aspose.Words Document Object Model, is made up of independent rows and cells, making it easy to split a table.

To manipulate a table to split it into two tables, we just need to move some of the rows from the original table to the new one. To do this, we need to pick the row by which we want to split the table.

We can create two tables from the original table by following these simple steps:

1. Create a clone of the table without cloning the children to keep the moved rows and insert them after the original table
2. Starting at the specified row, move all subsequent rows to this second table

The following code example shows how to split a table into two tables on a specific row:

{{< gist "aspose-words-gists" "4ab56c5443822fa44f4cac1f45af32b7" "split-table.cs" >}}

## Limitations and Considerations

- **Merged cells**: Aspose.Words does not change merge flags when rows are moved. If a vertically merged cell spans the split row, the first moved cell keeps `CellMerge.Previous`; set its `CellFormat.VerticalMerge` to `CellMerge.First` so that the merged block starts correctly in the new table.

- **Formatting preservation**: The formatting applied to rows, cells, and the table itself is retained because the rows are moved, not recreated. Any style or direct formatting on the moved rows remains unchanged in the new table.

- **Pagination effects**: Aspose.Words recalculates pagination automatically after the table structure changes. To avoid unexpected pagination shifts, perform the split operation before any layout-dependent processing (e.g., before saving or printing).

## Related APIs


- [Table](https://reference.aspose.com/words/net/aspose.words.tables/table/)
- [Row](https://reference.aspose.com/words/net/aspose.words.tables/row/)
- [Cell](https://reference.aspose.com/words/net/aspose.words.tables/cell/)
- [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/)
- [NodeCollection](https://reference.aspose.com/words/net/aspose.words/nodecollection/)

## FAQ

1. **Q:** How do I split a table at a particular row using Aspose.Words for .NET?  
   **A:** Create a clone of the original `Table` without its child nodes, insert the clone after the original table, then move all rows starting from the chosen split row to the cloned table. This separates the original table into two independent tables.

2. **Q:** What happens to merged cells that cross the split row?  
   **A:** Aspose.Words does not change merge flags when rows are moved. If a vertically merged cell spans the split row, the first moved cell keeps `CellMerge.Previous`; set its `CellFormat.VerticalMerge` to `CellMerge.First` so that the merged block starts correctly in the new table.

3. **Q:** Can I split a table into more than two tables?  
   **A:** Yes. After the first split, repeat the same process on the resulting tables: clone the table you want to split, insert the clone, and move the desired rows. By iterating, you can create any number of separate tables.

4. **Q:** Will the formatting (borders, shading, etc.) be preserved after splitting?  
   **A:** The formatting applied to rows, cells, and the table itself is retained because the rows are moved, not recreated. Any style or direct formatting on the moved rows remains unchanged in the new table.

5. **Q:** How can I split a table without affecting the document's pagination?  
   **A:** Perform the split operation before any layout‑dependent processing (e.g., before saving or printing). Aspose.Words recalculates pagination automatically after the table structure changes, ensuring the document flow remains correct.