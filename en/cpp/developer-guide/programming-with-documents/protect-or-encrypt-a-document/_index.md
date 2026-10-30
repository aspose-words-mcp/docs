---
title: Protect or Encrypt a Document in C++
second_title: Aspose.Words for C++
articleTitle: Protect or Encrypt a Document
linktitle: Protect or Encrypt a Document
description: "Aspose.Words for C++ provides Read-Only, Encrypt a Document, Restrict Editing, and Digital Signatures for document protection. Aspose.Words supports most Word protection options."
type: docs
weight: 50
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/protect-or-encrypt-a-document/
timestamp: 2025-12-30-12-07-05
---

The main reason to protect or encrypt a document is to apply more control over who can access the document or who can edit it. Applying protection to your documents, you avoid common risks such as copying or modifying documents without permission, as well as data leakage.

Some of the most popular formats when working with documents are Microsoft Word formats or formats that can be exported from Word. That's why many users are interested in the same document protection options that Microsoft Word provides. Despite the complexity of these options, Aspose.Words supports most of them, so it makes it an excellent solution for working with documents.

This article describes what options Aspose.Words provides for document protection and how these options are presented in the familiar Microsoft Word user interface. In the child articles of the current section, you can learn more about the listed protection functions with all the necessary properties and methods.

## Document Protection Options

Aspose.Words currently provides the document features listed in the table below. You can find the details on each of the features in the corresponding child article in the current section.

| Aspose.Words protection feature | Corresponding child article    | Corresponding MS Word feature                                |
| ------------------------------- | ------------------------------ | ------------------------------------------------------------ |
| Read-Only                       | “Make a Document Read-Only”    | Always Open Read-Only (File → Info → Protect Document)<br />Alternative feature: "Password to modify" (Save As → Tools → General Options → Password) |
| Encrypt a Document              | “Encrypt a Document”           | Encrypt with Password (File → Info → Protect Document)<br />Alternative feature: "Password to open" (Save As → Tools → General Options → Password) |
| Restrict Editing                | “Restrict Document Editing”    | Restrict Editing (File – Info – Protect Document)<br />Alternative feature: "Restrict Editing" (Review → Protect → Restrict Editing) |
| Digital Signatures              | “Work with Digital Signatures” | Add a Digital Signature (File → Info → Protect Document)     |

{{% alert color="primary" %}}

Note that Aspose.Words does not support both Microsoft Word features “Mark as Final” and “Restrict Access”.

{{% /alert %}}

{{% alert color="primary" %}}

Note that the exact names of features and the paths to them in Microsoft Word may differ depending on the version, we try to provide users with the latest data.

{{% /alert %}}

## See Also

* Try our [Free online documents unlocker](https://products.aspose.app/words/unlock)

------ 

## FAQ

1. **Q:** How can I encrypt a Word document with a password using Aspose.Words for C++?  
   **A:** Set a password in the save options of the target format and save the document; for DOCX use `OoxmlSaveOptions::set_Password`. `Document::Protect` only restricts editing, it does not encrypt the file. Example:  

   ```cpp
   System::SharedPtr<Aspose::Words::Document> doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   auto saveOptions = System::MakeObject<Aspose::Words::Saving::OoxmlSaveOptions>(Aspose::Words::SaveFormat::Docx);
   saveOptions->set_Password(u"MyOpenPassword");
   doc->Save(u"encrypted.docx", saveOptions);
   ```

2. **Q:** How do I make a document read‑only without requiring a password?  
   **A:** Use the `Protect` method with the `ReadOnly` protection type and pass an empty string for the password. The document can be opened by anyone but cannot be edited.  

   ```cpp
   System::SharedPtr<Aspose::Words::Document> doc = System::MakeObject<Aspose::Words::Document>(u"input.docx");
   doc->Protect(Aspose::Words::ProtectionType::ReadOnly);
   doc->Save(u"readonly.docx");
   ```

3. **Q:** How can I restrict editing to comments or tracked changes only?  
   **A:** Choose the appropriate `ProtectionType`—`ProtectionType::AllowOnlyComments` or `ProtectionType::AllowOnlyRevisions`—when calling `Document::Protect`. This limits the user to adding comments or using tracked changes, respectively.  

   ```cpp
   // Restrict to comments only
   doc->Protect(Aspose::Words::ProtectionType::AllowOnlyComments);
   // Restrict to tracked changes only
   doc->Protect(Aspose::Words::ProtectionType::AllowOnlyRevisions);
   ```

4. **Q:** How do I add a digital signature to a document with Aspose.Words for C++?  
   **A:** Use `DigitalSignatureUtil::Sign`, providing the source file name, the destination file name, and a `CertificateHolder` created from a PKCS#12 certificate and its password. The method signs files, not a loaded `Document`.  

   ```cpp
   auto certHolder = Aspose::Words::DigitalSignatures::CertificateHolder::Create(u"mycert.pfx", u"certPassword");
   Aspose::Words::DigitalSignatures::DigitalSignatureUtil::Sign(u"input.docx", u"signed.docx", certHolder);
   ```

5. **Q:** How can I apply a license to remove evaluation limitations?  
   **A:** Create a `License` object and call `SetLicense` with the path to your `.lic` file before using any Aspose.Words functionality.  

   ```cpp
   System::SharedPtr<Aspose::Words::License> license = System::MakeObject<Aspose::Words::License>();
   license->SetLicense(u"Aspose.Words.CPP.lic");
   // Now the library works in licensed mode
   ```

------