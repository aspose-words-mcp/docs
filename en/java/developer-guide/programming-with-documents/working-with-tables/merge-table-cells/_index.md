---
title: Merge Table Cells in in Java
second_title: Aspose.Words for Java
articleTitle: Merge Table Cells
linktitle: Merge Table Cells
description: "How to merge table cells in Java. Check if cells in a table are merged using Java."
type: docs
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-merged-cells/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with merged table cells.

{{% /alert %}}

Sometimes certain rows in a table require a heading or large blocks of text that take up the full width of the table. For proper design of the table, the user can merge several table cells into one. Aspose.Words supports merged cells when working with all input formats, including importing HTML content.

## How to Merge Table Cells

In Aspose.Words, merged cells are represented by the following properties of the [CellFormat](https://reference.aspose.com/words/java/com.aspose.words/cellformat/) class:

- [getHorizontalMerge()](https://reference.aspose.com/words/java/com.aspose.words/cellformat/#getHorizontalMerge) which describes if the cell is a part of a horizontal merge of cells
- [getVerticalMerge()](https://reference.aspose.com/words/java/com.aspose.words/cellformat/#getVerticalMerge) which describes if the cell is a part of a vertical merge of cells

The values of these properties determine the merge behavior of cells:

- The first cell in a sequence of merged cells will have [CellMerge.FIRST](https://reference.aspose.com/words/java/com.aspose.words/cellmerge/#FIRST)
- Any subsequently merged cells will have [CellMerge.PREVIOUS](https://reference.aspose.com/words/java/com.aspose.words/cellmerge/#PREVIOUS)
- A cell that is not merged will have [CellMerge.NONE](https://reference.aspose.com/words/java/com.aspose.words/cellmerge/#NONE)

{{% alert color="primary" %}}

Sometimes, when loading existing document cells in a table, they will appear merged. However, it can actually be one long cell – sometimes Microsoft Word exports merged cells this way. This can be confusing when attempting to work with individual cells, but there doesn't seem to be any particular pattern as to when this happens.

{{% /alert %}}

## Check if Cell is Merged

To check if a cell is part of a sequence of merged cells, we simply check the **getHorizontalMerge()** and **getVerticalMerge()** properties.

The following code example shows how to print the horizontal and vertical cell merge type:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "check-cells-merged.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Table%20with%20merged%20cells.docx).

{{% /alert %}}

## Merge Table Cells When Using DocumentBuilder

To merge cells in a table created with the [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/), you need to set the appropriate merge type for each cell where the merge is expected – first **CellMerge.FIRST** and then **CellMerge.PREVIOUS**.

Also, you must remember to clear the merge setting for those cells where no merge is required – this can be done by setting the first non-merge cell to **CellMerge.NONE**. If this is not done, all cells in the table will be merged.

The following code example shows how to create a table with two rows where the cells in the first row are merged horizontally:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "horizontal-merge.java" >}}

The following code example shows how to create a two-column table where the cells in the first column are vertically merged:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "vertical-merge.java" >}}

## Merge Table Cells in Other Cases

In other situations where the **DocumentBuilder** is not used, such as in an existing table, merging cells in the previous way may not be as easy. Instead, we can wrap the basic operations involved in applying merge properties to cells in a method that makes the task much easier. This method is similar to the Merge automation method, which is called to merge a range of cells in a table.

The code below will merge the table cells in the specified range, starting at the given cell and ending at the end cell. In this case, the range can span multiple rows or columns:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "merge-cells.java" >}}

The following code example shows how to merge a range of cells between two specified cells:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "merge-cell-range.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Table%20with%20merged%20cells.docx).

{{% /alert %}}

## Vertical and Horizontal Merged Cells in HTML Table

As we have said in previous articles, a table in Microsoft Word is a set of independent rows. Each row has a set of cells that are independent of the cells of other rows. Thus, in the Microsoft Word table there is no such object as a “column”, and “1st column” is something like “the set of the 1st cells of each row in the table”. This allows users to have a table in which, for example, the 1st row consists of two cells – 2cm and 1cm, and the 2nd row consists of two different cells – 1cm and 2cm wide. And Aspose.Words supports this concept of tables.

A table in HTML has a essentially different structure: each row has the same number of cells and (it is important for the task) each cell has the width of the corresponding column, the same for all cells in one column. So if **getHorizontalMerge()** and **getVerticalMerge()** return an incorrect value, use the following code example:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "print-horizontal-and-vertical-merged.java" >}}

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "horizontal-and-vertical-merge-helper-classes.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Table%20with%20merged%20cells.docx).

{{% /alert %}}

## Convert to Horizontally Merged Cells

Sometimes it is not possible to detect which cells are merged because some newer versions of Microsoft Word no longer use the merge flags when cells are merged horizontally. But for situations where cells are merged into a cell horizontally by their width using merge flags, Aspose.Words provides the `convertToHorizontallyMergedCells()` method to convert cells. This method simply transforms the table and adds new cells as needed.

The following code example shows the above method in operation:

{{< gist "aspose-words-gists" "4fe6fda3615c0c441401e2131533d93b" "convert-to-horizontally-merged-cells.java" >}}

## FAQ

1. **Q:** How do I merge cells horizontally using `DocumentBuilder`?  
   **A:** Create the table with `DocumentBuilder`, then for the first cell in the merge call `cell.getCellFormat().setHorizontalMerge(CellMerge.FIRST)`. For each subsequent cell that should be merged, set `CellMerge.PREVIOUS`. After the merged range, set the next cell's horizontal merge to `CellMerge.NONE` to stop the merge.

2. **Q:** How can I merge cells vertically?  
   **A:** The process is analogous to horizontal merging but uses `setVerticalMerge`. Set `CellMerge.FIRST` on the top‑most cell of the column, `CellMerge.PREVIOUS` on the cells below, and reset to `CellMerge.NONE` after the merged block.

3. **Q:** How can I determine whether a particular cell is part of a merged group?  
   **A:** Inspect the cell's format: `cell.getCellFormat().getHorizontalMerge()` and `cell.getCellFormat().getVerticalMerge()`. If either returns `CellMerge.FIRST` or `CellMerge.PREVIOUS`, the cell participates in a merge; `CellMerge.NONE` means it is not merged.

4. **Q:** Is there a way to merge a rectangular range of cells programmatically?  
   **A:** Yes. Loop through the cells in the desired range and set the appropriate horizontal and vertical merge values. Typically you set `CellMerge.FIRST` on the top‑left cell, `CellMerge.PREVIOUS` on the remaining cells in the first row for horizontal merges, and similarly use `setVerticalMerge` for rows. The `mergeCells(Cell startCell, Cell endCell)` method in the code example above wraps this logic; it is sample code, not part of the API.

5. **Q:** My table appears to have merged cells, but the merge flags are missing. How can I fix this?  
   **A:** Use the `Table.convertToHorizontallyMergedCells()` method. It analyses the visual widths of cells, inserts missing cells where needed, and sets the correct `getHorizontalMerge()` flags so that the merged state is represented accurately in the document model. This resolves issues where Word exported a merged cell as a single wide cell without flags.