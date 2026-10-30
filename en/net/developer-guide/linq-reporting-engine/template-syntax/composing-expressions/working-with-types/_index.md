---
title: Working with Types in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Types
linktitle: Working with Types
description: "Use external visible types in template expressions when building a report in C#."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-types/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with types used by the LINQ Reporting Engine.

{{% /alert %}}

LINQ Reporting Engine enables you to use externally visible types in template expressions. A *visible type* is a public type with outer types (if any) are public as well. You can use a data source object of any visible type to pass it to the engine.

However, you can use the identifier of a visible type in template expressions only if the following additional requirements are met:

- The type is not void.
- The type does not represent an array.
- The type is not an open or closed generic type.

**Note** – Whereas using generic types' identifiers is forbidden in template expressions, you can use identifiers of nullable types in the shorthand "`T?`" form.

Also, the engine enables you to use anonymous types in template expressions. Such types are useful while composing expressions with grouping by multiple keys. See "Appendix A. Enumeration Extension Methods" for the examples.

------

## FAQ

1. **Q:** Which types are allowed in LINQ Reporting Engine template expressions?  
   **A:** Only *visible* public types whose outer types are also public can be used. The type must not be `void`, must not be an array, and cannot be a generic type (open or closed). Nullable types are allowed using the `T?` shorthand.

2. **Q:** Can I reference a generic type (e.g., `List<T>`) inside a template expression?  
   **A:** No. Generic types are prohibited in template expressions. If you need to work with collections, pass a non‑generic wrapper or use an anonymous type that contains the required data.

3. **Q:** How do I use a nullable type in a template expression?  
   **A:** Use the shorthand `T?` form as a type name, for example `<<var [int? count = null]>>` or a cast `(int?)value`. Generic type identifiers such as `Nullable<int>` are not allowed. A nullable property is referenced by its name as usual, e.g., `Age`.

4. **Q:** Are anonymous types supported in template expressions?  
   **A:** Yes. Anonymous types can be used, which is handy for grouping or projecting multiple keys without defining a dedicated class. They must still satisfy the visibility rules (public members).

5. **Q:** What happens if I try to use an array type in a template expression?  
   **A:** The engine will reject the expression because array types are not allowed. Convert the array to a collection type that meets the visibility requirements or expose the needed elements through a property.