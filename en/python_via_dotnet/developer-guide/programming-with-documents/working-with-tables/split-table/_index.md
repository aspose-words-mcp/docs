---
title: Split Table in Python
second_title: Aspose.Words for Python
articleTitle: Split Table
linktitle: Split Table
description: "Split table in Python. How to split one table into two separate tables Python."
type: docs
weight: 100
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/split-table/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains how to split an existing table into two separate tables in Aspose.Words for Python by cloning the original table (without its rows) and moving rows from a specified split point to the new table.

{{% /alert %}}

A table, represented in the Aspose.Words Document Object Model, is made up of independent rows and cells, making it easy to split a table.

To manipulate a table to split it into two tables, we just need to move some of the rows from the original table to the new one. To do this, we need to pick the row by which we want to split the table.

We can create two tables from the original table by following these simple steps:

1. Create a clone of the table without cloning the children to keep the moved rows and insert them after the original table
2. Starting at the specified row, move all subsequent rows to this second table

The following code example shows how to split a table into two tables on a specific row:

{{< gist "aspose-words-gists" "d31be78b25b463dd4eb31c85c60fc549" "split-table.py" >}}

## Limitations and Considerations

- **Merged cells**: Aspose.Words does not change merge flags when rows are moved. If a vertically merged cell spans the split row, the first moved cell keeps `CellMerge.PREVIOUS`; set its `cell_format.vertical_merge` to `CellMerge.FIRST` so that the merged block starts correctly in the new table.

- **Formatting preservation**: The formatting applied to rows, cells, and the table itself is retained because the rows are moved, not recreated. Any style or direct formatting on the moved rows remains unchanged in the new table.

- **Pagination effects**: Aspose.Words recalculates pagination automatically after the table structure changes. To avoid unexpected pagination shifts, perform the split operation before any layout-dependent processing (e.g., before saving or printing).

## Related APIs

- [Table](https://reference.aspose.com/words/python-net/aspose.words.tables/table/)
- [Row](https://reference.aspose.com/words/python-net/aspose.words.tables/row/)
- [Cell](https://reference.aspose.com/words/python-net/aspose.words.tables/cell/)
- [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/)
- [NodeCollection](https://reference.aspose.com/words/python-net/aspose.words/nodecollection/) 

## FAQ

1. **Q:** How can I split a table into two tables at a specific row?  
   **A:** Create an empty clone of the original table using `Table.clone(False)`, insert the clone after the original table, then move each row starting from the split row to the new table with `original_table.rows.remove(row)` and `new_table.rows.add(row)`. This preserves the original table's formatting while separating the rows.

2. **Q:** Does cloning a table copy its formatting?  
   **A:** Yes. When you clone a table with `deep=False`, the table's properties (borders, shading, width, etc.) are copied, but the child rows and cells are not. The new empty table therefore retains the same visual style as the source table.

3. **Q:** Can I split a table that contains merged cells?  
   **A:** Merged cells that span rows being moved will be split automatically, which may break the original merge. After splitting, you may need to re‑apply merging on the affected cells in each resulting table.

4. **Q:** How do I split a table into more than two parts?  
   **A:** Perform the split operation repeatedly. For each additional part, create another empty clone, insert it after the previous table, and move the required rows into it. The same `clone` and `move rows` logic applies each time.

5. **Q:** Will splitting a table affect the surrounding document layout?  
   **A:** No. Because the new table is inserted immediately after the original, the flow of paragraphs, headers, and footers remains unchanged. Only the rows are redistributed between the two tables.