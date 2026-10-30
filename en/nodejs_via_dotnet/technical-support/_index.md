---
title: Technical Support
second_title: Aspose.Words for Node.js via .NET
articleTitle: Technical Support
linktitle: Technical Support
type: docs
description: "Aspose.Words for Node.js via .NET provides free technical support available to all users. Please report your question, issue, or feature request using Aspose Free Support Forum."
doc_version: 2025-04-18-19-55
weight: 80
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/technical-support/
aliases: [/nodejs/technical-support/]
timestamp: 2025-04-18-12-56-02
---

Aspose provides unlimited free technical support for all of its products. Support is available to all users, including evaluation. The main avenue of support is [Aspose.Forums](https://forum.aspose.com/c/words/8).

{{% alert color="primary" %}}

Please note that Aspose does not provide technical support over the phone. Phone support is only available for sales and purchase questions.

{{% /alert %}}

## Aspose Free Support Forum

If you need help with Aspose.Words, consider the following:

* Make sure you are using the latest Aspose.Words version before reporting an issue. 
* Have a look through the forums, this documentation, and the [API Reference](https://reference.aspose.com/words/nodejs-net/) before reporting an issue – perhaps your question has already been answered.
* Post your question to the [Aspose.Words Forum](https://forum.aspose.com/c/words/8), and it will be answered within a few hours. Questions are answered directly by the Aspose.Words development team.
* When expecting a reply on the forums, please allow for time zone differences.

## Report an Issue or Feature Request

When posting your issue, question, or feature request with Aspose.Words, follow these simple steps to make sure it is resolved in the most efficient way:

* Include the original document and possibly the code snippet that is causing the problem. If you need to attach multiple files, zip them into one. It is safe to attach your documents to `Aspose.Forums` because only you and the Aspose developers will have access to the attached files.
* Try to report one issue per thread. If you have another issue, question, or feature request, please report it in a separate thread.

------ 

## FAQ

1. **Q:** How do I apply a license for Aspose.Words in a Node.js‑via‑.NET project?  
   **A:** Load the license file using the `aw.License` class before creating any `Document` objects. Example:  
   ```js
   const aw = require('@aspose/words');
   const license = new aw.License();
   license.setLicense("Aspose.Words.lic");
   ```
   Ensure the license file is deployed with your application and the path is correct.

2. **Q:** Where can I find the API reference for licensing and other classes?  
   **A:** The complete API reference for Aspose.Words for Node.js via .NET is available at https://reference.aspose.com/words/nodejs-net/. Look under the **License** section for details on the `License` class and its methods.

3. **Q:** What should I include when posting a support request on the forum?  
   **A:** Attach the original document (or a zip containing all relevant files), a minimal reproducible code snippet, the exact version of Aspose.Words you are using, and a clear description of the problem. This helps the support team reproduce and resolve the issue quickly.

4. **Q:** Is phone support available for technical questions?  
   **A:** No. Aspose provides technical support exclusively through the free support forum and the issue‑tracking system. Phone support is limited to sales and purchase inquiries only.

5. **Q:** How can I verify that my license is correctly applied?  
   **A:** `setLicense` throws an exception if the license is invalid. After setting the license, save a test document (for example, a PDF): if it has no evaluation watermark or limitation message, the license is active.