---
title: Accessing Missing Members of Data Objects in C#
second_title: Aspose.Words for .NET
articleTitle: Accessing Missing Members of Data Objects
linktitle: Accessing Missing Members of Data Objects
description: "Learn how to treat missing members of data objects as null literals using LINQ in C#."
type: docs
weight: 70
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/accessing-missing-members-of-data-objects/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how the LINQ Reporting Engine handles missing object members by treating them as null or using custom fallback messages.

{{% /alert %}}

By default, LINQ Reporting Engine forbids access to missing members of data objects used to build a report in template expressions, since such access is forbidden by [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029). On attempt to use a missing member of a data object, the engine throws an exception then.

But in some scenarios, members of data objects are not exactly known while designing a template. For example, if using a `DataSet` instance loaded from XML without its schema defined, some of expected data members can be missing.

To support such scenarios, the engine provides an option to treat missing members of data objects as null literals. You can enable the option as shown in the following example.

{{< highlight csharp >}}
ReportingEngine engine = new ReportingEngine();
engine.Options |= ReportBuildOptions.AllowMissingMembers;
engine.BuildReport(...);
{{< /highlight >}}

Consider the following example. Given that `r` is a `DataRow` instance that does not have a field `Missing`, by default, the following template expression causes the engine to throw an exception while building a report.

{{< highlight xml >}}
<<[r.Missing]>>
{{< /highlight >}}

However, if `ReportBuildOptions.AllowMissingMembers` is applied, the engine treats access to such a field as a null literal, so no exception is thrown and simply no value is written to the report then.

Furthermore, the engine can be instructed to print a specific message instead of no value in such a case. The following code snippet shows how to achieve this.

{{< highlight csharp >}}
ReportingEngine engine = new ReportingEngine();
engine.Options |= ReportBuildOptions.AllowMissingMembers;
engine.MissingMemberMessage = "None";
engine.BuildReport(...);
{{< /highlight >}}

**Note –** The message can be printed only instead of a template expression that represents a plain reference to a missing member of an object like in the provided template example; for instance, the message is not used when printing the result of a binary operator, one of which operands references a missing object member.

------

## FAQ

1. **Q:** How can I enable the LINQ Reporting Engine to ignore missing members?  
   **A:** Set the `ReportBuildOptions.AllowMissingMembers` flag on the engine's `Options` property before calling `BuildReport`. This tells the engine to treat missing members as null literals instead of throwing an exception.

2. **Q:** What is the result of a template expression that references a missing member when `AllowMissingMembers` is enabled?  
   **A:** The engine substitutes the missing member with a null literal, so the expression produces no output and the report generation continues without errors.

3. **Q:** Can I display a custom message instead of an empty value for missing members?  
   **A:** Yes. Assign a string to `engine.MissingMemberMessage`. The specified message will be written to the report whenever a plain reference to a missing member is encountered.

4. **Q:** Does the custom missing‑member message work for expressions that use the missing member in calculations or concatenations?  
   **A:** No. The custom message is applied only to plain member references. If the missing member participates in a binary operator (e.g., arithmetic or string concatenation), the engine still treats it as null, and the expression evaluates accordingly.