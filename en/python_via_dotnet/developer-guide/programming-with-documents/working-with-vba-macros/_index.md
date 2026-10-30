---
title: Working with VBA Macros in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with VBA Macros
linktitle: Working with VBA Macros
description: "Create, read, write, clone, and manage VBA macros in a document using Python."
type: docs
weight: 410
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-vba-macros/
aliases: [/python/working-with-vba-macros/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to create, read, modify, clone, and manage VBA macro projects and modules within Word documents, including handling project references.

{{% /alert %}}

Visual Basic for Applications (VBA) for Microsoft Word is a simple but powerful programming language that can be used to extend the functionality. Aspose.Words API provides three classes to get access to the VBA project source code:

- The [VbaProject](https://reference.aspose.com/words/python-net/aspose.words.vba/vbaproject/) class provides access to VBA project information
- The [VbaModuleCollection](https://reference.aspose.com/words/python-net/aspose.words.vba/vbamodulecollection/) class returns the collection of VBA project modules
- The [VbaModule](https://reference.aspose.com/words/python-net/aspose.words.vba/vbamodule/) class provides access to the VBA project module
- The [VbaModuleType](https://reference.aspose.com/words/python-net/aspose.words.vba/vbamoduletype/) enumeration defines the types of a model in a VBA project. The module can be a procedural module, document module, class module, or designer module

## Create a VBA Project

Aspose.Words API provides the [vba_project](https://reference.aspose.com/words/python-net/aspose.words/document/vba_project/) property to get or set VbaProject in the document.

The following code example demonstrates how to create a VBA project and VBA Module along with basic properties e.g. Name and Type:

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "create-vba-project.py" >}}

## Read Macros

Aspose.Words also provides users with the ability to read VBA macros.

The following code example shows how to read VBA Macros from the document:

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "read-vba-macros.py" >}}

## Write or Modify Macros

Using Aspose.Words, users can modify VBA macros.

The following code example shows how to modify VBA Macros using the [source_code](https://reference.aspose.com/words/python-net/aspose.words.vba/vbamodule/source_code/) property:

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "modify-vba-macros.py" >}}

## Clone VBA Project

With Aspose.Words it is also possible to clone VBA projects.

The following code example shows how to clone the VBA Project using the [clone](https://reference.aspose.com/words/python-net/aspose.words.vba/vbaproject/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "clone-vba-project.py" >}}

## Clone VBA Module

You can also clone VBA modules if needed.

The following code example shows how to clone the VBA Module using the [clone](https://reference.aspose.com/words/python-net/aspose.words.vba/vbamodule/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "clone-vba-module.py" >}}

## Work with the VBA Project References

Aspose.Words API provides the [VbaReferenceCollection](https://reference.aspose.com/words/python-net/aspose.words.vba/vbareferencecollection/) class to work with VBA Project References representing a collection of VBA project references.

The following code example shows how to remove some references from the collection of references from a VBA project:

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "remove-vba-references.py" >}}

{{< gist "aspose-words-gists" "50526c04e8d563c4cef8678e5c28b442" "get-lib-id-and-reference-path.py" >}}