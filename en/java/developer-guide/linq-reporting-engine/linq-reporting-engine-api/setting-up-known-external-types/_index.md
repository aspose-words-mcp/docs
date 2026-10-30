---
title: Setting up Known External Types in Java
second_title: Aspose.Words for Java
articleTitle: Setting up Known External Types
linktitle: Setting up Known External Types
description: "Learn how to set up external types using LINQ in Java."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/setting-up-known-external-types/
timestamp: 2024-01-27-14-07-04
---

LINQ Reporting Engine must be aware of custom external types that you reference in your template before the engine processes the template. You can set up external types known by the engine through the `ReportingEngine.getKnownTypes()` property. The property represents an unordered set (that is, a collection of unique items) of [Class](https://docs.oracle.com/javase/7/docs/api/java/lang/Class.html) objects. Every type in the set must meet requirements declared at “Working with Types”.

**Note** – `Object`, `String`, and primitive types are known by the engine by default.

Consider the following example. Given an `ImageUtil` class declared at your application and a template accessing a static member of this class, you can use the following code to make the engine be aware of the class before processing the template.
{{< highlight java >}}
ReportingEngine engine = new ReportingEngine();
engine.getKnownTypes().add(ImageUtil.class);
engine.buildReport(...);
{{< /highlight >}}

------ 

## FAQ

1. **Q:** How do I register a custom Java class so that the LINQ Reporting Engine can use it in a template?  
   **A:** Create an instance of `ReportingEngine`, then add the class object to the engine's known‑types set via `engine.getKnownTypes().add(YourClass.class);`. After that, call `engine.buildReport(...)` to process the template.

2. **Q:** Which types are already known by the engine without any configuration?  
   **A:** The engine automatically knows `Object`, `String`, and all Java primitive types (e.g., `int`, `double`, `boolean`). No additional registration is required for these.

3. **Q:** Can I add several custom types at once?  
   **A:** Yes, by calling `add` once per type, e.g., `engine.getKnownTypes().add(TypeA.class); engine.getKnownTypes().add(TypeB.class);`, or in a loop before building the report. `KnownTypeSet` has no method that adds several types at once.

4. **Q:** How can I remove a previously added type from the known‑types set?  
   **A:** Use the `remove` method on the set: `engine.getKnownTypes().remove(UnwantedClass.class);`. This is useful if the class should no longer be accessible in templates.

5. **Q:** Do I need to register primitive wrapper classes (e.g., `Integer`, `Double`) manually?  
   **A:** Yes, to use their static members. Primitive types are known by default, but wrapper classes are not: add them like any other type, e.g., `engine.getKnownTypes().add(Integer.class)`, before calling `Integer.parseInt(...)` in a template.