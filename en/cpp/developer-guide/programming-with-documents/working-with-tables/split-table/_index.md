---
title: Split Table in C++
second_title: Aspose.Words for C++
articleTitle: Split Table
linktitle: Split Table
description: "Split table in C++. How to split one table into two separate tables C++."
type: docs
weight: 100
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/split-table/
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

{{< gist "aspose-words-gists" "29ce7710cab8c3ef18e912a5813e0d36" "split-table.h" >}}

## Limitations and Considerations

- **Merged cells**: Aspose.Words does not change merge flags when rows are moved. If a vertically merged cell spans the split row, the first moved cell keeps `CellMerge::Previous`; call its `get_CellFormat()->set_VerticalMerge(CellMerge::First)` so that the merged block starts correctly in the new table.

- **Formatting preservation**: The formatting applied to rows, cells, and the table itself is retained because the rows are moved, not recreated. Any style or direct formatting on the moved rows remains unchanged in the new table.

- **Pagination effects**: Aspose.Words recalculates pagination automatically after the table structure changes. To avoid unexpected pagination shifts, perform the split operation before any layout-dependent processing (e.g., before saving or printing).

## Related APIs

- [Table](https://reference.aspose.com/words/cpp/aspose.words.tables/table/)
- [Row](https://reference.aspose.com/words/cpp/aspose.words.tables/row/)
- [Cell](https://reference.aspose.com/words/cpp/aspose.words.tables/cell/)
- [DocumentBuilder](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/)
- [NodeCollection](https://reference.aspose.com/words/cpp/aspose.words/nodecollection/)

------ 

## FAQ

1. **Q:** How do I split a table at a specific row using Aspose.Words for C++?  
   **A:** Create a clone of the original table without its child rows (`table->Clone(false)`), insert the clone after the original, then move all rows starting from the split row to the new table using `Table::get_Rows()->RemoveAt()` and `Table::AppendChild(row)`. This preserves the original formatting while separating the rows into a new table.

2. **Q:** Will the cell formatting (widths, borders, shading) be retained after splitting?  
   **A:** Yes. Cloning the table without children copies the table's formatting, column widths, and style definitions. When you move rows to the cloned table, each row keeps its own cell formatting, so the appearance of both tables remains unchanged.

3. **Q:** Can I split a table into more than two tables?  
   **A:** Absolutely. Repeat the split process for each desired split point: clone the current table, insert the clone, and move the appropriate rows. Each iteration creates an additional independent table.

4. **Q:** What should I do if the split row is the first or last row of the table?  
   **A:** If the split row is the first row, the original table will become empty; you may remove it with `Node::Remove()`. If the split row is the last row, the new table will contain no rows, so you can skip inserting the clone or delete it after the operation.

5. **Q:** How can I split a table that is nested inside another table cell?  
   **A:** Retrieve the nested table via `Cell::GetChildNodes(NodeType::Table, true)` and apply the same cloning and row‑moving logic. Insert the new table into the same parent node (the cell) using `InsertAfter` to keep the document structure intact.

---