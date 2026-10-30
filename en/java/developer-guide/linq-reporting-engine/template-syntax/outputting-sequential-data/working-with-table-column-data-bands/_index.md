---
title: Working with Table-Column Data Bands in Java
second_title: Aspose.Words for Java
articleTitle: Working with Table-Column Data Bands
linktitle: Working with Table-Column Data Bands
description: "Output a sequence of table-column data when building a report in Java."
type: docs
weight: 23
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-table-column-data-bands/
timestamp: 2024-01-27-14-07-04
---

You can build tables growing horizontally rather than vertically by using table-column data bands.

A table-column data band represents a data band, which body occupies a rectangular area of cells of a single document table. The body of such a band starts at the beginning of the top-left cell of a corresponding area and ends at the end of its bottom-right cell. Typically, this area consists of one or several table columns as follows.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td>...</td>
      <td>&lt;&lt;foreach ... -horz>> ...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
      <td>... &lt;&lt;/foreach>></td>
      <td>...</td>
		</tr>
	</tbody>
</table>

**Note** – The horz switch instructs the engine to affect table columns rather than rows.

However, unlike table-row data bands able to capture only whole rows, table-column data bands can occupy columns even partially as shown in the following template snippet.

<table class="outputting-sequential-data">
	<tbody>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
		<tr>
			<td>...</td>
      <td>&lt;&lt;foreach ... -horz>> ...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
      <td>... &lt;&lt;/foreach>></td>
      <td>...</td>
		</tr>
    <tr>
			<td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
	</tbody>
</table>

Let us consider typical use cases for table-column data bands at first defining `ds`, a `DataSet` instance containing `DataTable` and `DataRelation` objects according to the following data model.

<img src="working-with-table-column-data-bands.jpeg" alt="table-column-data-bands-aspose-words-java" style="width:500px"/>

The most common scenario for a table-column data band is building of a document table that represents a list of items side by side. You can use a template like the following one to achieve this.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td><strong>Good</strong></td>
			<td>&lt;&lt;foreach [s in ds.Sales] -horz>>&lt;&lt;[s.Goods.Name]>></td>
			<td rowspan="2" style="vertical-align: middle"><strong>Total:</strong></td>
		</tr>
		<tr>
			<td><strong>Pack</strong></td>
			<td>&lt;&lt;[s.Packs.Name]>></td>
		</tr>
    <tr>
			<td><strong>Sold Quantity</strong></td>
      <td>&lt;&lt;[s.Quantity]>>&lt;&lt;/foreach>></td>
			<td>&lt;&lt;[ds.Sales.sum(s => s.Quantity)]>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| **Good**          | **Drinking Water** | **Drinking Water** | **Mineral Water** | **Mineral Water** | **Total:** |
| ----------------- | ------------------ | ------------------ | ----------------- | ----------------- | ---------- |
| **Pack**          | **1.5 L**          | **500 ml**         | **1.5 L**         | **500 ml**        |            |
| **Sold Quantity** | **12**             | **27**             | **5**             | **13**            | **57**     |

To grow a document table horizontally by filling it with master-detail data, you can use nested table-column data bands like in the following template.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td><strong>Good</strong></td>
			<td>&lt;&lt;foreach [g in ds.Goods] -horz>>&lt;&lt;[g.Name]>></td>
      <td>&lt;&lt;foreach [s in g.Sales]>>&lt;&lt;[s.Packs.Name]>></td>
      <td><strong>Total:</strong></td>
		</tr>
		<tr>
			<td><strong>Sold Packs</strong></td>
			<td>&lt;&lt;[g.Sales.sum(s => s.Quantity)]>></td>
      <td>&lt;&lt;[s.Quantity]>>&lt;&lt;/foreach>>&lt;&lt;/foreach>></td>
      <td>&lt;&lt;[ds.Sales.sum(s => s.Quantity)]>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| **Good / Pack**   | **Drinking Water** | **1.5 L** | **500 ml** | **Mineral Water** | **1.5 L** | **500 ml** | **Total:** |
| ----------------- | ------------------ | --------- | ---------- | ----------------- | --------- | ---------- | ---------- |
| **Sold Quantity** | **39**             | **12**    | **27**     | **18**            | **5**     | **13**     | **57**     |

You can normally use common data bands nested to table-column data bands as well like in the following template.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td><strong>Good</strong></td>
			<td>&lt;&lt;foreach [g in ds.Goods] -horz>>&lt;&lt;[g.Name]>></td>
		</tr>
		<tr>
			<td><strong>Sold Packs</strong></td>
			<td>&lt;&lt;foreach [s in g.Sales]>>&lt;&lt;[s.Packs.Name]>> &lt;&lt;/foreach>>&lt;&lt;/foreach>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| **Good**       | **Drinking Water**   | **Mineral Water**    |
| -------------- | -------------------- | -------------------- |
| **Sold Packs** | **1.5 L** **500 ml** | **1.5 L** **500 ml** |

**Note** – Table‑column data bands can themselves be nested to table‑row data bands (see “Working with Cross (Pivot) Tables” for details), but not conversely: Nesting of table‑row data bands into table‑column data bands is forbidden.

For more examples of templates for typical scenarios involving table‑column data bands, see “Appendix C. Typical Templates”.

------ 

## FAQ

1. **Q:** How do I enable the horizontal (column‑wise) mode for a `foreach` tag?  
   **A:** Add the `-horz` switch to the `foreach` tag, e.g. `<<foreach [item in ds.Items] -horz>>`. This tells the LINQ Reporting Engine to repeat the band across table columns instead of rows.

2. **Q:** Can I nest table‑column data bands inside each other?  
   **A:** Yes. You can place a `foreach` with `-horz` inside another `foreach` with `-horz`. The inner band will repeat for each column generated by the outer band, allowing multi‑level horizontal layouts.

3. **Q:** Is it possible to mix table‑column and table‑row data bands in the same table?  
   **A:** You can nest a table‑column data band inside a table‑row data band (as in cross tables), but you cannot nest a table‑row band inside a column band. Use a row band for vertical repetition and a column band for horizontal repetition as needed.

4. **Q:** How do I calculate a sum of a numeric field inside a table‑column data band?  
   **A:** Use the LINQ `sum` extension inside a tag, for example `<<[ds.Sales.sum(s => s.Quantity)]>>`. The expression is evaluated against the data source and the result is inserted into the document.

5. **Q:** I get “Tag end is unexpected” when closing a nested `foreach` with `-horz`. What is wrong?  
   **A:** Ensure that each opening tag has a matching closing tag and that the closing tag does not contain extra characters. For a nested column band, the correct syntax is `<<foreach [s in ds.Sales] -horz>> … << /foreach>>`. Remove any stray `>` or missing spaces between `<<` and `/foreach>>`.