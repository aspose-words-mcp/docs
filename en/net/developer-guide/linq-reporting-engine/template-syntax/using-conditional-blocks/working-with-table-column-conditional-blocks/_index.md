---
title: Working with Table-Column Conditional Blocks
second_title: Aspose.Words for .NET
articleTitle: Working with Table-Column Conditional Blocks
linktitle: Working with Table-Column Conditional Blocks
description: "Use table-column conditional blocks within single document table to represent the same data depending on a condition using C#."
type: docs
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-table-column-conditional-blocks/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with table-column conditional blocks in templates.

{{% /alert %}}

A table-column conditional block represents a conditional block, which body occupies a rectangular area of cells of a single document table. The body of such a block (as well as the body of its every template option) starts at the beginning of the top-left cell of a corresponding area and ends at the end of its bottom-right cell. Typically, this area consists of one or several table columns as follows.

**Note** – Table cells occupied by different template options in the following templates are highlighted with different colors.

<table class="conditional block">
	<tbody>
		<tr>
      <td>...</td>
      <td style="background-color: #e2fac0">&lt;&lt;if ... -horz>> ...</td>
      <td style="background-color: #fff9ba">&lt;&lt;elseif ...>> ...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #caeefc">&lt;&lt;else>> ...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td>...</td>
		</tr>
    <tr>
      <td>...</td>
      <td style="background-color: #e2fac0">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td>...</td>
		</tr>
    <tr>
      <td>...</td>
      <td style="background-color: #e2fac0">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...&lt;&lt;/if>></td>
      <td>...</td>
		</tr>
	</tbody>
</table>

**Note** – The `horz` switch instructs the engine to affect table columns rather than rows.

However, unlike table-row conditional blocks able to capture only whole rows, table-column conditional blocks can occupy columns even partially as shown in the following template snippet.

<table class="conditional block">
	<tbody>
		<tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
    <tr>
      <td>...</td>
      <td style="background-color: #e2fac0">&lt;&lt;if ... -horz>> ...</td>
      <td style="background-color: #fff9ba">&lt;&lt;elseif ...>> ...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #caeefc">&lt;&lt;else>> ...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td>...</td>
		</tr>
    <tr>
      <td>...</td>
      <td style="background-color: #e2fac0">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td>...</td>
		</tr>
    <tr>
      <td>...</td>
      <td style="background-color: #e2fac0">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #fff9ba">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...</td>
      <td style="background-color: #caeefc">...&lt;&lt;/if>></td>
      <td>...</td>
		</tr>
    <tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
		</tr>
	</tbody>
</table>

Let us consider typical use cases for table-column conditional blocks at first defining `showRepresentatives`, a `Boolean` value, and `person` and `persons`, an instance and an enumeration of instances of the `Person` class respectively, where the `Person` class is defined as follows.

{{< highlight csharp >}}
public class Person

{
	public String Name { get { ... } }

	public int Age { get { ... } }
	
	public String Representative { get { ... } }
	
	...
}
{{< /highlight >}}

The most typical scenario for table-column conditional blocks is showing or hiding a table column depending on a condition. You can do it using a template as follows.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td><strong>Age</strong></td>
      <td>&lt;&lt;if [showRepresentatives] -horz>>Representative</td>
    </tr>
    <tr>
      <td>&lt;&lt;[person.Name]>></td>
      <td>&lt;&lt;[person.Age]>></td>
      <td>&lt;&lt;[person.Representative]>>&lt;&lt;/if>>
</td>
    </tr>
	</tbody>
</table>

When `showRepresentatives` is set to `true`, the engine produces a report as follows.

| **Name**       | **Age** | **Representative**    |
| -------------- | ------- | --------------------- |
| **Evan Edger** | **47**  | **Terrence Randolph** |

When `showRepresentatives` is set to `false`, the engine produces a report as follows.

| **Name**       | **Age** |
| -------------- | ------- |
| **Evan Edger** | **47**  |

For a table being built using a table-row data band, you can also show or hide a table column depending on a condition like in the following template.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td><strong>Age</strong></td>
      <td>&lt;&lt;if [showRepresentatives] -horz>>Representative&lt;&lt;/if>></td>
    </tr>
    <tr>
      <td>&lt;&lt;foreach [p in persons]>>&lt;&lt;[p.Name]>></td>
      <td>&lt;&lt;[p.Age]>></td>
      <td>&lt;&lt;if [showRepresentatives] -horz>>&lt;&lt;[p.Representative]>>&lt;&lt;/if>>&lt;&lt;/foreach>>
</td>
    </tr>
	</tbody>
</table>

**Note** – Table-row and table-column regions cannot cross, that is why two table-column conditional blocks with the same condition are required in this case.

When `showRepresentatives` is set to `true`, the engine produces a report as follows.

| **Name**        | **Age** | **Representative**    |
| --------------- | ------- | --------------------- |
| **Evan Edger**  | **47**  | **Terrence Randolph** |
| **Kate Abrams** | **35**  |                       |

When `showRepresentatives` is set to `false`, the engine produces a report as follows.

| **Name**        | **Age** |
| --------------- | ------- |
| **Evan Edger**  | **47**  |
| **Kate Abrams** | **35**  |

Table-column conditional blocks can also be used to provide different views for a table column depending on a condition. You can use a template as follows to achieve this.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td rowspan="2" style="vertical-align: middle">&lt;&lt;if [person.Representative == “”] -horz>>&lt;&lt;[person.Name]>></td>
      <td>&lt;&lt;else>>&lt;&lt;[person.Name]>></td>
		</tr>
    <tr>
      <td><strong>Representative</strong></td>
      <td>&lt;&lt;[person.Representative]>>&lt;&lt;/if>></td>
    </tr>
	</tbody>
</table>

When a representative is present for a person, the engine produces a report as follows.

| **Name**           | **Evan Edger**        |
| ------------------ | --------------------- |
| **Representative** | **Terrence Randolph** |

When a representative is not specified for a person, the engine produces a report as follows.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td rowspan="2" style="vertical-align: middle">Kate Abrams</td>
		</tr>
    <tr>
      <td><strong>Representative</strong></td>
    </tr>
	</tbody>
</table>

You can use a similar approach to provide different views for columns of a table being built using a table-column data band. A template for this may look as follows.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td rowspan="2" style="vertical-align: middle">&lt;&lt;foreach [p in persons] -horz>>&lt;&lt;if [p.Representative == “”] -horz>>&lt;&lt;[p.Name]>></td>
      <td>&lt;&lt;else>>&lt;&lt;[p.Name]>></td>
		</tr>
    <tr>
      <td><strong>Representative</strong></td>
      <td>&lt;&lt;[p.Representative]>>&lt;&lt;/if>>&lt;&lt;/foreach>></td>
    </tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td>Evan Edger</td>
      <td rowspan="2" style="vertical-align: middle">Kate Abrams</td>
		</tr>
    <tr>
      <td><strong>Representative</strong></td>
      <td>Terrence Randolph</td>
    </tr>
	</tbody>
</table>

**Note** – You can use common conditional blocks within table-column data bands as well.

In addition, table-column conditional blocks can contain table-column data bands. This is useful, for example, for providing alternate content for an empty table-column data band as shown in the following template.

<table class="conditional block">
	<tbody>
    <tr>
      <td><strong>Name</strong></td>
      <td rowspan="2" style="vertical-align: middle">&lt;&lt;if [!persons.Any()] -horz>>No data</td>
      <td>&lt;&lt;else>>&lt;&lt;foreach [p in persons] -horz>>&lt;&lt;[p.Name]>></td>
		</tr>
    <tr>
      <td><strong>Representative</strong></td>
      <td>&lt;&lt;[p.Representative]>>&lt;&lt;/foreach>>&lt;&lt;/if>></td>
    </tr>
	</tbody>
</table>

When the enumeration of persons is not empty, the engine produces a report as follows.

| **Name**           | **Evan Edger**        | **Kate Abrams** |
| ------------------ | --------------------- | --------------- |
| **Representative** | **Terrence Randolph** |                 |

When there is no person at all, the engine produces a report as follows.

<table class="conditional block">
	<tbody>
    <tr>
      <td>Name</td>
      <td rowspan="2" style="vertical-align: middle">No data</td>
		</tr>
    <tr>
      <td>Representative</td>
    </tr>
	</tbody>
</table>

**Note** – Table‑column conditional blocks can themselves be nested to table‑row data bands and conditional blocks, but not conversely: Nesting of table‑row data bands and conditional blocks into table‑column conditional blocks is forbidden.

## Limitations and Considerations

Limitations and considerations for table-column conditional blocks include:

- **Nesting restrictions**: Table-column conditional blocks can contain table-column data bands, but they cannot contain table-row data bands or table-row conditional blocks. Attempting to nest table-row constructs inside a table-column conditional block will raise a template-validation error.

- **Horizontal switch requirement**: The `-horz` switch is required for column-level conditional logic. Without it, the conditional block operates on rows instead of columns, so columns will not be hidden or shown as intended.

- **Field validation**: The engine throws an `InvalidOperationException` saying that it cannot get the value of the member when the condition expression references a property that does not exist in the data source. Ensure property names match exactly (case-sensitive) the members of the object supplied to the reporting engine.

- **Empty collection handling**: When using table-column data bands with collections, provide alternate content for empty collections using conditional blocks that check with the `Any()` method, e.g., `<<if [!persons.Any()] -horz>>No data<<else>>...<</if>>`.

Note that table-column conditional blocks themselves can be nested inside table-row data bands and conditional blocks.

------

## FAQ

1. **Q:** How do I enable the `-horz` switch to make a conditional block affect columns instead of rows?  
   **A:** Add the `-horz` flag directly after the condition in the opening tag, e.g. `<<if [showColumn] -horz>>`. This tells the engine to apply the block to the column range defined by the surrounding cells.

2. **Q:** Can I nest a table‑row conditional block inside a table‑column conditional block?  
   **A:** No. Table‑column conditional blocks may contain table‑column data bands, but nesting table‑row data bands or row‑level conditional blocks inside a column block is prohibited. Attempting this will raise a template‑validation error.

3. **Q:** What happens if the condition expression references a property that does not exist in the data source?  
   **A:** The engine throws an `InvalidOperationException` saying that it cannot get the value of the member. Ensure that the property name matches exactly (case‑sensitive) the members of the object supplied to the reporting engine.

4. **Q:** How can I provide an alternate view when a collection used in a column data band is empty?  
   **A:** Use an `if` block that checks the collection with the `Any()` method, e.g. `<<if [!persons.Any()] -horz>>No data<<else>>...<</if>>`. Place the alternate content inside the `if` branch.

5. **Q:** Is it possible to hide a column conditionally without using the `-horz` switch?  
   **A:** The `-horz` switch is required for column‑level conditional logic. Without it, the `if` block operates on rows, so the column will not be hidden. Use `<<if [condition] -horz>>` to hide/show the column.