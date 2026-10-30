---
title: Work with Office Add-ins in C#
second_title: Aspose.Words for .NET
articleTitle: Work with Office Add-ins
linktitle: Work with Office Add-ins
description: "Aspose.Words for .NET provides various classes for working with Office Add-ins using C#. You can add Task Pane via web extension and customize the pane and extension properties."
type: docs
weight: 50
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/work-with-office-add-ins/
aliases: [/net/work-with-web-extensions/]
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

Aspose.Words provides the ability to add Web Extensions of the Task Pane type using the [WebExtension](https://reference.aspose.com/words/net/aspose.words.webextensions/webextension/) and [TaskPane](https://reference.aspose.com/words/net/aspose.words.webextensions/taskpane/) classes, and also allows you to customize the pane and extension properties.

The following code example shows how to create task panes and add to web extension task panes with basic properties:

{{< gist "aspose-words-gists" "8c31c018ea71c92828223776b1a113f7" "web-extension-task-panes.cs" >}}

To see a list of task pane add‑ins, use the [WebExtensionTaskPanes](https://reference.aspose.com/words/net/aspose.words/document/webextensiontaskpanes/) property.

The following code example shows how to get such a list of add-ins:

{{< gist "aspose-words-gists" "8c31c018ea71c92828223776b1a113f7" "get-list-of-addins.cs" >}}

------

## FAQ
1. **Q:** How can I add a task pane add‑in to a Word document using Aspose.Words?  
   **A:** Create a `TaskPane` object and add it to the document with `doc.WebExtensionTaskPanes.Add(taskPane)`. Set its appearance properties (e.g., `DockState`, `IsVisible`, `Width`), then describe the add-in through `taskPane.WebExtension.Reference` (`Id`, `Version`, `StoreType`, `Store`).

2. **Q:** How do I retrieve the list of task pane add‑ins that are already attached to a document?  
   **A:** Use the `Document.WebExtensionTaskPanes` property, which returns a `TaskPaneCollection` of `TaskPane` objects. For each task pane, read `DockState`, `IsVisible`, `Width`, and `WebExtension.Reference.Id` (the add-in ID).

3. **Q:** Can I add more than one task pane to the same Word document?  
   **A:** Yes. Create another `TaskPane` and add it to `Document.WebExtensionTaskPanes`. Each task pane has its own add-in, which you configure through `taskPane.WebExtension`.