---
title: Setting up Known External Types in C#
second_title: Aspose.Words for .NET
articleTitle: Setting up Known External Types
linktitle: Setting up Known External Types
description: "Learn how to set up external types using LINQ in C#."
type: docs
weight: 50
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/setting-up-known-external-types/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to configure known external types for the LINQ Reporting Engine.

{{% /alert %}}

LINQ Reporting Engine must be aware of custom external types that you reference in your template before the engine processes the template. You can set up external types known by the engine through the `ReportingEngine.KnownTypes` property. The property represents an unordered set (that is, a collection of unique items) of [Type](https://docs.microsoft.com/en-us/dotnet/api/system.type?view=net-6.0) objects. Every type in the set must meet requirements declared at “Working with Types”.

**Note** – Aliases of simple types like `int`, `string`, and others are known by the engine by default.

Consider the following example. Given an `ImageUtil` class declared at your application and a template accessing a static member of this class, you can use the following code to make the engine be aware of the class before processing the template.

{{< highlight csharp >}}
ReportingEngine engine = new ReportingEngine();
engine.KnownTypes.Add(typeof(ImageUtil));
engine.BuildReport(...);
{{< /highlight >}}

------

## FAQ

1. **Q:** How do I register a custom type with the LINQ Reporting Engine?  
   **A:** Create an instance of `ReportingEngine`, then call `engine.KnownTypes.Add(typeof(MyCustomClass));` before invoking `engine.BuildReport`. This makes the engine aware of the type used in the template.

2. **Q:** Which types are already known by the engine without registration?  
   **A:** Primitive and simple .NET types such as `int`, `string`, `bool`, `DateTime`, `double`, and their nullable counterparts are automatically recognized by the engine.

3. **Q:** What requirements must a type meet to be added to `KnownTypes`?  
   **A:** The type must be public, and any instance members accessed from the template must be public. If the template creates an instance, the type needs a public parameter‑less constructor. Static members can be accessed directly without a constructor.

4. **Q:** Can I add several external types at once?  
   **A:** Yes. Call `engine.KnownTypes.Add` for each type, or iterate over a collection of `Type` objects and add them in a loop before building the report.

5. **Q:** What happens if a required external type is not added to `KnownTypes`?  
   **A:** The Reporting Engine throws an `InvalidOperationException` because it cannot resolve the type name used in the template, which stops the report generation. Adding the missing type to `KnownTypes` resolves the error.