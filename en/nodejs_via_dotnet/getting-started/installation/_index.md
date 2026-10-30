---
title: Installation
second_title: Aspose.Words for Node.js via .NET
articleTitle: Installation
linktitle: Installation
description: "Install Aspose.Words for Node.js using npm."
type: docs
weight: 10
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/installation/
aliases: [/nodejs/installation/]
timestamp: 2025-04-18-01-01-01
---

Make sure your machine meets the [system requirements](/words/nodejs-net/system-requirements/) before you begin.

This article explains how to install Aspose.Words for Node.js via .NET on your computer.

[npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) is the easiest way to download and install [Aspose.Words for Node.js via .NET](https://www.npmjs.com/package/@aspose/words) APIs. To do this run the following command:

`npm add @aspose/words`

Once the module is installed, you can use it fom your Node.js code:

{{< highlight js >}}
const aw = require('@aspose/words');

// Create a Word document.
var doc = new aw.Document();

// Use a DocumentBuilder instance to add content to the file.
var builder = new aw.DocumentBuilder(doc);

// Write a new paragraph to the document.
builder.writeln('This is an example of a Word document created in Node.js');

// Save it as a DOCX file. The output format is automatically determined by the filename extension.
doc.save('OutputWordDocument.docx');
{{< /highlight >}}
