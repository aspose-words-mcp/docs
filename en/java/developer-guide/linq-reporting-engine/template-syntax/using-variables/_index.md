---
title: Using Variables in Java
second_title: Aspose.Words for Java
articleTitle: Using Variables
linktitle: Using Variables
description: "Use variables to calculate an expensive value just once and access it multiple times in template documents using Java."
type: docs
weight: 130
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/using-variables/
timestamp: 2024-10-21-11-17-44
---

LINQ Reporting Engine enables you to use variables in template documents. Variables are useful when you need to calculate an expensive value just once and access it multiple times in a template. Also, calculation of complex values such as running (progressive) totals may require variables, see “Appendix C. Typical Templates” to get an example.

You can declare a variable in a template using a var tag as follows.

{{< highlight csharp >}}
<<var [variable_type variable_name = variable_value]>>
{{< /highlight >}}

The following table describes elements of the var tag.

| Element | Optional? | Remarks |
| :- | :- | :- |
| **Variable Type** | Yes | You can specify the type of a variable explicitly. This type must be known by the engine (see “Setting up Known External Types” for more information).<br />If you do not specify the type explicitly, it is determined implicitly by the engine from the specified variable value. |
| **Variable Name** | No | For a new variable, its name must be a unique identifier. |
| **Assignment Operator** | No |  |
| **Variable Value** | No |  |

During runtime, a `var` tag is removed while the value of the corresponding variable is calculated and set appropriately.

After a variable is declared in a template, its value can be accessed using the name of the variable as any other identifier. For example, the following template outputs string “Hello!”

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

------ 

## FAQ

1. **Q:** How do I declare a variable with an explicit type in a template?  
   **A:** Include the type before the variable name inside the `var` tag, e.g. `<<var [LocalDate startDate = LocalDate.now()]>>`. The engine must know the type: add it with `engine.getKnownTypes().add(LocalDate.class)` (see “Setting up Known External Types”).

2. **Q:** How can I reference a variable after it has been declared?  
   **A:** Use the variable name inside double‑angle brackets. For example, after `<<var [total = 0]>>`, you can output its value with `<<[total]>>` anywhere later in the document.

3. **Q:** Can I change the type of a variable once it has been created?  
   **A:** No. The variable's type is fixed at the first declaration and cannot be redefined. Attempting to declare the same name with a different type will cause a runtime error.

4. **Q:** Is it possible to redefine a variable's value inside a `foreach` loop?  
   **A:** Yes, you may assign a new value to the same variable inside a loop using another `var` tag, e.g. `<<var [sum = sum + item.Price]>>`. However, you cannot change the variable's type or redefine an iteration variable itself.

5. **Q:** How do I use a variable to format a date inside a template?  
   **A:** Declare a variable that holds the formatted string, for example: `<<var [java.time.format.DateTimeFormatter fmt = java.time.format.DateTimeFormatter.ofPattern("yyyy-MM-dd")]>>` then `<<var [formattedDate = dateValue.format(fmt)]>>`. Output with `<<[formattedDate]>>`. This avoids repeated formatting calls.