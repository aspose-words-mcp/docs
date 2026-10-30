---
title: How to Run the Examples
second_title: Aspose.Words for Node.js via .NET
articleTitle: How to Run the Examples
linktitle: How to Run the Examples
description: "Download Aspose.Words for Node.js via .NET examples from our GitHub repository and learn how to run them to become more familiar with the Aspose.Words possibilities and features."
type: docs
weight: 110
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/how-to-run-the-examples/
aliases: [/nodejs/how-to-run-the-examples/]
timestamp: 2025-04-18-14-07-04
---

To become more familiar with the Aspose.Words possibilities and features we provide examples that can be downloaded from our GitHub repository, run, and learn in detail.

In this article, you can find the system requirements, as well as information on how to run the examples.

## Software Requirements and Prerequisites

Please make sure you have Node.js 14.17.0 or later installed on yout PC.

## Download and Run the Examples

All Aspose.Words for Node.js via .NET examples are hosted on [GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET). You can either clone the repository using your favorite GitHub client or download [the ZIP file](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/archive/master.zip).

After getting a copy of the repository, you may find that:

- All the examples are located in the **ApiExamples** and **DocExamples** folder.
- All the examples are unit tests.

To run the examples, open your favorite command prompt:

- Change the directory to the **ApiExamples** or **DocExamples** folder.
- Run all tests with the command:
{{< highlight js >}}
npm test
{{< /highlight >}}
- Run specific tests only, for example ExBookmarks.test.js:
{{< highlight js >}}
jest --findRelatedTests ExBookmarks.test.js
{{< /highlight >}}

{{% alert color="primary" %}}

Please feel free to reach out using our [Aspose.Words Product Family Forum](https://forum.aspose.com/c/words/8) if you have any issues setting up or running the examples.

{{% /alert %}}

## Contribute to Improving the Examples

If you like to add or improve an example, we encourage you to contribute to the project. All examples and showcase projects in this repository are open source and can be freely used in your applications.

You can fork the repository, edit the source code, and create a pull request to contribute. We will review the changes and include them in the repository if found helpful.

------  

## FAQ  

1. **Q:** Do I need a license file to run the example tests?  
   **A:** No. The repository does not include a license, so the examples run in evaluation mode, and some tests may fail because of the evaluation limitations. To use your own license, apply it in the base classes of the examples (`ApiExampleBase.js`, `DocExampleBase.js`) before any Aspose.Words API calls.

2. **Q:** Which version of Node.js is required for the examples?  
   **A:** The examples require Node.js 14.17.0 or later. Using an older version may cause syntax errors or missing module support. You can verify your version with `node -v`.

3. **Q:** How can I run a single example test instead of all tests?  
   **A:** Use the Jest command with the `--findRelatedTests` option followed by the test file name, e.g., `jest --findRelatedTests ExBookmarks.test.js`. This runs only the specified test and its dependencies.

4. **Q:** What should I do if `npm test` fails with missing modules or other errors?  
   **A:** First run `npm install` in the **ApiExamples** or **DocExamples** folder to restore all required packages. If the problem persists, delete the `node_modules` folder and the `package-lock.json` file, then run `npm install` again. Ensure you have an active internet connection and that your proxy settings (if any) allow npm to download packages.  