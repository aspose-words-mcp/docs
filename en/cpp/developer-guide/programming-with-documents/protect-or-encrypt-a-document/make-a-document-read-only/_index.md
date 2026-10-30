---
title: Make a Document Read-Only in C++
second_title: Aspose.Words for C++
articleTitle: Make a Document Read-Only
linktitle: Make a Document Read-Only
description: "Make your document read-only so that the content can be copied or read, but not modified."
type: docs
weight: 10
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/make-a-document-read-only/
aliases:
- /cpp/document-protection/
- /cpp/open-a-document-read-only/
timestamp: 2025-12-30-12-07-05
---

Sometimes, you may have a document that needs a review, but you do not want reviewers to randomly modify your content. Aspose.Words allows you to make the permission of your document read-only so that the content can be copied or read, but not modified. This will prevent content from being removed or added to your document.

{{% alert color="primary" %}}

Applying the read-only option to your document does not prevent someone from creating a new copy of it and saving it with another name.

{{% /alert %}}

This article explains how to make a document read-only.

## How to Make a Document Read-Only

Aspose.Words has the public class [WriteProtection](https://reference.aspose.com/words/cpp/aspose.words.settings/writeprotection/) that specifies write protection settings for a document. You do not create instances of this class directly.

Write protection shows whether the author has recommended opening a document as read-only and/or requiring a password to modify the document.

Aspose.Words allows you to make a document read-only to restrict editing by using the [get_ReadOnlyRecommended()](https://reference.aspose.com/words/cpp/aspose.words.settings/writeprotection/get_readonlyrecommended/) property and the [SetPassword](https://reference.aspose.com/words/cpp/aspose.words.settings/writeprotection/setpassword/) method.

{{% alert color="primary" %}}

In Microsoft Word, you can create a Read-Only document in a similar way using both:

* “Always Open Read-Only” (File → Info → Protect Document)
* "Password to modify" (Save As → Tools → General Options → Password)

{{% /alert %}}

{{% alert color="primary" %}}

Users can also restrict document editing by selecting [ProtectionType](https://reference.aspose.com/words/cpp/aspose.words/protectiontype/) as **ReadOnly**, but this is another feature that provides more advanced protection capabilities. There is such a function in Microsoft Word, respectively, it is implemented in Aspose.Words.

**ProtectionType** will be described in detail in one of the following articles – “Restrict Document Editing”.

{{% /alert %}}

The **ReadOnlyRecommended** property is password‑secured, so if you do not set a password before applying the **ReadOnlyRecommended** property, then other users can simply open the document as if it were unprotected. You access the document protection settings and set a write protection password via the **SetPassword** method.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security.

{{% /alert %}}

If you need to check if a document has a write protection password that restricts it from editing, you can use the [get_IsWriteProtected()](https://reference.aspose.com/words/cpp/aspose.words.settings/writeprotection/get_iswriteprotected/) property.

The following code example shows how to make a document read-only:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-ReadOnlyProtection.h" >}}

## Remove Read-Only Restriction

If you do not want a user to open your document as read-only, you can simply set the **ReadOnlyRecommended** property to *false*.

The following code example shows how to remove read-only access for a document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Protect or Encrypt Document-Document protection-RemoveReadOnlyRestriction.h" >}}

------

## FAQ

1. **Q:** How do I make a document read‑only with a password?  
   **A:** Load the document, call `doc->get_WriteProtection()->set_ReadOnlyRecommended(true);` and then `doc->get_WriteProtection()->SetPassword(u"yourPassword");`. Finally, save the document. The password protects the read‑only recommendation.

2. **Q:** Can I check whether a document is currently write‑protected?  
   **A:** Yes. Use `doc->get_WriteProtection()->get_IsWriteProtected()`; it returns `true` if a write‑protection password has been set.

3. **Q:** How can I remove the read‑only recommendation from an existing document?  
   **A:** Call `doc->get_WriteProtection()->set_ReadOnlyRecommended(false);`, then save the document.

4. **Q:** Is the read‑only password a security feature?  
   **A:** The password is stored as a document property and can be removed by users who can edit the document's metadata. It deters casual editing but should not be considered strong security.

5. **Q:** Are Aspose.Words licenses backward compatible with older library versions?  
   **A:** Yes. An Aspose.Words license file works with earlier versions of the library, provided the license file format has not changed. However, features introduced in newer versions will not be available when using older library releases.
