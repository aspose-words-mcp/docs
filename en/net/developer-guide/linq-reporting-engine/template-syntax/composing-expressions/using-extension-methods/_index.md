---
title: Using Extension Methods in C#
second_title: Aspose.Words for .NET
articleTitle: Using Extension Methods
linktitle: Using Extension Methods
description: "Use extension methods in template expressions when building a report in C#."
type: docs
weight: 40
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/using-extension-methods-linq/
timestamp: 2024-02-16-10-54-23
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to use extension methods within LINQ Reporting Engine templates.

{{% /alert %}}

LINQ Reporting Engine enables you to use the following built‑in extension methods in template expressions:

- Extension methods mimicking the ones for `IEnumerable<T>` (see "Appendix A. Enumeration Extension Methods" for more information)
- Extension methods for iteration variables (see "Using Extension Methods of Iteration Variables" for more information)

**Note** – Extension methods, other than the built‑in ones, can be used only in the form of plain static methods in template expressions.

------

## FAQ

1. **Q:** How can I call a custom static method as an extension method in a LINQ Reporting Engine template?  
   **A:** Custom extension methods cannot be called with extension-method syntax; call them as plain static methods. Make the class and the method public, add the class to the known types (`engine.KnownTypes.Add(typeof(MyUtilities))`), and call the method with the class name, e.g., `<<[MyUtilities.FormatDate(order.Date)]>>`.

2. **Q:** Which built‑in extension methods are available for iteration variables?  
   **A:** Iteration variables have the `IndexOf()` and `NumberOf()` methods (see "Using Extension Methods of Iteration Variables"), e.g., `<<[item.NumberOf()]>>`. Enumeration extension methods such as `Where` are applied to sequences, e.g., `<<foreach [p in Products.Where(p => p.Price > 100)]>>`.

3. **Q:** Can I use full LINQ query operators like `Select` or `OrderBy` inside a template expression?  
   **A:** Yes, in method syntax: `Select`, `OrderBy`, and the other methods listed in "Appendix A. Enumeration Extension Methods" can be used, e.g., `Persons.OrderBy(p => p.Age)`. LINQ query syntax (`from … select …`) is not supported.

4. **Q:** Why do I receive a “Method not found” error when using an extension method in a template?  
   **A:** Custom methods must be public and static, their class must be added to `ReportingEngine.KnownTypes`, and they must be called as static methods (`MyUtilities.Method(value)`), not with extension-method syntax (`value.Method()`). Otherwise the engine cannot resolve the member and throws an exception.

5. **Q:** Can I return a custom object type from an extension method used in a template?  
   **A:** Yes. An expression tag outputs the result's `ToString()` value, so a custom object is rendered with its `ToString()` implementation. You can also access the object's public members in the template, e.g., `<<[MyUtilities.GetPoint().X]>>`.