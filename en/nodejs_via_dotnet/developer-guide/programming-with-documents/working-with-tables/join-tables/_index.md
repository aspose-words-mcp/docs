---
title: Join Tables
second_title: Aspose.Words for Node.js via .NET
articleTitle: Join Tables
linktitle: Join Tables
description: "Join tables in a document using Node.js. How to merge two tables into one in Node.js."
type: docs
weight: 90
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/join-tables/
timestamp: 2025-07-09-10-05-05
---

A table, represented in the Aspose.Words Document Object Model, is made up of independent rows and cells, making it easy to join tables.

To manipulate a table to join with another table, we just need to move the rows from the second table to the end of the first one and remove the second table's container.

The following code example shows how to merge rows from two tables into one:

{{< gist "aspose-words-gists" "9cc6f2ce785d8c91aa932c98aeed304d" "combine-rows.js" >}}

------ 

## FAQ

1. **Q:** How can I join two tables in a Word document using Aspose.Words for Node.js?  
   **A:** Load the document, locate the first and second tables, move each row from the second table to the end of the first using `firstTable.appendChild(row);`, and finally remove the now‑empty second table with `secondTable.remove();`.

2. **Q:** Will the original formatting of rows and cells be preserved after joining tables?  
   **A:** Yes. Moving a `Row` node retains its cell formatting, paragraph styles, and borders. If column widths differ, you may need to adjust them after the join to achieve a uniform appearance.

3. **Q:** What should I do if the two tables have a different number of columns?  
   **A:** Ensure both tables have the same column count before moving rows. You can add missing cells to a row with `row.appendChild(new aw.Tables.Cell(doc));` until the column numbers match.

4. **Q:** Can I join tables that are located inside headers, footers, or different sections?  
   **A:** Absolutely. Retrieve the table node from the appropriate `HeaderFooter` or `Section` object, then apply the same row‑moving logic. The API works uniformly across the main body, headers, and footers.

5. **Q:** After moving rows, how do I clean up the empty table container?  
   **A:** Call `secondTable.remove();` on the original second table node. This deletes the empty `<Table>` element from the document tree, leaving a single combined table.