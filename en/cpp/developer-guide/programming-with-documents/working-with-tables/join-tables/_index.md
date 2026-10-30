---
title: Join Tables in C++
second_title: Aspose.Words for C++
articleTitle: Join Tables
linktitle: Join Tables
description: "Advanced table manipulations. How to merge two tables into one C++. Join tables using C++."
type: docs
weight: 90
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/join-tables/
aliases: [/cpp/joining-and-splitting-tables/]
timestamp: 2024-01-27-14-07-04
---

A table, represented in the Aspose.Words Document Object Model, is made up of independent rows and cells, making it easy to join tables.

To manipulate a table to join with another table, we just need to move the rows from the second table to the end of the first one and remove the second table's container.

The following code example shows how to merge rows from two tables into one:

{{< gist "aspose-words-gists" "e89b24cb8b77096687e8e6567018c087" "combine-rows.h" >}}

------ 

## FAQ

1. **Q:** How can I join two tables in a Word document using Aspose.Words for C++?  
   **A:** Retrieve the first and second `Table` nodes, iterate through the rows of the second table and call `firstTable->AppendChild(row->Clone(true))` for each row. After all rows are moved, remove the second table node with `secondTable->Remove()`.

2. **Q:** Will the formatting of the original rows be preserved after joining tables?  
   **A:** Yes. When rows are cloned with `Clone(true)`, all formatting, cell widths, and styles are copied to the destination table, so the visual appearance remains unchanged.

3. **Q:** What should I do if the two tables have a different number of columns?  
   **A:** Ensure both tables have the same column count before moving rows. You can add missing cells to rows of the second table using `row->AppendChild(System::MakeObject<Cell>(doc))` so that the merged table stays well‑structured.

4. **Q:** Can I join tables that are located in headers, footers, or different sections?  
   **A:** Yes. Access the tables through their containing `HeaderFooter` or `Section` objects, perform the same row‑moving logic, and then remove the now‑empty container if needed.

5. **Q:** Is there a single API method that automatically joins tables?  
   **A:** Aspose.Words does not provide a dedicated “JoinTables” method. The recommended approach is to manually move rows as demonstrated in the code sample. This gives you full control over formatting and handling of edge cases.