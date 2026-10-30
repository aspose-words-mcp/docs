---
title: Working with Common Conditional Blocks in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Common Conditional Blocks
linktitle: Working with Common Conditional Blocks
description: "Use common conditional blocks within paragraphs to represent the same data depending on a condition using C#."
type: docs
weight: 10
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-common-conditional-blocks/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with common conditional blocks in templates.

{{% /alert %}}

A common conditional block is a conditional block which body starts and ends within paragraphs that belong to a single story or table cell.

If a conditional block belongs to a single paragraph, it can be used as a replacement for an expression tag that involves the ternary “`?:`” operator. For example, given that `items` is an enumeration, you can use the following template to represent the count of elements in the enumeration.

{{< highlight csharp >}}
You have chosen <<if [!items.Any()]>>
no items<<else>><<[items.Count()]>> item(s)<</if>>.
{{< /highlight >}}

**Note** – A template option of a common conditional block can be composed of multiple paragraphs if needed.

You can normally use common conditional blocks within data bands. For example, given that items is an enumeration of the strings “item1”, “item2”, and “item3”, you can use the following template to enumerate them and apply different formatting for even and odd elements.

<table class="conditional block">
	<tbody>
		<tr>
			<td>&lt;&lt;foreach [item in items]>>&lt;&lt;if [IndexOf() % 2 == 0]>>&lt;&lt;[item]>><br>
<span  style="background-color: #ffff00">&lt;&lt;else>>&lt;&lt;[item]>></span><br>
&lt;&lt;/if>>&lt;&lt;/foreach>></td>
		</tr>
	</tbody>
</table>

In this case, the engine produces a report as follows.

<table class="conditional block">
	<tbody>
		<tr>
			<td>item1<br>
<span style="background-color: #ffff00">item2</span><br>
item3</td>
		</tr>
	</tbody>
</table>

You can use data bands within common conditional blocks as well. For example, given the previous declaration of `items`, you can check whether the enumeration contains any elements before outputting their list.

{{< highlight csharp >}}
<<if [!items.Any()]>>No data.
<<else>><<foreach [item in items]>><<[item]>>
<</foreach>><</if>>
{{< /highlight >}}

------

## FAQ

1. **Q:** How can I test whether a collection is empty inside a `<<if>>` block?  
   **A:** Use the `Any()` method with a negation operator. Example: `<<if [!items.Any()]>>No items.<</if>>`. The `!` before `items.Any()` returns true when the collection has no elements.

2. **Q:** Are logical operators such as `&&` and `||` supported in the condition expression?  
   **A:** Yes. You can combine multiple boolean checks using `&&` (AND) and `||` (OR). Example: `<<if [items.Any() && total > 0]>>...<</if>>`.

3. **Q:** How do I obtain the current index of an item inside a `<<foreach>>` loop for even/odd formatting?  
   **A:** Use the `IndexOf()` function, which returns the zero‑based position of the current item. Example: `<<if [IndexOf() % 2 == 0]>>` for even rows and `<<else>>` for odd rows.

4. **Q:** Can I nest `<<if>>` blocks inside other `<<if>>` or `<<foreach>>` blocks?  
   **A:** Yes. Conditional blocks can be nested to any depth, allowing complex logic. Ensure each block is properly closed with its corresponding `<</if>>` or `<</foreach>>` tag.

5. **Q:** What happens if a condition evaluates to false and there is no `<<else>>` clause?  
   **A:** The engine simply omits the block's content; nothing is rendered for that part of the template. Provide an `<<else>>` clause only when you need alternative output.