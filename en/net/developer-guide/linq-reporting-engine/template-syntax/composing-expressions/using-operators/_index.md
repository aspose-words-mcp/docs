---
title: Using Operators in C#
second_title: Aspose.Words for .NET
articleTitle: Using Operators
linktitle: Using Operators
description: "Use predefined operators in template expressions when building a report in C#."
type: docs
weight: 50
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/using-operators-linq/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to use template operators supported by the LINQ Reporting Engine.

{{% /alert %}}

The following table contains predefined and user-defined operators that LINQ Reporting Engine enables you to use in template expressions.

<table class="using operators">
	<tbody>
		<tr>
			<td>Primary</td>
			<td>x.y  x?.y  f(x)  a[x]  a?[x]  new</td>
		</tr>
		<tr>
			<td>Unary</td>
			<td>-  !  ~  (T)x</td>
		</tr>
		<tr>
			<td>Binary</td>
			<td>*  /  %  +  -  <<  >>  <  >  <=  >=  ==  !=  &amp;  ^  |  &amp;&amp;  |  |  ??</td>
		</tr>
		<tr>
			<td>Ternary</td>
			<td>?:</td>
		</tr>
	</tbody>
</table>

The engine follows operator precedence, associativity, and overload resolution rules declared at [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029) while evaluating template expressions. But be aware of the following limitations in the behavior comparing with the specification:

- Implicit user-defined conversions are supported only when specified explicitly.
- The indexing of multi-dimensional arrays is not supported.
- Whereas the object initializer syntax is supported (including objects of anonymous types), the collection initializer syntax is not.

Also, the engine enables you to use lifted operators in template expressions. 

## Related APIs


- [ReportingEngine](https://reference.aspose.com/words/net/aspose.words.reporting/reportingengine/) — The engine responsible for building reports from templates, evaluating template expressions including operators.
- [ReportBuilder](https://reference.aspose.com/words/net/aspose.words.lowcode/reportbuilder/) — A helper class that simplifies report creation by wrapping the reporting engine.
- [ReportBuildOptions](https://reference.aspose.com/words/net/aspose.words.reporting/reportbuildoptions/) — Controls behavior of report building, such as handling of operator overloads and expression evaluation.

## FAQ

1. **Q:** Which operators are available for use in LINQ Reporting Engine template expressions?  
   **A:** The engine supports primary operators (`x.y`, `x?.y`, `f(x)`, `a[x]`, `a?[x]`, `new`), unary operators (`-`, `!`, `~`, `(T)x`), binary operators (`*`, `/`, `%`, `+`, `-`, `<<`, `>>`, `<`, `>`, `<=`, `>=`, `==`, `!=`, `&`, `^`, `|`, `&&`, `||`, `??`), and the ternary conditional operator (`?:`). Custom user‑defined operators can also be used if they are defined in the data model.

2. **Q:** Can I use the null‑conditional operator (`?.`) inside a template expression?  
   **A:** Yes, the null‑conditional operator is part of the primary operators supported by the engine, allowing safe navigation of potentially null objects in expressions.

3. **Q:** Are implicit user‑defined conversions applied automatically in template expressions?  
   **A:** No. Implicit user‑defined conversions are only applied when you explicitly cast the value in the expression. The engine does not perform automatic implicit conversions.

4. **Q:** Is collection initializer syntax (e.g., `new List<int>{1,2,3}`) supported in template expressions?  
   **A:** No. While object initializer syntax is supported (including anonymous types), collection initializer syntax is not recognized by the LINQ Reporting Engine.

5. **Q:** How does the engine handle indexing of multi‑dimensional arrays?  
   **A:** Indexing of multi‑dimensional arrays is not supported. You can only index single‑dimensional arrays or collections that expose an indexer.