---
title: Restrict Document Editing in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Restrict Document Editing
linktitle: Restrict Document Editing
description: "Restrict editing a document by setting a restriction type using Node.js. You can also remove protection and make unrestricted editable regions."
type: docs
weight: 30
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/restrict-document-editing/
timestamp: 2025-07-09-10-05-05
---

Sometimes you may need to limit the ability to edit a document and only allow certain actions with it. This can be useful to prevent other people from editing sensitive and confidential information in your document.

Aspose.Words allows you to restrict editing a document by setting a restriction type. In addition, Aspose.Words also enables you to specify write protection settings for a document.

This article explains how to use Aspose.Words to select a restriction type, how to add or remove protection, and how to make unrestricted editable regions.

## Select Editing Restriction Type  

Aspose.Words allows you to control the way you restrict the content using the [ProtectionType](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/) enumeration parameter. This will enable you to select an exact type of protection such as the following:

* [AllowOnlyComments](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/)
* [AllowOnlyFormFields](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/)
* [AllowOnlyRevisions](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/)
* [ReadOnly](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/)
* [NoProtection](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/)

All types are password‑secured, and if this password is not entered correctly, a user will not be able to legally change the content of your document. Thus, if your document is returned to you without a requirement to provide the necessary password, this is a sign that something is wrong.

If you did not set a password when choosing the security type, other users can simply ignore the protection of your document.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security. The [Document.unprotect](https://reference.aspose.com/words/nodejs-net/aspose.words/document/unprotect/) method shows just that.

{{% /alert %}}

## Add Document Protection  

Adding protection to your document is a simple process, as all you need to do is apply one of the protection methods detailed in this section.

Aspose.Words allows you to protect your documents from changes using the [Document.protect](https://reference.aspose.com/words/nodejs-net/aspose.words/document/protect/) method. This method is not a security feature and does not encrypt a document.

{{% alert color="primary" %}}

In Microsoft Word, you can restrict editing in a similar way using both:

* Restrict Editing (File → Info → Protect Document)
* Alternative feature – “Restrict Editing” (Review → Protect → Restrict Editing)

{{% /alert %}}

The following code example shows how to add password protection to your document:

{{< gist "aspose-words-gists" "d9e52f106d399d80f5df382419349f58" "password-protection.js" >}}

The following code example shows how to restrict editing in a document so only editing in form fields is possible:

{{< gist "aspose-words-gists" "d9e52f106d399d80f5df382419349f58" "allow-only-form-fields-protect.js" >}}

## Remove Document Protection  

Aspose.Words allows you to remove protection from a document with simple and direct document modification. You can either remove the document protection without knowing the actual password or provide the correct password to unlock the document by using the [unprotect](https://reference.aspose.com/words/nodejs-net/aspose.words/document/unprotect/) method. Both removing ways have no difference.

The following code example shows how to remove protection from your document:

{{< gist "aspose-words-gists" "d9e52f106d399d80f5df382419349f58" "remove-document-protection.js" >}}

## Specify Unrestricted Editable Regions  

You can restrict editing of your document and at the same time allow changes to selected parts of it. So, anyone who opens your document will be able to access these unrestricted parts and make changes to the content.

Aspose.Words allows you to mark the parts that can be changed in your document using the [startEditableRange](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/starteditablerange/) and [endEditableRange](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/endeditablerange/) methods.

The following code example shows how to mark the whole document as read‑only and specify editable regions in it:

{{< gist "aspose-words-gists" "d9e52f106d399d80f5df382419349f58" "unrestricted-editable-regions.js" >}}

You can also choose different document editing restrictions for different sections.

The following code example shows how to add a restriction for the entire document, and then remove the restriction for one of the sections:

{{< gist "aspose-words-gists" "d9e52f106d399d80f5df382419349f58" "unrestricted-section.js" >}}

------  

## FAQ  

1. **Q:** How do I apply password protection to a document in Node.js?  
   **A:** Use the `Document.protect` method, passing the desired `ProtectionType` and a password string. The password is stored in the document properties and will be required to modify the protected content.  

2. **Q:** Can I remove protection from a document without knowing the password?  
   **A:** Yes. `Document.unprotect()` without arguments removes the protection regardless of the password. `unprotect(password)` removes it only when the password is correct (otherwise it returns `false`). The password only prevents users from removing the protection in Microsoft Word; it does not encrypt the document.  

3. **Q:** How can I determine whether a document is protected and which protection type is applied?  
   **A:** Check the `Document.protectionType` property. It returns a value from the `ProtectionType` enumeration, such as `ReadOnly`, `AllowOnlyFormFields`, or `NoProtection`.  

4. **Q:** How do I create unrestricted editable regions inside a read‑only document?  
   **A:** Use a `DocumentBuilder` to call `startEditableRange` before the region and `endEditableRange` after it. Content inside this range can be edited even when the rest of the document is read‑only.  

5. **Q:** Is it possible to change the protection type of an already protected document?  
   **A:** Yes. Call `Document.protect` with the new `ProtectionType` (and password). It replaces the current protection, so you do not need to call `Document.unprotect` first.  