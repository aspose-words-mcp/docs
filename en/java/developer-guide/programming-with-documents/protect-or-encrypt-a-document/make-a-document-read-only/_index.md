---
title: Make a Document Read-Only in Java
second_title: Aspose.Words for Java
articleTitle: Make a Document Read-Only
linktitle: Make a Document Read-Only
description: "Make your document read-only so that the content can be copied or read, but not modified using Java."
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/make-a-document-read-only/
aliases:
- /java/document-protection/
- /java/open-a-document-read-only/
timestamp: 2025-12-30-12-07-05
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to open a document in read-only mode programmatically.

{{% /alert %}}

Sometimes, you may have a document that needs a review, but you do not want reviewers to randomly modify your content. Aspose.Words allows you to make the permission of your document read-only so that the content can be copied or read, but not modified. This will prevent content from being removed or added to your document.

{{% alert color="primary" %}}

Applying the read-only option to your document does not prevent someone from creating a new copy of it and saving it with another name.

{{% /alert %}}

This article explains how to make a document read-only.

## How to Make a Document Read-Only

Aspose.Words has the public class [WriteProtection](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/) that specifies write protection settings for a document. You do not create instances of this class directly.

Write protection shows whether the author has recommended opening a document as read-only and/or requiring a password to modify the document.

Aspose.Words allows you to make a document read-only to restrict editing by using the [getReadOnlyRecommended()](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/#getReadOnlyRecommended) property and the [setPassword()](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/#setPassword-java.lang.String) method.

{{% alert color="primary" %}}

In Microsoft Word, you can create a Read-Only document in a similar way using both:

* “Always Open Read-Only” (File → Info → Protect Document)
* "Password to modify" (Save As → Tools → General Options → Password)

{{% /alert %}}

{{% alert color="primary" %}}

Users can also restrict document editing by selecting [ProtectionType](https://reference.aspose.com/words/java/com.aspose.words/protectiontype/) as **READ_ONLY**, but this is another feature that provides more advanced protection capabilities. There is such a function in Microsoft Word, respectively, it is implemented in Aspose.Words.

**ProtectionType** will be described in detail in one of the following articles – “Restrict Document Editing”.

{{% /alert %}}

The **getReadOnlyRecommended()** property is password‑secured, so if you do not set a password before applying the **getReadOnlyRecommended()** property, then other users can simply open the document as if it were unprotected. You access the document protection settings and set a write protection password via the **SetPassword** method.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security.

{{% /alert %}}

If you need to check if a document has a write protection password that restricts it from editing, you can use the [isWriteProtected()](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/#isWriteProtected) property.

The following code example shows how to make a document read-only:

{{< gist "aspose-words-gists" "577227450ada581e16ca7c050112e36d" "read-only-protection.java" >}}

## Remove Read-Only Restriction

If you do not want a user to open your document as read-only, you can simply set the **ReadOnlyRecommened** property to *false* or select **ProtectionType** as **NO_PROTECTION**.

The following code example shows how to remove read-only access for a document:

{{< gist "aspose-words-gists" "577227450ada581e16ca7c050112e36d" "remove-read-only-restriction.java" >}}

## Related APIs

- [WriteProtection](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/)  
- [WriteProtection.getReadOnlyRecommended()](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/#getReadOnlyRecommended)  
- [WriteProtection.setPassword](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/#setPassword-java.lang.String)  
- [WriteProtection.isWriteProtected](https://reference.aspose.com/words/java/com.aspose.words/writeprotection/#isWriteProtected)  
- [ProtectionType](https://reference.aspose.com/words/java/com.aspose.words/protectiontype/)

## FAQ

1. **Q:** How do I make a document read‑only with Aspose.Words for Java?  
   **A:** Load the document, obtain its `WriteProtection` object via `document.getWriteProtection()`, call `setReadOnlyRecommended(true)`, optionally call `setPassword("yourPassword")`, and then save the document. This flag tells Word to open the file in read‑only mode.

2. **Q:** Can I require a password to modify the document while still allowing read‑only access?  
   **A:** Yes. After enabling `getReadOnlyRecommended()`, call `writeProtection.setPassword("modifyPassword")`. Users can open the file without a password, but any attempt to edit will prompt for the password you supplied.

3. **Q:** How can I verify whether a document is write‑protected?  
   **A:** Use the `WriteProtection` object's `isWriteProtected()` property. It returns `true` when a write protection password is set; the read‑only recommendation alone does not make it `true`.

4. **Q:** How do I remove the read‑only recommendation or any write protection from a document?  
   **A:** Call `writeProtection.setReadOnlyRecommended(false)` and, to remove the password, `writeProtection.setPassword("")`. Then save the document. Document protection (`Document.protect` / `Document.unprotect`) is a separate feature and does not change write protection.