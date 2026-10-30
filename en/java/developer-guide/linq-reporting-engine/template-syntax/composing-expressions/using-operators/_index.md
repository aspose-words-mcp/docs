---
title: Using Operators in Java
second_title: Aspose.Words for Java
articleTitle: Using Operators
linktitle: Using Operators
description: "Use predefined operators in template expressions when building a report in Java."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/using-operators/
timestamp: 2024-10-21-11-17-44
---

The following table contains predefined operators that LINQ Reporting Engine enables you to use in template expressions.

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

The engine follows operator precedence, associativity, and overload resolution rules declared at [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029) while evaluating template expressions. This behavior normally conforms to Java. But be aware of the following limitations and differences in the behavior comparing with the specification and Java behavior:

- String equality and inequality check operators test string contents, rather than string references.
- Whereas the object initializer syntax is supported (including objects of anonymous types), the collection initializer syntax is not.

Also, the engine enables you to use lifted operators in template expressions. In Java, operands of lifted operators are represented by primitive type class wrappers like `Integer`, `Double`, and others, in contrast to nullable types in C#. That is, for example, given that variables a and b are of the `Integer` type and the value of a is `null`, expression "a + b" is evaluated to `null` by the engine, whereas it throws an exception in Java during runtime.

------ 

## FAQ

1. **Q:** How does the `==` operator evaluate strings in a template expression?  
   **A:** In the LINQ Reporting Engine the `==` (and `!=`) operator compares the actual text of the strings, not their object references. Therefore two different `String` objects containing the same characters are considered equal. This behavior differs from the default Java reference comparison.

2. **Q:** Can I use collection initializer syntax (e.g., `{1, 2, 3}`) inside a template?  
   **A:** No. The engine supports object initializer syntax, including anonymous types, but collection initializer syntax is not implemented. To create a collection you need to instantiate it explicitly in your data source before passing it to the template.

3. **Q:** What happens when I apply an arithmetic operator to a `null` operand?  
   **A:** The engine uses lifted operators: if any operand of an arithmetic expression is `null`, the whole expression evaluates to `null` instead of throwing a `NullPointerException`. This allows safe calculations on nullable wrapper types such as `Integer` or `Double`.

4. **Q:** How can I use the ternary operator to provide a default value?  
   **A:** The ternary operator `condition ? valueIfTrue : valueIfFalse` works the same as in Java. Example: `<<[total != null ? total : 0]>>` will output `total` when it is not `null`; otherwise it outputs `0`.

5. **Q:** Are there any operator‑precedence differences I should be aware of compared to standard Java?  
   **A:** The engine follows the precedence rules defined in the C# specification, which are largely compatible with Java. Most operators (e.g., `*`, `+`, `&&`, `||`) have the same precedence, but be cautious with the null‑coalescing operator `??`, which does not exist in Java and has its own precedence level in the engine.