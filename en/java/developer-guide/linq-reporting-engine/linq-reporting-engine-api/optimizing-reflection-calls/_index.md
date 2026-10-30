---
title: Optimizing Reflection Calls in Java
second_title: Aspose.Words for Java
articleTitle: Optimizing Reflection Calls
linktitle: Optimizing Reflection Calls
description: "Learn how to minimize the reflection usage using LINQ in Java."
type: docs
weight: 100
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/optimizing-reflection-calls/
timestamp: 2024-01-27-14-07-04
---

LINQ Reporting Engine uses reflection calls while accessing members of custom external types. However, reflection calls are much slower than direct calls, which creates a performance overhead.

That is why, the engine provides a strategy minimizing the reflection usage. The strategy is based upon the runtime type generation. That is, the engine generates a proxy type per an external type. The proxy directly calls members of the corresponding external type, the engine to access these members in a uniform way with no reflection involved. The proxy is [lazily initialized](https://en.wikipedia.org/wiki/Lazy_initialization) and reused in further. Thus, the reflection is used only while building the proxy.

Although this strategy can significantly minimize the reflection usage in a long run, it creates a performance overhead of the runtime type generation. So, if you deal with small data collections all the time while building your reports, consider the disabling of the strategy.

You can control the enabling of the strategy through the `ReportingEngine.setUseReflectionOptimization` static property. By default, the strategy is enabled.

------ 

## FAQ

1. **Q:** How can I disable reflection optimization in the LINQ Reporting Engine?  
   **A:** Call `ReportingEngine.setUseReflectionOptimization(false);` before generating any reports. This turns off the proxy‑generation mechanism, so the engine will use direct reflection for each member access.

2. **Q:** When is it advisable to turn off reflection optimization?  
   **A:** If your reports are built from very small data collections (e.g., a few dozen records), the cost of generating proxy types may outweigh the benefit of avoiding reflection. In such cases, disabling the optimization can reduce overall processing time.

3. **Q:** How do I know whether reflection optimization is currently enabled?  
   **A:** Call the static `ReportingEngine.getUseReflectionOptimization()` method. It returns `true` when the optimization is enabled.