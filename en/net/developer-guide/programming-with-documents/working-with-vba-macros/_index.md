---
title: Working with VBA Macros in C#
second_title: Aspose.Words for .NET
articleTitle: Working with VBA Macros
linktitle: Working with VBA Macros
description: "Working with document VBA projects using C#."
type: docs
weight: 410
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-vba-macros/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with VBA macros, including enabling and modifying them.

{{% /alert %}}

Visual Basic for Applications (VBA) for Microsoft Word is a simple but powerful programming language that can be used to extend the functionality. Aspose.Words API provides three classes to get access to the VBA project source code:

- The [VBAProject](https://reference.aspose.com/words/net/aspose.words.vba/vbaproject/) class provides access to VBA project information
- The [VBAModuleCollection](https://reference.aspose.com/words/net/aspose.words.vba/vbamodulecollection/) class returns the collection of VBA project modules
- The [VbaModule](https://reference.aspose.com/words/net/aspose.words.vba/vbamodule/) class provides access to the VBA project module
- The [VbaModuleType](https://reference.aspose.com/words/net/aspose.words.vba/vbamoduletype/) enumeration defines the types of a model in a VBA project. The module can be a procedural module, document module, class module, or designer module

## Create a VBA Project

Aspose.Words API provides the [VbaProject](https://reference.aspose.com/words/net/aspose.words/document/vbaproject/) property to get or set VbaProject in the document.

The following code example demonstrates how to create a VBA project and VBA Module along with basic properties e.g. Name and Type:

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "create-vba-project.cs" >}}

## Read Macros

Aspose.Words also provides users with the ability to read VBA macros.

The following code example shows how to read VBA Macros from the document:

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "read-vba-macros.cs" >}}

## Write or Modify Macros

Using Aspose.Words, users can modify VBA macros.

The following code example shows how to modify VBA Macros using the [SourceCode](https://reference.aspose.com/words/net/aspose.words.vba/vbamodule/sourcecode/) property:

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "modify-vba-macros.cs" >}}

## Clone VBA Project

With Aspose.Words it is also possible to clone VBA projects.

The following code example shows how to clone the VBA Project using the [Clone](https://reference.aspose.com/words/net/aspose.words.vba/vbaproject/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "clone-vba-project.cs" >}}

## Clone VBA Module

You can also clone VBA modules if needed.

The following code example shows how to clone the VBA Module using the [Clone](https://reference.aspose.com/words/net/aspose.words.vba/vbamodule/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "clone-vba-module.cs" >}}

## Work with the VBA Project References

Aspose.Words API provides the [VbaReferenceCollection](https://reference.aspose.com/words/net/aspose.words.vba/vbareferencecollection/) class to work with VBA Project References representing a collection of VBA project references.

The following code example shows how to remove some references from the collection of references from a VBA project:

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "remove-vba-references.cs" >}}

{{< gist "aspose-words-gists" "d9bac4ed890f81ea3de392ecfeedbc55" "get-lib-id-and-reference-path.cs" >}}

------

## FAQ

1. **Q:** How can I create a new VBA project in a Word document using Aspose.Words for .NET?  
   **A:** Use the `Document.VbaProject` property to obtain a `VbaProject` instance, then add a new `VbaModule` to its `Modules` collection. Set the module's `Name` and `Type` (e.g., `VbaModuleType.ProceduralModule`) before saving the document.

2. **Q:** How do I read the source code of an existing VBA macro?  
   **A:** Retrieve the desired `VbaModule` from `Document.VbaProject.Modules` and access its `SourceCode` property. The property returns the macro's source as a string, which you can inspect or display.

3. **Q:** How can I modify or replace the source code of a VBA module?  
   **A:** After obtaining the `VbaModule`, assign a new string to its `SourceCode` property. Save the document afterwards to persist the changes in the VBA project.

4. **Q:** Is it possible to clone an entire VBA project or a single VBA module?  
   **A:** Yes. Both `VbaProject` and `VbaModule` implement a `Clone()` method that returns a deep copy. You can clone the project and assign it to another document, or clone individual modules and add them to the same or a different project.

5. **Q:** Do I need a separate Aspose.Words license to work with VBA macros?  
   **A:** No separate license is required. VBA macro manipulation is covered by the standard Aspose.Words for .NET license. Ensure your license file is correctly loaded in your application to avoid evaluation limitations.