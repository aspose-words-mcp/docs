---
title: Make a Document Read-Only in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Make a Document Read-Only
linktitle: Make a Document Read-Only
description: "Make your document read-only so that the content can be copied or read, but not modified using Node.js."
type: docs
weight: 10
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/make-a-document-read-only/
aliases:
- /nodejs-net/open-a-document-read-only/
timestamp: 2025-12-30-12-07-05
---

Sometimes, you may have a document that needs a review, but you do not want reviewers to randomly modify your content. Aspose.Words allows you to make the permission of your document read-only so that the content can be copied or read, but not modified. This will prevent content from being removed or added to your document.

{{% alert color="primary" %}}

Applying the read-only option to your document does not prevent someone from creating a new copy of it and saving it with another name.

{{% /alert %}}

This article explains how to make a document read-only.

## Make a Document Read-Only

Aspose.Words has the public class [WriteProtection](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/) that specifies write protection settings for a document. You do not create instances of this class directly.

Write protection shows whether the author has recommended opening a document as read-only and/or requiring a password to modify the document.

Aspose.Words allows you to make a document read-only to restrict editing by using the [readOnlyRecommended](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/readOnlyRecommended/) property and the [setPassword](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/setPassword/) method.

{{% alert color="primary" %}}

In Microsoft Word, you can create a Read-Only document in a similar way using both:

* "Always Open Read-Only" (File → Info → Protect Document)
* "Password to modify" (Save As → Tools → General Options → Password)

{{% /alert %}}

{{% alert color="primary" %}}

Users can also restrict document editing by selecting [ProtectionType](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/) as [ReadOnly](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/), but this is another feature that provides more advanced protection capabilities. There is such a function in Microsoft Word, respectively, it is implemented in Aspose.Words.

[ProtectionType](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/) will be described in detail in one of the following articles – “Restrict Document Editing”.

{{% /alert %}}

The [readOnlyRecommended](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/readOnlyRecommended/) property is password-secured, so if you do not set a password before applying the [readOnlyRecommended](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/readOnlyRecommended/) property, then other users can simply open the document as if it were unprotected. You access the document protection settings and set a write protection password via the [setPassword](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/setPassword/#string) method.

{{% alert color="primary" %}}

Note that the password being set is just a property in a document that can be removed if the document properties are accessed. Accordingly, such a password is not a guarantee of the document security.

{{% /alert %}}

If you need to check if a document has a write protection password that restricts it from editing, you can use the [isWriteProtected](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/isWriteProtected/) property.

The following code example shows how to make a document read-only:

{{< gist "aspose-words-gists" "2a464f0279e5751f4ef94d7daf395e52" "read-only-protection.js" >}}

## Remove Read-Only Restriction

If you do not want a user to open your document as read-only, you can simply set the [readOnlyRecommended](https://reference.aspose.com/words/nodejs-net/aspose.words.settings/writeprotection/readOnlyRecommended/) property to `False` or select [protectionType](https://reference.aspose.com/words/nodejs-net/aspose.words/document/protectiontype/) as [NoProtection](https://reference.aspose.com/words/nodejs-net/aspose.words/protectiontype/).

The following code example shows how to remove read-only access for a document:

{{< gist "aspose-words-gists" "2a464f0279e5751f4ef94d7daf395e52" "remove-read-only-restriction.js" >}}

------ 

## FAQ

1. Q: How can I make a document read‑only without requiring a password?  
   A: Set the `readOnlyRecommended` property to `true` on the document's `WriteProtection` object and do not call `setPassword`. The document will open in read‑only mode, but users can still remove the recommendation by changing the setting in Word.

2. Q: How do I set a password that forces users to open the document as read‑only?  
   A: After loading the document, call `document.writeProtection.setPassword("MyPassword")` and then set `document.writeProtection.readOnlyRecommended = true`. When the file is opened, Word will prompt for the password before allowing edits.

3. Q: How can I programmatically verify whether a document is write‑protected?  
   A: Use the `isWriteProtected` property:  
   ```javascript
   const Document = require('@aspose/words').Document;
   const doc = new Document("input.docx");
   const isProtected = doc.writeProtection.isWriteProtected;
   console.log("Write protected:", isProtected);
   ```

4. Q: What is the correct way to remove the read‑only recommendation from a document?  
   A: Set `readOnlyRecommended` to `false` and optionally clear the password with `setPassword("")`. Example:  
   ```javascript
   const doc = new Document("protected.docx");
   doc.writeProtection.readOnlyRecommended = false;
   doc.writeProtection.setPassword("");
   doc.save("unprotected.docx");
   ```

5. Q: What is the difference between `readOnlyRecommended` and `ProtectionType.ReadOnly`?  
   A: `readOnlyRecommended` only suggests that the document be opened in read‑only mode and can be combined with a password; it does not enforce editing restrictions. `ProtectionType.ReadOnly` (applied via `document.protect(ProtectionType.ReadOnly, password)`) applies a stronger protection that disables editing features in Word, similar to the “Restrict Editing” feature. Use `ProtectionType` when you need to prevent any modifications, not just suggest read‑only.