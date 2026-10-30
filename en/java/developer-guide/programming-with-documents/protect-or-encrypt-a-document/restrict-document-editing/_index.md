---
title: Restrict Document Editing in Java
second_title: Aspose.Words for Java
articleTitle: Restrict Document Editing
linktitle: Restrict Document Editing
description: "Restrict editing a document by setting a restriction type using Java. You can also remove protection and make unrestricted editable regions."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/restrict-document-editing/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to restrict editing of a document or selected parts.

{{% /alert %}}

Sometimes you may need to limit the ability to edit a document and only allow certain actions with it. This can be useful to prevent other people from editing sensitive and confidential information in your document.

Aspose.Words allows you to restrict editing a document by setting a restriction type. In addition, Aspose.Words also enables you to specify write protection settings for a document.

This article explains how to use Aspose.Words to select a restriction type, how to add or remove protection, and how to make unrestricted editable regions.

## Select Editing Restriction Type

Aspose.Words allows you to control the way you restrict the content using the [ProtectionType](https://reference.aspose.com/words/java/com.aspose.words/protectiontype/) enumeration parameter. This will enable you to select an exact type of protection such as the following:

* AllowOnlyComments
* AllowOnlyFormFields
* AllowOnlyRevisions
* ReadOnly
* NoProtection

All types are password-secured, and if this password is not entered correctly, a user will not be able to legally change the content of your document. Thus, if your document is returned to you without a requirement to provide the necessary password, this is a sign that something is wrong.

If you did not set a password when choosing the security type, other users can simply ignore the protection of your document.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security. The [unprotect()](https://reference.aspose.com/words/java/com.aspose.words/document/#unprotect) method shows just that.

{{% /alert %}}

## Add Document Protection

Adding protection to your document is a simple process, as all you need to do is apply one of the protection methods detailed in this section.

Aspose.Words allows you to protect your documents from changes using the [protect()](https://reference.aspose.com/words/java/com.aspose.words/document/#protect-int) method. This method is not a security feature and does not encrypt a document.

{{% alert color="primary" %}}

In Microsoft Word, you can restrict editing in a similar way using both:

* Restrict Editing (File → Info → Protect Document)
* Alternative feature – “Restrict Editing” (Review → Protect → Restrict Editing)

{{% /alert %}}

The following code example shows how to add password protection to your document:

{{< gist "aspose-words-gists" "d0b170eaed36360c47a6522c22d7e568" "password-protection.java" >}}

The following code example shows how to restrict editing in a document so only editing in form fields is possible:

{{< gist "aspose-words-gists" "d0b170eaed36360c47a6522c22d7e568" "allow-only-form-fields-protect.java" >}}

## Remove Document Protection

Aspose.Words allows you to remove protection from a document with simple and direct document modification. You can either remove the document protection without knowing the actual password or provide the correct password to unlock the document by using the [unprotect()](https://reference.aspose.com/words/java/com.aspose.words/document/#unprotect) method. Both removing ways have no difference.

The following code example shows how to remove protection from your document:

{{< gist "aspose-words-gists" "d0b170eaed36360c47a6522c22d7e568" "remove-document-protection.java" >}}

## Specify Unrestricted Editable Regions

You can restrict editing of your document and at the same time allow changes to selected parts of it. So, anyone who opens your document will be able to access these unrestricted parts and make changes to the content.

Aspose.Words allows you to mark the parts that can be changed in your document using the [startEditableRange()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#startEditableRange) and [endEditableRange()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endEditableRange) methods.

The following code example shows how to mark the whole document as read-only and specify editable regions in it:

{{< gist "aspose-words-gists" "d0b170eaed36360c47a6522c22d7e568" "unrestricted-editable-regions.java" >}}

You can also choose different document editing restrictions for different sections.

The following code example shows how to add a restriction for the entire document, and then remove the restriction for one of the sections:

{{< gist "aspose-words-gists" "d0b170eaed36360c47a6522c22d7e568" "unrestricted-section.java" >}}

## Limitations and Considerations

- Aspose.Words protection is not encryption — it stores only a password hash in the document properties and does not secure the document content.
- Protection does not prevent programmatic access or modification — any Aspose.Words application can remove protection or modify the document regardless of restrictions.
- The `protect` method only sets a metadata flag; it does not prevent changes via API calls such as `Document.unprotect` or `DocumentBuilder.startEditableRange`.
- Editable ranges do not override section-level protection settings — they apply only to the document-level protection state and require correct section break types to function as expected. 

## Related APIs

- [ProtectionType](https://reference.aspose.com/words/java/com.aspose.words/protectiontype/)
- [Document.protect(int, String)](https://reference.aspose.com/words/java/com.aspose.words/document/#protect-int-java.lang.String)
- [Document.unprotect()](https://reference.aspose.com/words/java/com.aspose.words/document/#unprotect)
- [DocumentBuilder.startEditableRange()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#startEditableRange)
- [DocumentBuilder.endEditableRange()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endEditableRange)

## FAQ

1. **Q:** How do I apply password protection to a document?  
   **A:** Use the `Document.protect(ProtectionType, password)` method, passing the desired `ProtectionType` and a string password. The password is stored in the document and is required to remove or change the protection.

2. **Q:** Can I remove protection without knowing the password?  
   **A:** Yes. Call `Document.unprotect()` without arguments; this removes protection regardless of the password. Use the overload `unprotect(String password)` only when you want to verify the password before removing protection.

3. **Q:** Which restriction type allows users to fill only form fields?  
   **A:** Use `ProtectionType.ALLOW_ONLY_FORM_FIELDS` when calling `Document.protect`. This lets users edit form fields while keeping the rest of the document read‑only.

4. **Q:** How can I create editable regions inside a read-only document?  
   **A:** With a `DocumentBuilder`, call `startEditableRange()` before the region and `endEditableRange()` after it. Content inside this range can be edited even when the document is protected with `ProtectionType.READ_ONLY`.

5. **Q:** How can I check whether a document is currently protected?  
   **A:** Inspect the `Document.getProtectionType()` property. If it returns `ProtectionType.NO_PROTECTION`, the document is unprotected; otherwise it returns the active restriction type.
