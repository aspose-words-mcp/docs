---
title: Working with Types in Java
second_title: Aspose.Words for Java
articleTitle: Working with Types
linktitle: Working with Types
description: "Use external visible types in template expressions when building a report in Java."
type: docs
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-types/
timestamp: 2024-01-27-14-07-04
---

LINQ Reporting Engine enables you to use external visible types in template expressions. A *visible* type is a public type which outer types (if any) are public as well. You can use a data source object of any visible type to pass it to the engine.

However, you can use the identifier of a visible type in template expressions only if the following additional requirements are met:

- The type is not void.
- The type does not represent an array.
- The type identifier does not contain generic type arguments.

Also, the engine enables you to use anonymous types in template expressions. Such types are useful while composing expressions with grouping by multiple keys. See “Appendix A. Enumeration Extension Methods” for the examples.

------ 

## FAQ

1. **Q:** What qualifies as a *visible* type for use in LINQ Reporting Engine template expressions?  
   **A:** A visible type must be a public class (or struct) whose containing (outer) types are also public. The type cannot be `void`, an array, or contain generic type arguments in its identifier.

2. **Q:** Can I reference generic types or arrays directly in a template expression?  
   **A:** No. The engine does not allow identifiers that include generic type arguments (e.g., `List<T>`) or array types (e.g., `String[]`). Use a non‑generic wrapper or a concrete type instead.

3. **Q:** How can I use an anonymous type inside a template expression?  
   **A:** Java has no anonymous types, so you cannot pass one in a data source. You can create one inside a template expression with the object initializer syntax, e.g., `<<var [item = new { Id = 1, Name = "John" }]>>`, and then access its members, such as `<<[item.Id]>>` and `<<[item.Name]>>`.

4. **Q:** Why does a template expression fail when I try to use a nested public class?  
   **A:** All outer types of the nested class must be public. If any containing class is non‑public, the nested type is not considered visible and its identifier cannot be used in the template.

5. **Q:** Are Java primitive types (e.g., `int`, `double`) usable in template expressions?  
   **A:** Yes. Primitive types are treated as visible types, so you can reference them directly in expressions, such as `<<[order.Total]>>` where `Total` is a `double`.