---
title: LINQ Reporting Engine Features in C#
second_title: Aspose.Words for .NET
articleTitle: LINQ Reporting Engine Features
linktitle: LINQ Reporting Engine Features
description: "Learn the powerful LINQ Reporting Engine features to build a report in C#."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/linq-reporting-engine-features/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains the features of the LINQ Reporting Engine, detailing its templating syntax, data‑binding options, expressions, and dynamic content capabilities.

{{% /alert %}}

LINQ Reporting Engine enables you to build reports in a similar way as Aspose.Words Mail Merge does. The engine provides the API that enables you to populate template documents with data that comes from various sources.

In contrast to Aspose.Words Mail Merge, LINQ Reporting Engine works with templates based on tags that you can form using just plain text. These tags define expressions and their roles during a report building process. Then, while building a report, the following procedure takes place:

1. The expressions are sequentially evaluated against a passed data source object.
2. The results of the expressions are processed by the engine according to their roles.
3. The corresponding tags are replaced with appropriate content.

While composing expressions, you can use a subset of C# language that satisfies [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029). Common reporting data manipulations such as grouping, sorting, and others are included in the expression syntax in the form of [IEnumerable&lt;T&gt;](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerable-1?view=net-6.0) extension methods. LINQ Reporting Engine gained its name because of this feature.

You can use common Aspose.Words Mail Merge data source objects such as [DataSet](https://docs.microsoft.com/en-us/dotnet/api/system.data.dataset?view=net-6.0), [DataTable](https://docs.microsoft.com/en-us/dotnet/api/system.data.datatable?view=net-6.0), and others while working with LINQ Reporting Engine as well. The engine provides a simplified expression syntax to work with such objects. For example, a data table is treated as a collection of its rows. That is, you can normally apply `IEnumerable<T>` extension methods to it. A single data row, in turn, is treated as if it was an object that has the same set of fields that the row has.

In addition to traditional data sources, the engine enables you to use custom ones. Custom data source objects are not treated in a special way by the engine. That is while working with such objects, you can use the same expression syntax as you use while writing C# code. Moreover, you can use accessible members of any custom type that can implement any complex logic. This feature makes the engine very flexible and suitable almost for any specific need while building a report.

------

## FAQ

1. **Q:** What is the LINQ Reporting Engine and how does it differ from Aspose.Words Mail Merge?  
   **A:** The LINQ Reporting Engine is a templating system that populates plain‑text tags in a Word document with data. Unlike Mail Merge, which relies on merge fields, the engine evaluates C#‑style expressions inside custom tags, giving you full LINQ capabilities for grouping, sorting, and calculations.

2. **Q:** How are tags defined in a template document?  
   **A:** Tags are written as plain text in the form `<<tag_name [expression] -switches>>` (for example, `<<[Name]>>` outputs a value and `<<foreach [item in Items]>>` … `<</foreach>>` repeats content). The engine parses these tags, evaluates any embedded expression, and replaces the tag with the resulting content during report generation.

3. **Q:** Which data source types can be used with the engine?  
   **A:** You can use standard Aspose.Words Mail Merge sources such as `DataSet`, `DataTable`, `IDataReader`, as well as any `IEnumerable<T>` collection. The engine treats each row of a `DataTable` as an object with fields that can be accessed in expressions.

4. **Q:** Can I use my own custom objects as a data source?  
   **A:** Yes. Any custom class that exposes public properties or methods can be passed to the engine. The expression syntax works exactly as it does in regular C# code, allowing you to call methods, access properties, and apply LINQ operators on your custom objects.