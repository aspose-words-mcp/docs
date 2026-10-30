---
title: Hello World Example in Java
second_title: Aspose.Words for Java
articleTitle: Hello World Example
linktitle: Hello World Example
description: "Create Hello world example to start working with LINQ Reporting Engine to build a report in Java."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/hello-world-example/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="primary" %}}

A "Hello, World" example is traditionally used to introduce features of a programming language or software with a simple use case. Here is the example for LINQ Reporting Engine.

{{% /alert %}}

Assume, that you have the `Sender` class defined in your application as follows:


{{< gist "aspose-words-gists" "4732fa15eef8fceb1219ff2c1309d5e4" "sender.java" >}}

To produce a report containing a message of a concrete sender on its behalf, you can use a template document with the following content.

{{< highlight csharp >}}
<<[sender.getName()]>> says: "<<[sender.getMessage()]>>."
{{< /highlight >}}

To build a report from the template, you can use the following source code.

{{< gist "aspose-words-gists" "4732fa15eef8fceb1219ff2c1309d5e4" "linq-hello-world.java" >}}

After the source code is ran, the template document is populated with the data about the sender, and the document becomes a ready report with the following content.

{{< highlight csharp >}}
LINQ Reporting Engine says: "Hello, World."
{{< /highlight >}}

After the report document is built, you can save it or perform any other tasks on it using [Aspose.Words API](https://reference.aspose.com/words/java/com.aspose.words/) in your code.

------ 

## FAQ

1. **Q:** How do I add the LINQ Reporting Engine to my Java project?  
   **A:** Include the Aspose.Words for Java Maven/Gradle dependency (e.g., `com.aspose:aspose-words:23.12`) and ensure the `aspose-words.jar` is on the classpath. The LINQ Reporting Engine is part of this library, so no additional packages are required.

2. **Q:** What is the correct syntax for template tags when using Java objects?  
   **A:** Use double‑angle brackets with the object variable name and its Java getter method, e.g., `<<[sender.getName()]>>` and `<<[sender.getMessage()]>>`. The engine evaluates the expression at runtime and inserts the returned string.

3. **Q:** How can I pass my custom `Sender` object to the report?  
   **A:** Create an instance of `Sender` and pass it to `engine.buildReport(doc, sender, "sender")`. The third argument is the data source name used in the template tags (`sender` in `<<[sender.getName()]>>`). After the report is built, save the document with `doc.save(...)`.

4. **Q:** In which formats can I save the generated report?  
   **A:** After building the report, use `Document.save(String filePath, SaveFormat format)` where `SaveFormat` can be `DOCX`, `PDF`, `HTML`, etc. Example: `document.save("Report.pdf", SaveFormat.PDF);`.

5. **Q:** Do I need a license to run this example, and how do I apply it?  
   **A:** A temporary evaluation license works for testing, but a purchased license removes evaluation limitations. Load the license with `License license = new License(); license.setLicense("Aspose.Words.Java.lic");` before creating any `Document` or `ReportingEngine` objects.