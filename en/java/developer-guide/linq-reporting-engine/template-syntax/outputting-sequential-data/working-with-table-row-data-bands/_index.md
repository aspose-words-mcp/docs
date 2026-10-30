---
title: Working with Table-Row Data Bands in Java
second_title: Aspose.Words for Java
articleTitle: Working with Table-Row Data Bands
linktitle: Working with Table-Row Data Bands
description: "Output a sequence of table-row data when building a report in Java."
type: docs
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-table-row-data-bands/
timestamp: 2024-10-21-11-17-44
---

A table-row data band is a data band which body occupies single or multiple rows of a single document table. The body of such a band starts at the beginning of the first occupied row and ends at the end of the last occupied row as follows.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td> </td>
      <td> </td>
      <td> </td>
		</tr>
    <tr>
      <td>&lt;&lt;foreach ...>> ...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>... &lt;&lt;/foreach>></td>
		</tr>
    <tr>
			<td> </td>
      <td> </td>
      <td> </td>
		</tr>
	</tbody>
</table>

The following examples in this section are given using `ds`, a `DataSet` instance containing `DataTable` and `DataRelation` objects according to the following data model.

![working-with-table-row-aspose-words-java](working-with-table-row-data-bands.png)

The most common use case of a table-row data band is the building of a document table that represents a list of items. You can use a template like the following one to achieve this.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td><strong>Client</strong></td>
			<td><strong>Manager</strong></td>
			<td><strong>Contract Price</strong></td>
		</tr>
		<tr>
			<td>&lt;&lt;foreach [c in ds.Contracts]>>&lt;&lt;[c.Clients.Name]>></td>
			<td>&lt;&lt;[c.Managers.Name]>></td>
			<td>&lt;&lt;[c.Price]>>&lt;&lt;/foreach>></td>
		</tr>
    <tr>
			<td colspan="2">Total:</td>
			<td>&lt;&lt;[ds.Contracts.sum(c => c.Price)]>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| Client | Manager | Contract Price |
| :- | :- | :- |
| **A Company** | **John Smith** | **1200000** |
| **B Ltd.** | **John Smith** | **750000** |
| **C & D** | **John Smith** | **350000** |
| **E Corp.** | **Tony Anderson** | **650000** |
| **F & Partners** | **Tony Anderson** | **550000** |
| **G & Co.** | **July James** | **350000** |
| **H Group** | **July James** | **250000** |
| **I & Sons** | **July James** | **100000** |
| **J Ent.** | **July James** | **100000** |
| **Total:** |  |**4300000** |

To populate a document table with a master-detail data, you can use nested table-row data bands like in the following template.

| Manager/Client | Contract Price |
| :- | :- |
| &lt;&lt;foreach [m in ds.Managers]&gt;&gt;&lt;&lt;[m.Name]&gt;&gt; | &lt;&lt;[m.Contracts.sum(c => c.Price)]&gt;&gt; |
| &lt;&lt;foreach [c in m.Contracts]&gt;&gt;  &lt;&lt;[c.Clients.Name]&gt;&gt; | &lt;&lt;[c.Price]&gt;&gt;&lt;&lt;/foreach&gt;&gt;&lt;&lt;/foreach&gt;&gt; |
| **Total:** | &lt;&lt;[ds.Contracts.sum(c =>c.Price)]&gt;&gt; |

In this case, the engine produces a report as follows.

| Manager/Client | Contract Price |
| :- | :- |
| **John Smith** | **2300000** |
| **A Company** | **1200000** |
| **B Ltd.** | **750000** |
| **C & D** | **350000** |
| **Tony Anderson** | **1200000** |
| **E Corp.** | **650000** |
| **F & Partners** | **550000** |
| **July James** | **800000** |
| **G & Co.** | **350000** |
| **H Group** | **250000** |
| **I & Sons** | **100000** |
| **J Ent.** | **100000** |
| **Total:** | **4300000** |

You can normally use common data bands nested to table-row data bands as well like in the following template.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td><strong>Manager</strong></td>
			<td><strong>Client</strong></td>
		</tr>
		<tr>
			<td>&lt;&lt;foreach [m in ds.Managers]>>&lt;&lt;[m.Name]>></td>
			<td>&lt;&lt;foreach [c in m.Contracts]>>&lt;&lt;[c.Clients.Name]>>&lt;&lt;/foreach>>&lt;&lt;/foreach>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| Manager | Clients |
| :- | :- |
| **John Smith** | <p>A Company</p><p>B Ltd.</p><p>C & D</p><p></p> |
| **Tony Anderson** | <p>E Corp.</p><p>F & Partners</p><p></p> |
| **July James** | <p>G & Co.</p><p>H Group</p><p>I & Sons</p><p>J Ent.</p><p></p> |

**Note** – Table-column data bands can also be nested to table-row data bands (see “Working with Cross (Pivot) Tables” for details), but not conversely: Nesting of table-row data bands into table-column data bands is forbidden.

A special case is a data band inside a single-column table row. In such a case, if you put opening and closing `foreach` tags in the same cell, the engine treats a data band formed by these tags as a common one rather than a table-row one by default. The following template illustrates such a scenario.

| Managers |
| :- |
| &lt;&lt;foreach [m in ds.Managers]&gt;&gt;&lt;&lt;[m.Name]&gt;&gt;  &lt;&lt;/foreach&gt;&gt; |

In this case, the engine produces a report as follows.

| Managers |
| :- |
| **John Smith  Tony Anderson  July James**  |

However, if needed, you can override this behavior making the engine to treat such a data band as a table-row one by specifying a `greedy` switch like in the following template.

| Managers |
| :- |
| &lt;&lt;foreach [m in ds.Managers]&gt;&gt;&lt;&lt;[m.Name]&gt;&gt;&lt;&lt;/foreach -greedy&gt;&gt; |

In this case, the engine produces a report as follows.

| Managers |
| :- |
| **John Smith** |
| **Tony Anderson** |
| **July James** |

For more examples of templates for typical scenarios involving table‑row data bands, see “Appendix C. Typical Templates”.

------ 

## FAQ

1. **Q:** How can I force a data band that has its opening and closing `foreach` tags in the same cell to be treated as a table‑row data band?  
   **A:** Add the `-greedy` switch to the closing tag. Example: `<<foreach [m in ds.Managers]>>...<< /foreach -greedy>>`. The greedy switch tells the engine to treat the band as a table‑row band even when the tags are in a single cell.

2. **Q:** Is it possible to nest common (row‑independent) data bands inside a table‑row data band?  
   **A:** Yes. You can place any common data band (e.g., a `foreach` that outputs a list of values) inside the body of a table‑row data band. The outer table‑row band controls the rows, while the inner common band repeats its content within a single cell.

3. **Q:** How do I calculate a sum of a numeric column inside a table‑row data band?  
   **A:** Use a LINQ expression inside a tag, for example `<<[ds.Contracts.sum(c => c.Price)]>>`. The expression is evaluated once for the whole data set and the result is inserted into the cell.

4. **Q:** What is the correct way to create a master‑detail report using nested table‑row data bands?  
   **A:** Place an outer `foreach` that iterates over the master collection (e.g., managers) and inside its row add another `foreach` that iterates over the related detail collection (e.g., contracts). Example:  

   ```text
   <<foreach [m in ds.Managers]>> <<[m.Name]>>
   <<foreach [c in m.Contracts]>> <<[c.Clients.Name]>> <<[c.Price]>> <</foreach>>
   <</foreach>>
   ```

   This produces a row for each manager and rows for each of their contracts.

5. **Q:** Can I nest a table‑row data band inside a table‑column data band?  
   **A:** No. Nesting a table‑row data band into a table‑column data band is forbidden. A table‑row data band can contain common data bands, other table‑row data bands (for master‑detail data), and table‑column data bands.