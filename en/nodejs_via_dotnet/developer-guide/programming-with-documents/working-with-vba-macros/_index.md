---
title: Working with VBA Macros in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with VBA Macros
linktitle: Working with VBA Macros
description: "Create, read, write, clone, and manage VBA macros in a document using Node.js."
type: docs
weight: 410
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-vba-macros/
timestamp: 2025-07-09-10-05-05
---

Visual Basic for Applications (VBA) for Microsoft Word is a simple but powerful programming language that can be used to extend the functionality. Aspose.Words API provides three classes to get access to the VBA project source code:

- The [VbaProject](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbaproject/) class provides access to VBA project information
- The [VbaModuleCollection](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodulecollection/) class returns the collection of VBA project modules
- The [VbaModule](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodule/) class provides access to the VBA project module
- The [VbaModuleType](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamoduletype/) enumeration defines the types of a model in a VBA project. The module can be a procedural module, document module, class module, or designer module

## Create a VBA Project

Aspose.Words API provides the [vbaProject](https://reference.aspose.com/words/nodejs-net/aspose.words/document/vbaproject/) property to get or set [VbaProject](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbaproject/) in the document.

The following code example demonstrates how to create a VBA project and VBA Module along with basic properties e.g. [name](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodule/name/) and [type](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodule/type/):

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "create-vba-project.js" >}}

## Read Macros

Aspose.Words also provides users with the ability to read VBA macros.

The following code example shows how to read VBA Macros from the document:

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "read-vba-macros.js" >}}

## Write or Modify Macros

Using Aspose.Words, users can modify VBA macros.

The following code example shows how to modify VBA Macros using the [sourceCode](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodule/sourceCode/) property:

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "modify-vba-macros.js" >}}

## Clone VBA Project

With Aspose.Words it is also possible to clone VBA projects.

The following code example shows how to clone the VBA Project using the [clone](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodule/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "clone-vba-project.js" >}}

## Clone VBA Module

You can also clone VBA modules if needed.

The following code example shows how to clone the VBA Module using the [clone](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbamodule/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "clone-vba-module.js" >}}

## Work with the VBA Project References

Aspose.Words API provides [VbaReferenceCollection](https://reference.aspose.com/words/nodejs-net/aspose.words.vba/vbareferencecollection/) class to work with VBA Project References representing a collection of VBA project references.

The following code example shows how to remove some references from the collection of references from a VBA project:

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "remove-vba-references.js" >}}

{{< gist "aspose-words-gists" "65a1b9bae9592a992d97821378084e93" "get-lib-id-and-reference-path.js" >}}
