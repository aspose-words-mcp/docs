---
title: Using Contextual Object Member Access in Java
second_title: Aspose.Words for Java
articleTitle: Using Contextual Object Member Access
linktitle: Using Contextual Object Member Access
description: "Use contextual object member to access some objects without specifying the objects id in template expressions using Java."
type: docs
weight: 120
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/using-contextual-object-member-access/
timestamp: 2024-01-27-14-07-04
---

You can make your templates less cumbersome using the contextual object member access feature. This feature enables you to access members of some objects without specifying the objects' identifiers in template expressions. An object to which the feature can be applied is determined depending on a 
context as follows:

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

1. **Q:** How does contextual object member access differ from regular member access in template expressions?  
   **A:** Contextual access lets you omit the object identifier; the engine automatically resolves the member to the innermost iteration variable (inside a data band) or to the passed data source (outside a data band). Regular access requires you to specify the full path, such as `ds.Persons.Name`.

2. **Q:** Can I use contextual object member access to reference an outer iteration variable from within a nested loop?  
   **A:** No. Inside a data band, contextual access always resolves to the innermost iteration variable. To reach an outer variable you must use the regular object member syntax with the appropriate identifier.

3. **Q:** How can I count the number of items in a data source using contextual syntax?  
   **A:** Outside a data band, call `count()` on the collection name without a prefix, e.g., `<<[Persons.count()]>>`; the name is resolved against the passed data source. Inside a `foreach` over `Persons`, contextual access resolves to the current item, so use the full name there instead, e.g., `<<[ds.Persons.count()]>>`.

4. **Q:** What happens if I try to use contextual member access outside a data band body?  
   **A:** The engine resolves the member to the passed data source object. If no data source is supplied, the expression will fail with a “member not found” error. In such cases, specify the full data source identifier.

5. **Q:** Is it possible to mix contextual and regular member access in the same template?  
   **A:** Yes. You can use contextual syntax where it is allowed and fall back to regular syntax for cases that require explicit object references, such as accessing outer loop variables or when you need clarity in complex templates.