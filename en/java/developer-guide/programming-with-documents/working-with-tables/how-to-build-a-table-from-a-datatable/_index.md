---
title: How to Build a Table from a DataTable in Java
second_title: Aspose.Words for Java
articleTitle: Build a Table from a DataTable 
linktitle: Build a Table from a DataTable 
description: "Example of filling document table from external database using Java."
type: docs
weight: 130
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/how-to-build-a-table-from-a-datatable/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to build a table from a DataTable using Aspose.Words.

{{% /alert %}}

Often your application will pull data from a database and store it in the form of a **DataTable**. You can easily insert this data into your document as a new table and quickly apply formatting to the whole table.

{{% alert color="primary" %}}

Note that the preferred way of inserting data from a **DataTable** into a document table is by using [Mail Merge with Regions](/words/java/types-of-mail-merge-operations/#mail-merge-with-regions). The technique presented in this article is only suggested if you are unable to create a suitable template before hand to merge data with, in other words if you require everything to happen programmatically.

{{% /alert %}}

Using Aspose.Words, you can easily retrieve data from a database and store it as a table:

1. Create a new **DocumentBuilder** object on your **Document**.
1. Start a new table using **DocumentBuilder**.
1. If we want to insert the names of each of the columns from our **DataTable** as a header row then iterate through each data column and write the column names into a row in the table.
1. Iterate through each **DataRow** in the **DataTable**:
   1. Iterate through each object in the **DataRow**.
   1. Insert the object into the document using **DocumentBuilder**. The method used depends on the type of the object being inserted e.g **DocumentBuilder.writeln** for text and **DocumentBuilder.insertImage** for a byte array which represents an image.
   1. At the end of processing of the **DataRow** also end the row being created by the **DocumentBuilder** by using **DocumentBuilder.endRow**.
1. Once all rows from the **DataTable** have been processed finish the table by calling **DocumentBuilder.endTable**.
1. Finally we can set the desired table style using one of the appropriate table properties such as **Table.getStyleIdentifier()** to automatically apply formatting to the entire table.

The **ImportTableFromDataTable** method accepts a **DocumentBuilder** object, the **DataTable** containing the data and a flag which specifies if the column heading from the **DataTable** are included at the top of the table. This method builds a table from these parameters using the builder's current position and formatting. Provides a method to import data from the `DataTable` and insert it into a new table using the DocumentBuilder.

The following data in our **DataTable** is used in this example:

![how-to-build-a-table-from-a-datatable-aspose-words-net](how-to-build-a-table-from-a-datatable-1.png)

The following code example shows how to execute the above algorithm in Aspose.Words:

{{< gist "aspose-words-gists" "b5330afb035e842063be7ce93cefe219" "import-table-from-data-table.java" >}}

The method can then be easily called using your **DocumentBuilder** and data.

The following code example shows how to import the data from a `DataTable` and insert it into a new table in the document:

{{< gist "aspose-words-gists" "b5330afb035e842063be7ce93cefe219" "build-table-from-data-table.java" >}}

## FAQ

1. **Q:** How can I insert an image stored as a byte array into a table cell?  
   **A:** Use `DocumentBuilder.insertImage(byte[] imageBytes)` while the builder's cursor is positioned inside the desired cell. After inserting the image, call `DocumentBuilder.insertCell()` to continue with the next cell (or `endRow()` to finish the row).

2. **Q:** What is the easiest way to apply a predefined table style after the table is built?  
   **A:** Retrieve the `Table` node (the first child of the builder's current paragraph) and call `table.setStyleIdentifier(StyleIdentifier.LIGHT_LIST)` (or any other `StyleIdentifier`). The style is applied to the whole table instantly.

3. **Q:** Is there a more automatic approach than writing code for each column when populating a table from a `DataTable`?  
   **A:** Yes. Aspose.Words' **Mail Merge with Regions** can map a `DataTable` directly to a table in a template. Create a region in the template with the merge fields `TableStart:Data` and `TableEnd:Data` (`{ MERGEFIELD TableStart:Data }` … `{ MERGEFIELD TableEnd:Data }`) and call `document.getMailMerge().executeWithRegions(dataTable)`. This eliminates manual iteration.

4. **Q:** How should I handle `null` values in the `DataTable` while building the table?  
   **A:** Check each cell value before writing. If the value is `null`, write an empty string or a placeholder, e.g. `builder.writeln("")`. This prevents `NullPointerException` and keeps the table layout consistent.

5. **Q:** Can I merge cells or set column widths after the table has been created?  
   **A:** Yes. After `endTable()`, locate the `Table` node, then merge cells with `cell.getCellFormat().setHorizontalMerge(...)` or `setVerticalMerge(...)` and `CellMerge` values. Column widths can be set via `Table.getFirstRow().getCells().get(i).getCellFormat().setWidth(width)`. Adjust widths before saving the document.