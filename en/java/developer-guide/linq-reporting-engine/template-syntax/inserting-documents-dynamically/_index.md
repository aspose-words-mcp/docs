---
title: Inserting Documents Dynamically in Java
second_title: Aspose.Words for Java
articleTitle: Inserting Documents Dynamically
linktitle: Inserting Documents Dynamically
description: "Insert contents of outer documents into your document dynamically when building a report in Java."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/inserting-documents-dynamically/
timestamp: 2024-05-08-14-20-48
---

You can insert contents of outer documents to your reports dynamically using `doc` tags. A `doc` tag denotes a placeholder within a template for a document to be inserted during runtime. 

Syntax of a `doc` tag is defined as follows.

{{< highlight csharp >}}
<<doc [document_expression]>>
{{< /highlight >}}

**Note** – A `doc` tag can be used almost anywhere in a template document except textboxes and charts.

An expression declared within a `doc` tag is used by the engine to load a document to be inserted during runtime. The expression must return a value of one of the following types:

- A byte array containing document data
- An [InputStream](https://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html) instance able to read document data
- An instance of the `Document` class
- A string containing a document URI, path, or Base64-encoded document data

While building a report, an expression declared within a `doc` tag is evaluated and its result is used to load a document which content replaces the `doc` tag then.

**Note** – If an expression declared within a `doc` tag returns a stream object, then the stream is closed by the engine as soon as a corresponding document is loaded.

By default, while inserting content of an outer document, the engine applies corresponding styles of a template document. This makes content of a result document look more consistent. However, you can keep source formatting for content being inserted by using a `sourceStyles` switch as shown in the following snippet.

{{< highlight csharp >}}
<<doc [document_expression] -sourceStyles>>
{{< /highlight >}}

The engine exhibits similar behavior when dealing with list numbering. By default, numbered lists from a template document are continued when their identifiers match those from a document being inserted. However, if numbering for content being inserted should be separated and kept as is, this can be done by applying a `sourceNumbering` switch as follows.

{{< highlight csharp >}}
<<doc [document_expression] -sourceNumbering>>
{{< /highlight >}}

Also, you can trim the last paragraph break from a document being inserted by using an `inline` switch. In particular, this feature is useful for a single-paragraph document being inserted, when it is necessary to put the document's content within the same paragraph that contains a corresponding `doc` tag in order to apply the paragraph's formatting such as list numbering. The following snippet shows the template syntax for this.

{{< highlight csharp >}}
<<doc [document_expression] -inline>>
{{< /highlight >}}

By default, a document being inserted is not checked against template syntax and is not populated with data. However, you can enable this by using a `build` switch as follows.

{{< highlight csharp >}}
<<doc [document_expression] -build>>
{{< /highlight >}}

When a `build` switch is used, the engine treats a document being inserted as a template that can access the following data available at the scope of a corresponding `doc` tag:

- Data sources  
- Variables  
- A contextual object (see “Using Contextual Object Member Access” for more information)  
- Known external types (see “Setting up Known External Types” for more information)  

------  

## FAQ  

1. **Q:** How do I insert a document from a file path using a `doc` tag?  
   **A:** Place a `doc` tag in the template and provide the file path as a string expression, e.g. `<<doc ["C:/Docs/Appendix.docx"]>>`. At runtime the engine loads the file and replaces the tag with its content.

2. **Q:** I want the inserted document to keep its original formatting. Which switch should I use?  
   **A:** Add the `-sourceStyles` switch to the tag: `<<doc [docExpression] -sourceStyles>>`. This tells the engine to preserve the source document's styles instead of mapping them to the template's styles.

3. **Q:** My inserted document contains numbered lists, but the numbering continues from the template list. How can I keep the numbering separate?  
   **A:** Use the `-sourceNumbering` switch: `<<doc [docExpression] -sourceNumbering>>`. This prevents the engine from merging list identifiers and retains the original numbering of the inserted document.

4. **Q:** Can I insert a single‑paragraph document inline so that it adopts the surrounding paragraph's formatting?  
   **A:** Yes. Apply the `-inline` switch: `<<doc [docExpression] -inline>>`. The engine removes the trailing paragraph break of the inserted document and places its text inside the same paragraph that contains the tag.

5. **Q:** How can I populate merge fields inside the inserted document with data from my report?  
   **A:** The `-build` switch processes LINQ Reporting Engine template syntax in the inserted document, not merge fields. Use template tags in that document and add the switch: `<<doc [docExpression] -build>>`. The inserted document is then treated as a template and can use the same data sources, variables, and contextual objects that are available at the location of the `doc` tag.  