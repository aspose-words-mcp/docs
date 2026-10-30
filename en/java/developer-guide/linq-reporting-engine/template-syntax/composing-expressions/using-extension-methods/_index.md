---
title: Using Extension Methods in Java
second_title: Aspose.Words for Java
articleTitle: Using Extension Methods
linktitle: Using Extension Methods
description: "Use extension methods in template expressions when building a report in Java."
type: docs
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/using-extension-methods/
timestamp: 2024-01-27-14-07-04
---

LINQ Reporting Engine enables you to use the following built-in extension methods in template expressions:

- Extension methods mimicking the ones for `IEnumerable<T>` (see "Appendix A. Enumeration Extension Methods" for more information)
- Extension methods for iteration variables (see "Using Extension Methods of Iteration Variables" for more information)

------ 

## FAQ

1. **Q:** How do I call an extension method inside a LINQ Reporting Engine template?  
   **A:** Call it on a sequence inside an expression in square brackets, using the Java (camelCase) name, e.g., `<<[persons.where(p => p.getAge() > 30).count()]>>`, or in a data band: `<<foreach [p in persons.where(p => p.getAge() > 30)]>>`. The engine resolves the method at runtime.

2. **Q:** Which enumeration‑style extension methods are available by default?  
   **A:** The methods that mimic the `IEnumerable<T>` extension methods, written in camelCase in Java templates: `where`, `select`, `orderBy`, `take`, `skip`, `count`, `any`, and the others listed in “Appendix A. Enumeration Extension Methods”.

3. **Q:** Can I use extension methods on the iteration variable itself (e.g., the index of a `foreach` loop)?  
   **A:** Yes. Iteration variables have the `indexOf()` and `numberOf()` methods (see “Using Extension Methods of Iteration Variables”), e.g., `<<[item.indexOf()]>>`. There are no `IsFirst`, `IsLast`, or `IsEven` helpers; use expressions such as `<<[item.indexOf() == 0 ? "First" : ""]>>` instead.

4. **Q:** Is it possible to add my own custom extension methods for use in Java templates?  
   **A:** Not as extension methods: only the built‑in extension methods can be called on a sequence. To use your own code, make the class and the method public and static, add the class to `engine.getKnownTypes()`, and call the method with the class name, e.g., `<<[MyUtilities.formatDate(order.getOrderDate())]>>`.

5. **Q:** Are the same extension methods available when using Aspose.Words for .NET or other platforms?  
   **A:** Yes. .NET and Java have the same set of built‑in extension methods and the same `<< >>` tag syntax. Only the method names follow the platform's naming: `Where`, `Count` in .NET templates and `where`, `count` in Java templates. Refer to the platform‑specific documentation for details.