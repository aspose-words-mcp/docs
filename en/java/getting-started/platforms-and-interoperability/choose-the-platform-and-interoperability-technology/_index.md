---
title: Choose Platform and Technology
second_title: Aspose.Words for Java
articleTitle: Choose the Platform and Interoperability Technology
linktitle: Choose the Platform and Interoperability Technology
description: "Choose the Platform for Aspose.Words."
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/choose-the-platform-and-interoperability-technology/
timestamp: 2024-10-21-11-17-44
---

Using Aspose.Words from any other programming language requires the use of some *interoperability technology* . The interoperability technology must allow your programming language to call into a class library written for Java. 

This is a list of the suggested interoperability technologies to use for a variety of programming languages: 

| Programming Language | Aspose.Words to Use | Interoperability Technology |
| :- | :- | :- |
| `ASP` | .NET | `COM Interop` |
| `ColdFusion` | .NET | ColdFusion .NET extension |
|  | `Java` | ColdFusion |
| `Delphi` | .NET | `COM Interop` |
| `JScript` | .NET | `COM Interop` |
| `Perl` | .NET | `COM Interop` |
|  | `Java` | `Inline::Java` |
| `PHP` | .NET | `COM Interop` |
|  | `Java` | Java Bridge |
| `PowerBuilder` | .NET | `COM Interop` |
| `Python` | .NET | `COM Interop` |
|  | `Java` | JPype |
| `VBScript` | .NET | `COM Interop` |
| Visual Basic | .NET | `COM Interop` |
From the above table you can see that for some programming languages it is possible to use either Aspose.Words for .NET or Aspose.Words for Java. The following table can help you choose:

| `Scenario` | Comments |
| :- | :- |
| Aspose.Words for .NET via COM Interop | <p>Consider the following:</p><p>- Available on Microsoft Windows platforms only.</p><p>- Cannot call static methods.</p><p>- Hard to call overloaded methods (suffixes added to names).</p><p>- Hard to use enumerated values (need to look up and use a constant value).</p><p>- Cannot invoke constructors with parameters.</p> |
| Aspose.Words for Java via Java Bridge or Inline::Java | <p>Consider the following:</p><p>- Available on any platform where Java is available.</p><p>- Can call static methods, constructors with parameters, overloaded methods and use enumerated values.</p> |

------

## FAQ


1. **Q:** Which Aspose.Words product should I choose for my programming language?  
   **A:** If your language runs on the Java Virtual Machine (e.g., via Java Bridge, JPype, Inline::Java), use **Aspose.Words for Java**. If you are on Windows and can use COM, you may use **Aspose.Words for .NET** through COM Interop. The table above lists the recommended interoperability technology for each language.

2. **Q:** Can I use Aspose.Words for .NET on Linux or macOS?  
   **A:** Yes. Aspose.Words for .NET runs on Linux and macOS with .NET Core, .NET, or Mono. Only COM Interop, which this page describes, is limited to Microsoft Windows. For cross-platform scenarios with the languages listed here, use the Java version with a Java-based interoperability layer.

3. **Q:** Why can't I call static methods or overloaded methods when using COM Interop?  
   **A:** COM Interop exposes only instance members and does not support method overloading or static members directly. To work around this, create wrapper classes in .NET that expose the required functionality as instance methods, then call those wrappers via COM.

4. **Q:** What interoperability options are available for calling Aspose.Words for Java from other languages?  
   **A:** The main options are:
   - **Java Bridge** — for languages supporting Java invocation through a bridge,
   - **JPype** — for Python,
   - **Inline::Java** — for Perl.  
   All these libraries enable calling static methods, constructors with parameters, and using enumerations as in native Java code.

5. **Q:** How do I apply an Aspose.Words license when using the Java version through an interoperability layer?  
   **A:** Load the license in the Java side of your code:  

   ```java
   // Example in Java called via JPype or Java Bridge
   com.aspose.words.License license = new com.aspose.words.License();
   license.setLicense("Aspose.Words.Java.lic");
   ```

   Ensure the license file is accessible to the Java runtime (e.g., placed in the classpath or provided with an absolute path). The interoperability layer simply forwards the call, so licensing behaves exactly as in a native Java application.