---
title: Using Contextual Object Member Access in C#
second_title: Aspose.Words for .NET
articleTitle: Using Contextual Object Member Access
linktitle: Using Contextual Object Member Access
description: "Use contextual object member to access some objects without specifying the objects id in template expressions using C#."
type: docs
weight: 120
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/using-contextual-object-member-access/
aliases: [/net/template-syntax/#using-contextual-object-member-access]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how contextual member access works in templates when resolving object properties.

{{% /alert %}}

You can make your templates less cumbersome using the contextual object member access feature. This feature enables you to access members of some objects without specifying the objects' identifiers in template expressions. An object to which the feature can be applied is determined depending on a context as follows:

- Inside a data band body, the object is resolved to the innermost iteration variable.
- Outside a data band body, the object is resolved to a passed data source.

Obviously, inside a data band body, you can not use the feature to access members of an outer iteration variable or a passed data source object. With the exception of this restriction, you can use both contextual and common object member access syntaxes interchangeably depending on your needs and preferences.

Consider the following example. Given that `ds` is a `DataSet` instance containing a `DataTable` object named “Persons” that has fields named “Name” and “Age”, you can use the following template to list the contents of the table.

<table class="ct">
	<tbody>
		<tr>
			<td><strong>No.</strong></td>
			<td><strong>Name</strong></td>
			<td><strong>Age</strong></td>
		</tr>
		<tr>
			<td>&lt;&lt;foreach [p 
    in ds.Persons]>>&lt;&lt;[
  p.numberOf()]>></td>
			<td>&lt;&lt;[p.Name]>></td>
			<td>&lt;&lt;[p.Age]>>&lt;&lt;/foreach>></td>
		</tr>
		<tr>
			<td colspan="3">Count: &lt;&lt;[ds.Persons.count()]>></td>
		</tr>
	</tbody>
</table>

Alternatively, you can use the following template involving the contextual object member access syntax to get the same results.

<table class="iksweb">
	<tbody>
		<tr>
			<td><strong>No.</strong></td>
			<td><strong>Name</strong></td>
			<td><strong>Age</strong></td>
		</tr>
		<tr>
			<td>&lt;&lt;foreach [
    in Persons]>>&lt;&lt;[
  numberOf()]>></td>
			<td>&lt;&lt;[Name]>></td>
			<td>&lt;&lt;[Age]>>&lt;&lt;/foreach>></td>
		</tr>
		<tr>
			<td colspan="3">Count: &lt;&lt;[Persons.count()]>></td>
		</tr>
	</tbody>
</table>

------

## FAQ
1. **Q:** How can I use contextual object member access inside an IF field?  
   **A:** Place an `if` tag around the content and use contextual access in its condition, e.g., `<<if [Age > 30]>>Adult<</if>>`. The member `Age` is resolved to the current iteration variable, so the condition works without specifying the variable name.

2. **Q:** What happens if I try to access a member of an outer iteration variable using contextual access?  
   **A:** Contextual access only resolves to the innermost iteration variable. Attempting to reference an outer variable will result in an error or an empty value. Use the full object identifier (e.g., `outerVar.Property`) for outer scopes.

3. **Q:** Is contextual object member access available in other language APIs such as Java or Python?  
   **A:** Yes, the same template syntax is supported across all Aspose.Words language bindings, including Java and Python. The feature is part of the template engine, not the programming language, so the same templates can be used regardless of the host language.