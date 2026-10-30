---
title: Accessing Missing Members of Data Objects in Java
second_title: Aspose.Words for Java
articleTitle: Accessing Missing Members of Data Objects
linktitle: Accessing Missing Members of Data Objects
description: "Learn how to treat missing members of data objects as null literals using LINQ in Java."
type: docs
weight: 70
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/accessing-missing-members-of-data-objects/
timestamp: 2024-07-05-16-45-23
---

By default, LINQ Reporting Engine forbids access to missing members of data objects used to build a report in template expressions, since such access is forbidden by [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029). On attempt to use a missing member of a data object, the engine throws an exception then.

But in some scenarios, members of data objects are not exactly known while designing a template. For example, if using a `DataSet` instance loaded from XML without its schema defined, some of expected data members can be missing.

To support such scenarios, the engine provides an option to treat missing members of data objects as null literals. You can enable the option as shown in the following example.

{{< highlight java >}}
ReportingEngine engine = new ReportingEngine();
engine.setOptions(ReportBuildOptions.ALLOW_MISSING_MEMBERS);
engine.buildReport(...);
{{< /highlight >}}

Consider the following example. Given that r is a `DataRow` instance that does not have a field `Missing`, by default, the following template expression causes the engine to throw an exception while building a report.

{{< highlight xml >}}
    <<[r.Missing]>>
{{< /highlight >}}

However, if `ReportBuildOptions.ALLOW_MISSING_MEMBERS` is applied, the engine treats access to such a field as a null literal, so no exception is thrown and simply no value is written to the report then.

Furthermore, the engine can be instructed to print a specific message instead of no value in such a case. The following code snippet shows how to achieve this.

{{< highlight xml >}}
ReportingEngine engine = new ReportingEngine();
engine.setOptions(ReportBuildOptions.ALLOW_MISSING_MEMBERS);
engine.setMissingMemberMessage("None");
engine.buildReport(...);
{{< /highlight >}}

**Note –** The message can be printed only instead of a template expression that represents a plain reference to a missing member of an object like in the provided template example; for instance, the message is not used when printing the result of a binary operator, one of which operands references a missing object member.

------ 

## FAQ

1. **Q:** How do I enable the engine to treat missing members as null values?  
   **A:** Set the `ReportBuildOptions.ALLOW_MISSING_MEMBERS` option on the `ReportingEngine` before building the report:

   ```java
   ReportingEngine engine = new ReportingEngine();
   engine.setOptions(ReportBuildOptions.ALLOW_MISSING_MEMBERS);
   engine.buildReport(...);
   ```

2. **Q:** What happens if I access a missing member without enabling `ALLOW_MISSING_MEMBERS`?  
   **A:** The engine throws a `RuntimeException` indicating that the member does not exist. The report generation stops unless the exception is caught.

3. **Q:** Can I display a custom message instead of an empty value when a missing member is accessed?  
   **A:** Yes. After enabling `ALLOW_MISSING_MEMBERS`, call `engine.setMissingMemberMessage("YourMessage")`. The specified message will be written wherever a missing member is referenced directly.

4. **Q:** Does `ALLOW_MISSING_MEMBERS` affect expressions that use missing members inside binary operations?  
   **A:** No. The custom message is only applied to plain member references (e.g., `<<[obj.Missing]>>`). If the missing member participates in a binary operation, the engine still treats the result as `null` and does not replace it with the custom message.

5. **Q:** Is the `ALLOW_MISSING_MEMBERS` option available in other language APIs (e.g., .NET)?  
   **A:** Yes. The same functionality exists in the .NET version of Aspose.Words under `ReportBuildOptions.ALLOW_MISSING_MEMBERS`. The usage pattern is analogous—set the option on the reporting engine before building the report.