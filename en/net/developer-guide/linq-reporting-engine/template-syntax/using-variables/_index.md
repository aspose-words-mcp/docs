---
title: Using Variables in C#
second_title: Aspose.Words for .NET
articleTitle: Using Variables
linktitle: Using Variables
description: "Use variables to calculate an expensive value just once and access it multiple times in template documents using C#."
type: docs
weight: 130
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/using-variables/
aliases: [/net/template-syntax/#using-variables]
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to use variables in templates for dynamic content generation.

{{% /alert %}}

LINQ Reporting Engine enables you to use variables in template documents. Variables are useful when you need to calculate an expensive value just once and access it multiple times in a template. Also, calculation of complex values such as running (progressive) totals may require variables, see “Appendix C. Typical Templates” to get an example.

You can declare a variable in a template using a var tag as follows.

{{< highlight csharp >}}
<<var [variable_type variable_name = variable_value]>>
{{< /highlight >}}

The following table describes elements of the `var` tag.

| Element | Optional? | Remarks |
| :- | :- | :- |
| **Variable Type** | Yes | You can specify the type of a variable explicitly. This type must be known by the engine (see “Setting up Known External Types” for more information). If you do not specify the type explicitly, it is determined implicitly by the engine from the specified variable value. |
| **Variable Name** | No | For a new variable, its name must be a unique identifier. |
| **Assignment Operator** | No |  |
| **Variable Value** | No |  |


During runtime, a `var` tag is removed while the value of the corresponding variable is calculated and set appropriately.

After a variable is declared in a template, its value can be accessed using the name of the variable as any other identifier. For example, the following template outputs a string “Hello!”

{{< highlight csharp >}}
<<var [s = “Hello!”]>><<[s]>>
{{< /highlight >}}

You can redefine the value of a variable using a `var` tag against the name of this variable. For example, the following template outputs string “Hello, World!”

{{< highlight csharp >}}
<<var [s = “Hello, ”]>><<[s]>><<var [s = “World!”]>><<[s]>>
{{< /highlight >}}

Using of variables has the following restrictions:

- You can not redefine the type of a variable.
- You can not use the contextual object member access feature against a variable. See “Using Contextual Object Member Access” for more information.
- Using a `var` tag, you can not redefine the value of an iteration variable or a data source.

## Related APIs


- [ReportingEngine](https://reference.aspose.com/words/net/aspose.words.reporting/reportingengine/)
- [ReportingEngine.BuildReport](https://reference.aspose.com/words/net/aspose.words.reporting/reportingengine/buildreport/)
- [`<<var>>` Tag Syntax](https://docs.aspose.com/words/net/template-syntax/#using-variables)
- [`<<[name]>>` Expression Syntax](https://docs.aspose.com/words/net/template-syntax/)


## FAQ

1. **Q:** How do I declare a variable in a template?  
   **A:** Use the `<<var>>` tag with the syntax `<<var [type name = value]>>`. The type is optional; if omitted, the engine infers it from the value.

2. **Q:** Can I explicitly set the variable type, and when should I do it?  
   **A:** Yes. Include the type before the variable name, e.g., `<<var [int total = 0]>>`. Specify the type when the engine must know the exact CLR type, such as for numeric calculations or when the value cannot be inferred.

3. **Q:** Is it possible to change a variable's type after it has been declared?  
   **A:** No. Once a variable's type is defined, it cannot be redefined. Attempting to assign a value of a different type will cause a runtime error.

4. **Q:** How can I access the value of a variable later in the same template?  
   **A:** Insert the variable name inside double‑angle brackets, e.g., `<<[myVar]>>`. The engine replaces this placeholder with the current value of `myVar`.

5. **Q:** What restrictions apply when redefining a variable's value?  
   **A:** You may change the value, but you cannot change its type, use contextual object member access on it, or redefine iteration variables or data‑source variables with a `var` tag.