---
title: Split Table in Java
second_title: Aspose.Words for Java
articleTitle: Split Table
linktitle: Split Table
description: "Split table in Java. How to split one table into two separate tables Java."
type: docs
weight: 100
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/split-table/
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

{{< gist "aspose-words-gists" "ff5affdcea04dcd20d1b872f9503dbfe" "split-table.java" >}}

## Limitations and Considerations

- **Merged cells**: Aspose.Words does not change merge flags when rows are moved. If a vertically merged cell spans the split row, the first moved cell keeps `CellMerge.PREVIOUS`; set its `getCellFormat().setVerticalMerge(CellMerge.FIRST)` so that the merged block starts correctly in the new table.

- **Formatting preservation**: The formatting applied to rows, cells, and the table itself is retained because the rows are moved, not recreated. Any style or direct formatting on the moved rows remains unchanged in the new table.

- **Pagination effects**: Aspose.Words recalculates pagination automatically after the table structure changes. To avoid unexpected pagination shifts, perform the split operation before any layout-dependent processing (e.g., before saving or printing).

## Related APIs


- [Table](https://reference.aspose.com/words/java/com.aspose.words/table/)
- [Row](https://reference.aspose.com/words/java/com.aspose.words/row/)
- [Cell](https://reference.aspose.com/words/java/com.aspose.words/cell/)
- [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/)
- [NodeCollection](https://reference.aspose.com/words/java/com.aspose.words/nodecollection/)

## FAQ

1. **Q:** How can I split a table at a specific row using Aspose.Words for Java?  
   **A:** Load the document, locate the target `Table` node, clone the table without its child nodes (`Table clonedTable = (Table) originalTable.deepClone(false);`), insert the cloned table after the original, then move each `Row` starting from the split row to the cloned table using `clonedTable.appendChild(row);`. This creates two independent tables.

2. **Q:** Does cloning a table also clone its rows and cells?  
   **A:** By default `deepClone(true)` copies the table together with all its rows and cells. To split a table you should use `deepClone(false)` so only the table structure is cloned; the rows are then moved manually to the new table.

3. **Q:** After splitting, how do I preserve the original table's formatting in the new table?  
   **A:** The cloned table inherits the original table's formatting (borders, shading, width, etc.) because the clone copies the table's properties. Since you move existing `Row` objects, their individual formatting is retained as well. If you need to adjust spacing, modify `Table.setAllowAutoFit(false)` or call `getRowFormat().setHeight(...)` on the rows of the new table.

4. **Q:** Can I split a table without affecting the surrounding document layout (e.g., page breaks or spacing)?  
   **A:** Yes. Insert the cloned table immediately after the original with `originalTable.getParentNode().insertAfter(clonedTable, originalTable);`. This keeps the flow of paragraphs unchanged. If a page break is required, insert a `Paragraph` between the two tables, move a `DocumentBuilder` to it, and call `builder.insertBreak(BreakType.PAGE_BREAK)`.