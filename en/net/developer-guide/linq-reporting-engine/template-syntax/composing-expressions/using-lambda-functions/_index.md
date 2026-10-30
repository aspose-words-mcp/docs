---
title: Using Lambda Functions in C#
second_title: Aspose.Words for .NET
articleTitle: Using Lambda Functions
linktitle: Using Lambda Functions
description: "Use lambda functions in template expressions when building a report in C#."
type: docs
weight: 60
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/using-lambda-functions/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to use lambda functions inside LINQ Reporting Engine templates.

{{% /alert %}}

LINQ Reporting Engine enables you to use lambda functions only as arguments of built-in enumeration extension methods in template expressions. See "Appendix A. Enumeration Extension Methods" for more information.

**Note** – Lambda functions declared within template expressions are not interchangeable with delegates. Thus, you can not pass delegates as arguments to built-in enumeration extension methods.

You can use both explicit and implicit lambda function signatures in template expressions. If you do not specify the type of a parameter of a lambda function explicitly, the type is determined implicitly by the engine depending on the type of the corresponding enumeration.

------

## FAQ

1. **Q:** Can I pass a regular delegate to a LINQ Reporting Engine enumeration method?  
   **A:** No. Lambda functions used in template expressions are not interchangeable with delegates, and the engine does not accept delegate instances as arguments for its built‑in enumeration extension methods.

2. **Q:** Do I have to declare the parameter types explicitly in a lambda function inside a template?  
   **A:** No. You may omit the parameter types; the engine will infer them automatically based on the type of the collection being enumerated. Explicit types can be used when you need to clarify the signature.

3. **Q:** Which enumeration extension methods support lambda functions?  
   **A:** Only the built‑in enumeration extension methods listed in *Appendix A. Enumeration Extension Methods* (such as `Where`, `Select`, `OrderBy`, etc.) accept lambda functions as arguments. Custom methods are not supported.

4. **Q:** Are lambda functions allowed in other parts of a template, such as field expressions or conditional statements?  
   **A:** Lambda functions are limited to arguments of the supported enumeration extension methods. They cannot be used directly in IF fields, MERGEFIELDs, or other non‑enumeration expressions.

5. **Q:** How do I write an implicit lambda function in a template expression?  
   **A:** Use the syntax `x => x.Property` without specifying the type of `x`. The engine determines the type of `x` from the collection being processed, e.g., `<<foreach [item in Employees.Where(e => e.IsActive)]>>`.