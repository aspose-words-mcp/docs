---
title: Work with Office Add-ins in Java
second_title: Aspose.Words for Java
articleTitle: Work with Office Add-ins
linktitle: Work with Office Add-ins
description: "Aspose.Words for Java provides various classes for working with Office Add-ins. You can add Task Pane via web extension and customize the pane and extension properties."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/work-with-office-add-ins/
aliases: [/java/working-with-web-extensions/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with Office Add-ins that incorporate Aspose.Words.

{{% /alert %}}

Sometimes you might want to give access to interface controls that run code to modify documents. Aspose.Words API provides the `WebExtensions` namespace, which grants various classes to customize elements and attributes extending the XML vocabulary for representing Office Add-ins.

WebExtensions namespace can be conditionally divided into:

* Objects for working with the task pane
* Objects for working with web extensions

## Using Task Panes

The task panes are interface surfaces that are displayed on the right side of the window in Microsoft Word. Task pane allows users to access interface controls that can run code to modify documents.

For example, using Aspose.Words API, you can add a task pane add-in and customize its appearance.

## Using Web Extensions

Web Extensions are tools that expand the capabilities of Office applications and interact with Office document content. Web Extensions provide additional functionality to Office clients for improving user experience.

Aspose.Words provides the ability to add Web Extensions of the Task Pane type using the [WebExtension](https://reference.aspose.com/words/java/com.aspose.words/webextension/) and [TaskPane](https://reference.aspose.com/words/java/com.aspose.words/taskpane/) classes, and also allows you to customize the pane and extension properties.

The following code example shows how to create task panes and add to web extension task panes with basic properties:

{{< gist "aspose-words-gists" "b91d438dcc82b6b4a3c8db34ad732c7d" "web-extension-task-panes.java" >}}

To see a list of task pane add‑ins, use the [getWebExtensionTaskPanes()](https://reference.aspose.com/words/java/com.aspose.words/document/#getWebExtensionTaskPanes) property.

The following code example shows how to get such a list of add-ins:

{{< gist "aspose-words-gists" "b91d438dcc82b6b4a3c8db34ad732c7d" "get-list-of-addins.java" >}}

## FAQ

1. **Q:** How do I add a Task Pane add‑in to a Word document using Aspose.Words for Java?  
   **A:** Create a `TaskPane` object and add it to the document with `doc.getWebExtensionTaskPanes().add(taskPane)`. Then set up the add‑in through `taskPane.getWebExtension()`, e.g., `getReference().setId(...)`, `getReference().setStore(...)`, and `getReference().setStoreType(...)`. The API handles the required XML for the add‑in.

2. **Q:** Which class lets me retrieve the list of Task Pane add‑ins already present in a document?  
   **A:** Use the `Document.getWebExtensionTaskPanes()` property. It returns a `TaskPaneCollection` of `TaskPane` objects that represent each task pane defined in the document.

3. **Q:** Can I customize the appearance (size, visibility, docking state) of a Task Pane programmatically?  
   **A:** Partly. `TaskPane` has `setDockState`, `isVisible(boolean)`, `setWidth`, `setRow`, and `isLocked(boolean)`; there is no height setting. Set them on a `TaskPane` from `doc.getWebExtensionTaskPanes()`. These properties control how the pane is displayed in Word.

4. **Q:** Is it possible to add other types of Web Extensions (e.g., content add‑ins) with Aspose.Words for Java?  
   **A:** Aspose.Words currently supports only the Task Pane type of Web Extensions. For other extension types you would need to manipulate the underlying XML manually, which is not covered by the high‑level API.

5. **Q:** Do I need a licensed version of Aspose.Words to use Web Extensions?  
   **A:** Not to use the feature. Without a license, Aspose.Words for Java works in evaluation mode with full functionality, but it adds an evaluation watermark and limits the document size to a few hundred paragraphs. To remove these limitations, apply a license: `License license = new License(); license.setLicense("Aspose.Words.Java.lic");`.