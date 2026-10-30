---
title: Restrict Document Editing in C++
second_title: Aspose.Words for C++
articleTitle: Restrict Document Editing
linktitle: Restrict Document Editing
description: "Restrict editing a document by setting a restriction type using C++. You can also remove protection and make unrestricted editable regions."
type: docs
weight: 30
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/restrict-document-editing/
timestamp: 2024-01-27-14-07-04
---

Sometimes you may need to limit the ability to edit a document and only allow certain actions with it. This can be useful to prevent other people from editing sensitive and confidential information in your document.

Aspose.Words allows you to restrict editing a document by setting a restriction type. In addition, Aspose.Words also enables you to specify write protection settings for a document.

This article explains how to use Aspose.Words to select a restriction type, how to add or remove protection, and how to make unrestricted editable regions.

## Select Editing Restriction Type

Aspose.Words allows you to control the way you restrict the content using the [ProtectionType](https://reference.aspose.com/words/cpp/aspose.words/protectiontype/) enumeration parameter. This will enable you to select an exact type of protection such as the following:

* AllowOnlyComments
* AllowOnlyFormFields
* AllowOnlyRevisions
* ReadOnly
* NoProtection

All types are password‑secured, and if this password is not entered correctly, a user will not be able to legally change the content of your document. Thus, if your document is returned to you without a requirement to provide the necessary password, this is a sign that something is wrong.

If you did not set a password when choosing the security type, other users can simply ignore the protection of your document.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security. The [Unprotect](https://reference.aspose.com/words/cpp/aspose.words/document/unprotect/) method shows just that.

{{% /alert %}}

## Add Document Protection

Adding protection to your document is a simple process, as all you need to do is apply one of the protection methods detailed in this section.

Aspose.Words allows you to protect your documents from changes using the [Protect](https://reference.aspose.com/words/cpp/aspose.words/document/protect/) method. This method is not a security feature and does not encrypt a document.

{{% alert color="primary" %}}

In Microsoft Word, you can restrict editing in a similar way using both:

* Restrict Editing (File → Info → Protect Document)
* Alternative feature – “Restrict Editing” (Review → Protect → Restrict Editing)

{{% /alert %}}

The following code example shows how to add password protection to your document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-PasswordProtection.h" >}}

The following code example shows how to restrict editing in a document so only editing in form fields is possible:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-AllowOnlyFormFieldsProtect.h" >}}

## Remove Document Protection

Aspose.Words allows you to remove protection from a document with simple and direct document modification. You can either remove the document protection without knowing the actual password or provide the correct password to unlock the document by using the [Unprotect](https://reference.aspose.com/words/cpp/aspose.words/document/unprotect/) method. Both removing ways have no difference.

The following code example shows how to remove protection from your document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-RemoveDocumentProtection.h" >}}

## Specify Unrestricted Editable Regions

You can restrict editing of your document and at the same time allow changes to selected parts of it. So, anyone who opens your document will be able to access these unrestricted parts and make changes to the content.

Aspose.Words allows you to mark the parts that can be changed in your document using the [StartEditableRange](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/starteditablerange/) and [EndEditableRange](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/endeditablerange/) methods.

The following code example shows how to mark the whole document as read‑only and specify editable regions in it:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-UnrestrictedEditableRegions.h" >}}

You can also choose different document editing restrictions for different sections.

The following code example shows how to add a restriction for the entire document, and then remove the restriction for one of the sections:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-UnrestrictedSection.h" >}}

------ 

## FAQ

1. **Q:** How do I apply a password to protect a Word document using Aspose.Words for C++?  
   **A:** Create a `Document` object, then call `Protect` with the desired `ProtectionType` and a password string. The password is stored in the document and is required to remove or change the protection.  

   ```cpp
   System::SharedPtr<Aspose::Words::Document> doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   doc->Protect(Aspose::Words::ProtectionType::ReadOnly, u"MySecretPassword");
   doc->Save(u"protected.docx");
   ```

2. **Q:** Can I remove protection from a document if I don't know the password?  
   **A:** Yes. `Unprotect()` removes the protection even if the document is protected with a password. `Unprotect(password)` removes it only when the password is correct and returns `false` otherwise.

   ```cpp
   doc->Unprotect();                                  // removes protection without the password
   bool removed = doc->Unprotect(u"MySecretPassword"); // removes it only if the password is correct
   ```

3. **Q:** What is the difference between `ReadOnly` and `NoProtection` protection types?  
   **A:** `ReadOnly` makes the entire document non‑editable unless the correct password is supplied, while `NoProtection` means the document has no editing restrictions at all. `NoProtection` is the default state of a newly created document.

4. **Q:** How can I allow editing only in form fields while keeping the rest of the document read‑only?  
   **A:** Use the `Protect` method with `ProtectionType::AllowOnlyFormFields` and provide a password. Users will be able to fill in form fields but cannot modify any other content.

   ```cpp
   doc->Protect(Aspose::Words::ProtectionType::AllowOnlyFormFields, u"FormPassword");
   ```

5. **Q:** How do I define unrestricted editable regions inside a protected document?  
   **A:** After protecting the document, use `DocumentBuilder::StartEditableRange` and `DocumentBuilder::EndEditableRange` to mark the sections that should remain editable. These ranges can be nested and are identified by a unique ID.

   ```cpp
   System::SharedPtr<Aspose::Words::DocumentBuilder> builder = System::MakeObject<Aspose::Words::DocumentBuilder>(doc);
   auto rangeStart = builder->StartEditableRange();
   builder->Writeln(u"This part can be edited.");
   builder->EndEditableRange(rangeStart);
   ```