---
title: Working with VBA Macros in C++
second_title: Aspose.Words for C++
articleTitle: Working with VBA Macros
linktitle: Working with VBA Macros
description: "Working with document VBA projects using C++."
type: docs
weight: 410
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-vba-macros/
timestamp: 2024-01-30-16-22-34
---

Visual Basic for Applications (VBA) for Microsoft Word is a simple but powerful programming language that can be used to extend the functionality. Aspose.Words API provides three classes to get access to the VBA project source code:

- The [VbaProject](https://reference.aspose.com/words/cpp/aspose.words.vba/vbaproject/) class provides access to VBA project information
- The [VbaModuleCollection](https://reference.aspose.com/words/cpp/aspose.words.vba/vbamodulecollection/) class returns the collection of VBA project modules
- The [VbaModule](https://reference.aspose.com/words/cpp/aspose.words.vba/vbamodule/) class provides access to the VBA project module

## Create a VBA Project

Aspose.Words API provides `Document::VbaProject` property to get or set VbaProject in the document.

The following code example demonstrates how to create a VBA project and VBA Module along with basic properties e.g. Name and Type:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithVbaMacros-CreateVbaProject.cpp" >}}

## Read Macros

Aspose.Words also provides users with the ability to read VBA macros.

The following code example shows how to read VBA Macros from the document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithVbaMacros-ReadVbaMacros.cpp" >}}

## Write or Modify Macros

Using Aspose.Words, users can modify VBA macros.

The following code example shows how to modify VBA Macros using the [get_SourceCode()](https://reference.aspose.com/words/cpp/aspose.words.vba/vbamodule/get_sourcecode/) property:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithVbaMacros-ModifyVbaMacros.cpp" >}}

## Clone VBA Project

With Aspose.Words it is also possible to clone VBA projects.

The following code example shows how to clone the VBA Project using the [Clone](https://reference.aspose.com/words/cpp/aspose.words.vba/vbamodule/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithVbaMacros-CloneVbaProject.cpp" >}}

## Clone VBA Module

You can also clone VBA modules if needed.

The following code example shows how to clone the VBA Module using the [Clone](https://reference.aspose.com/words/cpp/aspose.words.vba/vbamodule/clone/) property which creates a copy of the existing project:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Loading-and-Saving-WorkingWithVbaMacros-CloneVbaModule.cpp" >}}


------ 

## FAQ

1. **Q:** How do I apply an Aspose.Words license when working with VBA macros in C++?  
   **A:** Load the license file using `auto license = System::MakeObject<Aspose::Words::License>(); license->SetLicense(u"Aspose.Words.CPP.lic");` before creating any `Document` objects. The license covers all features, including VBA project access, so the API will work without evaluation limitations.

2. **Q:** Can I clone an entire VBA project from one document to another?  
   **A:** Yes. Clone the source project and assign the copy to the target document with `targetDoc->set_VbaProject(sourceDoc->get_VbaProject()->Clone());`. This creates a deep copy of the project and all its modules.

3. **Q:** How can I read the source code of a specific VBA macro module?  
   **A:** Access the module through the collection: `auto module = doc->get_VbaProject()->get_Modules()->idx_get(u"Module1");` and then read the code with `System::String code = module->get_SourceCode();`. The returned string contains the full VBA source.

4. **Q:** Is it possible to modify a VBA macro's source code and save the changes back to the document?  
   **A:** Yes. After obtaining the `VbaModule`, call `module->set_SourceCode(newCode);` where `newCode` is a `String` containing the updated VBA code. Save the document afterwards to persist the changes.

5. **Q:** Are there any limitations when manipulating VBA macros with Aspose.Words for C++?  
   **A:** The API supports reading, writing, cloning, and deleting VBA projects and modules, but it does not execute VBA code. Also, the API cannot unlock password-protected VBA projects; use `VbaProject::get_IsProtected` to detect them.