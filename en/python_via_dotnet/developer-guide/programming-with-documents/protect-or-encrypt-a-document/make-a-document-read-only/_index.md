---
title: Make a Document Read-Only in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Make a Document Read-Only
linktitle: Make a Document Read-Only
description: "Make your document read-only so that the content can be copied or read, but not modified using Python."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/make-a-document-read-only/
aliases:
 - /python/document-protection/
 - /python/open-a-document-read-only/
 - /python-net/open-a-document-read-only/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to apply and remove read‑only protection on a document using Aspose.Words for Python via .NET, including code examples for setting a password, enabling the read‑only recommendation, and applying protection types.

{{% /alert %}}

Sometimes, you may have a document that needs a review, but you do not want reviewers to randomly modify your content. Aspose.Words allows you to make the permission of your document read-only so that the content can be copied or read, but not modified. This will prevent content from being removed or added to your document.

{{% alert color="primary" %}}

Applying the read-only option to your document does not prevent someone from creating a new copy of it and saving it with another name.

{{% /alert %}}

This article explains how to make a document read-only.

## How to Make a Document Read-Only

Aspose.Words has the public class [WriteProtection](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/) that specifies write protection settings for a document. You do not create instances of this class directly.

Write protection shows whether the author has recommended opening a document as read-only and/or requiring a password to modify the document.

Aspose.Words allows you to make a document read-only to restrict editing by using the [read_only_recommended](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/read_only_recommended/) property and the [set_password](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/set_password/) method.

{{% alert color="primary" %}}

In Microsoft Word, you can create a Read-Only document in a similar way using both:

* “Always Open Read-Only” (File → Info → Protect Document)
* "Password to modify" (Save As → Tools → General Options → Password)

{{% /alert %}}

{{% alert color="primary" %}}

Users can also restrict document editing by selecting [ProtectionType](https://reference.aspose.com/words/python-net/aspose.words/protectiontype/) as **READ_ONLY**, but this is another feature that provides more advanced protection capabilities. There is such a function in Microsoft Word, respectively, it is implemented in Aspose.Words.

**ProtectionType** will be described in detail in one of the following articles – “Restrict Document Editing”.

{{% /alert %}}

The **read_only_recommended** property is password‑secured, so if you do not set a password before applying the **read_only_recommended** property, then other users can simply open the document as if it were unprotected. You access the document protection settings and set a write protection password via the **set_password** method.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security.

{{% /alert %}}

If you need to check if a document has a write protection password that restricts it from editing, you can use the [is_write_protected](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/is_write_protected/) property.

The following code example shows how to make a document read-only:

{{< gist "aspose-words-gists" "4240df05013243baa2dbfb7728108b89" "read-only-protection.py" >}}

## Remove Read-Only Restriction

If you do not want a user to open your document as read-only, you can simply set the **read_only_recommended** property to *false* or select **ProtectionType** as **NO_PROTECTION**.

The following code example shows how to remove read-only access for a document:

{{< gist "aspose-words-gists" "4240df05013243baa2dbfb7728108b89" "remove-read-only-restriction.py" >}}

## Related APIs

- [WriteProtection](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/)  
- [WriteProtection.read_only_recommended](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/read_only_recommended/)  
- [WriteProtection.set_password](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/set_password/)  
- [WriteProtection.is_write_protected](https://reference.aspose.com/words/python-net/aspose.words.settings/writeprotection/is_write_protected/)  
- [ProtectionType](https://reference.aspose.com/words/python-net/aspose.words/protectiontype/) 

## FAQ

1. **Q:** How do I make a document read‑only using Aspose.Words for Python?  
   **A:** Set a password with `doc.write_protection.set_password("yourPassword")`, enable the read‑only recommendation with `doc.write_protection.read_only_recommended = True`, and then apply the protection using `doc.protect(aw.ProtectionType.READ_ONLY)`.

2. **Q:** Is a password required to use the `read_only_recommended` property?  
   **A:** No, the property can be set without a password, but without a password any user can remove the recommendation by clearing the property. Adding a password makes the setting harder to bypass.

3. **Q:** What is the difference between `read_only_recommended` and `doc.protect(ProtectionType.READ_ONLY)`?  
   **A:** `read_only_recommended` only suggests that the document should be opened as read‑only; it does not enforce protection. `doc.protect(ProtectionType.READ_ONLY)` actually enforces the read‑only mode and, when combined with a password, prevents editing unless the password is supplied.

4. **Q:** How can I remove the read‑only restriction from a document?  
   **A:** Set `doc.write_protection.read_only_recommended = False` and call `doc.protect(aw.ProtectionType.NO_PROTECTION)`. This clears both the recommendation and any applied protection.

5. **Q:** Does making a document read‑only stop users from copying its content?  
   **A:** No. Read‑only protection only prevents modifications to the document. Users can still select, copy, and paste the content unless additional restrictions (e.g., encryption) are applied.