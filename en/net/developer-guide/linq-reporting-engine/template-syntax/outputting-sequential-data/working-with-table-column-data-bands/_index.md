---
title: Working with Table-Column Data Bands in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Table-Column Data Bands
linktitle: Working with Table-Column Data Bands
description: "Output a sequence of table-column data when building a report in C#."
type: docs
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-table-column-data-bands/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with table-column data bands in templates.

{{% /alert %}}

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

**Note** – The `horz` switch instructs the engine to affect table columns rather than rows.

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

<img src="graph-10.jpeg" alt="table-column-data-bands-aspose-words-net" style="width:500px"/>

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
			<td>&lt;&lt;[ds.Sales.Sum(s => s.Quantity)]>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| **Good**          | **Drinking Water** | **Drinking Water** | **Mineral Water** | **Mineral Water** | **Total:** |
| ----------------- | ------------------ | ------------------ | ----------------- | ----------------- | ---------- |
| **Pack**          | **1.5 L**          | **500 ml**         | **1.5 L**         | **500 ml**        |            |
| **Sold Quantity** | **12**             | **27**             | **5**             | **13**            | **57**     |

To grow a document table horizontally by filling it with master‑detail data, you can use nested table‑column data bands like in the following template.

<table class="outputting-sequential-data">
	<tbody>
		<tr>
			<td><strong>Good/Pack</strong></td>
			<td>&lt;&lt;foreach [g in ds.Goods] -horz>>&lt;&lt;[g.Name]>></td>
			<td>&lt;&lt;foreach [s in g.Sales] -horz>>&lt;&lt;[s.Packs.Name]>></td>
      <td><strong>Total:</strong>
		</tr>
		<tr>
			<td><strong>Sold Quantity</strong></td>
			<td>&lt;&lt;[g.Sales.Sum(s => s.Quantity)]>></td>
      <td>&lt;&lt;[s.Quantity]>>&lt;&lt;/foreach>>&lt;&lt;/foreach>></td>
      <td>&lt;&lt;[ds.Sales.Sum(s => s.Quantity)]>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

| **Good / Pack**   | **Drinking Water** | **1.5 L** | **500 ml** | **Mineral Water** | **1.5 L** | **500 ml** | **Total:** |
| ----------------- | ------------------ | --------- | ---------- | ----------------- | --------- | ---------- | ---------- |
| **Sold Quantity** | **39**             | **12**    | **27**     | **18**            | **5**     | **13**     | **57**     |

You can normally use common data bands nested to table‑column data bands as well like in the following template.

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

| **Good**       | **Drinking Water**         | **Mineral Water**          |
| -------------- | -------------------------- | -------------------------- |
| **Sold Packs** | **1.5 L**<br /> **500 ml** | **1.5 L**<br /> **500 ml** |

**Note** – Table‑column data bands can themselves be nested to table‑row data bands (see “Working with Cross (Pivot) Tables” for details), but not conversely: Nesting of table‑row data bands into table‑column data bands is forbidden.

{{% alert color="primary" %}}

For more examples of templates for typical scenarios involving table‑column data bands, see “Appendix C. Typical Templates”.

{{% /alert %}}

------

## FAQ

1. **Q:** How do I declare a table‑column data band in a template?  
   **A:** Use the `<<foreach … -horz>>` tag inside the cells that belong to the band. The `-horz` switch tells the engine to repeat the content horizontally across columns. Example: `<<foreach [s in ds.Sales] -horz>> <<[s.Goods.Name]>> <</foreach>>`.

2. **Q:** Can I nest table‑column data bands inside each other?  
   **A:** Yes. You can place a `<<foreach … -horz>>` block inside another `<<foreach … -horz>>` block to create multi‑level horizontal repetition, such as iterating goods and then packs for each good.

3. **Q:** Is it possible to nest a table‑row data band inside a table‑column data band?  
   **A:** No. Table‑column data bands may contain other column bands or regular data bands, but a table‑row data band cannot be placed inside a column band. Attempting this will cause the engine to ignore the row band.

4. **Q:** What does the `-horz` switch change in the `foreach` tag?  
   **A:** The `-horz` switch changes the iteration direction from the default vertical (row‑wise) to horizontal (column‑wise). The engine expands the band across columns, creating a new column for each iteration item.

5. **Q:** How can I calculate aggregates, like a sum, within a table‑column data band?  
   **A:** Use standard LINQ expressions inside field tags. For example, `<<[ds.Sales.Sum(s => s.Quantity)]>>` will output the total quantity across all sales rows, even when the band is horizontal. The expression is evaluated in the context of the data set.