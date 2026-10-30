---
title: Update Fields C#
second_title: Aspose.Words for .NET
articleTitle: Update Fields
linktitle: Update Fields
description: "Learn how to update fields in C#. Update fields programmatically or use automatic field update using .NET API."
type: docs
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/update-fields/
aliases: [/net/updating-and-removing-a-field/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to update fields in a Word document programmatically.

{{% /alert %}}

Typically, a field inserted into Microsoft Word already contains an up to date value. For example, if the field is a formula or a page number, it will contain the correct calculated value for the given version of the document. But if you have an application that generates or modifies a document with fields like merging two documents or populating it with data, then ideally all fields must be updated for the document to be useful.

## How to Update Fields

When a document is loaded, Aspose.Words mimics the behavior of Microsoft Word with the option to automatically update fields is switched off. The behavior can be summarized as follows:

- when you open/save a document the fields remain intact
- you can explicitly update all fields in a document, for example, rebuild `TOC`, when you need to
- when you print/render to PDF or XPS the fields related to page-numbering in headers/footers are updated
- when you execute Mail Merge all fields are updated automatically

### Update Fields Programmatically

To explicitly update fields in the whole document, simply call the [UpdateFields](https://reference.aspose.com/words/net/aspose.words/document/updatefields/) method. To update fields contained in part of a document, obtain a [Range](https://reference.aspose.com/words/net/aspose.words/range/) object and call the [UpdateFields](https://reference.aspose.com/words/net/aspose.words/range/updatefields/) method. In Aspose.Words, you can obtain a **Range** for any node in the document tree, such as [Section](https://reference.aspose.com/words/net/aspose.words/section/), [HeaderFooter](https://reference.aspose.com/words/net/aspose.words/headerfooter/) , [Paragraph](https://reference.aspose.com/words/net/aspose.words/paragraph/), etc. using the [Node.Range](https://reference.aspose.com/words/net/aspose.words/node/range/) property. You can update the result of a single field by calling the [Update](https://reference.aspose.com/words/net/aspose.words.fields/field/update/) method.

### Automatic Update of Page-Related Fields During Rendering

When you execute conversion of a document to a fixed-page format e.g. to PDF or XPS, then Aspose.Words will automatically update page layout-related fields `PAGE`, `PAGEREF` found in headers/footers of the document. This behavior mimics the behavior of Microsoft Word when printing a document.

If you want to update all other fields in the document, then you need to call [UpdateFields](https://reference.aspose.com/words/net/aspose.words/document/updatefields/) before rendering the document.

The following code example shows how to update all fields before rendering a document:

{{< gist "aspose-words-gists" "08db64c4d86842c4afd1ecb925ed07c4" "update-doc-fields.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

### Automatic Field Update During Mail Merge

When you execute a mail merge, all fields in the document will be automatically updated. This is because the Mail Merge is a case of a field update. The program encounters a Mail Merge field and needs to update its result, which involves grabbing the value from the data source and inserting it into the field. The logic is of course more complicated, for example, when the end of the document/mail merge region is reached but there is still further data to be merged, then the region needs to be duplicated and the new set of fields updated.

## Update Fields Having Dirty Attribute

The w:dirty is a field-level attribute that will refresh only the field you specify when the document is opened. It tells MS Word to only refresh this field the next time the document is opened. You can use the [UpdateDirtyFields](https://reference.aspose.com/words/net/aspose.words.loading/loadoptions/updatedirtyfields/) property to specify whether to update the fields with the dirty attribute. When the value of **UpdateDirtyFields** is set to *true*, all fields having *true* value for [Field.IsDirty](https://reference.aspose.com/words/net/aspose.words.fields/field/isdirty/) or [FieldChar.IsDirty](https://reference.aspose.com/words/net/aspose.words.fields/fieldchar/isdirty/) property are updated on document load.

The following code example shows how to update fields having the dirty attribute:

{{< gist "aspose-words-gists" "08db64c4d86842c4afd1ecb925ed07c4" "update-dirty-fields.cs" >}}

## Update LastSavedTime Property Before Saving

You can use the [UpdateLastSavedTimeProperty](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/) property whether to update the corresponding built-in document property [LastSavedTime](https://reference.aspose.com/words/net/aspose.words.properties/builtindocumentproperties/lastsavedtime/) when saving the document.

The following code example shows how to update this property:

{{< gist "aspose-words-gists" "83e5c469d0e72b5114fb8a05a1d01977" "update-last-saved-time.cs" >}}

## Related APIs


- [Document.UpdateFields()](https://reference.aspose.com/words/net/aspose.words/document/updatefields/) - Updates all fields in the document.
- [Range.UpdateFields()](https://reference.aspose.com/words/net/aspose.words/range/updatefields/) - Updates fields within a specific range (e.g., section, header, paragraph).
- [Field.Update()](https://reference.aspose.com/words/net/aspose.words.fields/field/update/) - Updates a single field.
- [LoadOptions.UpdateDirtyFields](https://reference.aspose.com/words/net/aspose.words.loading/loadoptions/updatedirtyfields/) - Gets or sets a value indicating whether to update fields marked as dirty when loading a document.
- [Field.IsDirty](https://reference.aspose.com/words/net/aspose.words.fields/field/isdirty/) - Gets or sets a value indicating whether the field result is out of date.
- [FieldChar.IsDirty](https://reference.aspose.com/words/net/aspose.words.fields/fieldchar/isdirty/) - Gets or sets a value indicating whether the field result is out of date.
- [SaveOptions.UpdateLastSavedTimeProperty](https://reference.aspose.com/words/net/aspose.words.saving/saveoptions/updatelastsavedtimeproperty/) - Gets or sets a value indicating whether to update the `LastSavedTime` built-in document property when saving.
- [BuiltInDocumentProperties.LastSavedTime](https://reference.aspose.com/words/net/aspose.words.properties/builtindocumentproperties/lastsavedtime/) - Gets or sets the date and time the document was last saved.

## FAQ

1. **Q:** How can I update all fields in a document using Aspose.Words for .NET?  
   **A:** Load the document, call `Document.UpdateFields()`, and then save or render it. This updates every field, including TOC, formulas, and references.  

   ```csharp
   Document doc = new Document("input.docx");
   doc.UpdateFields();               // Updates all fields in the document
   doc.Save("output.docx");
   ```

2. **Q:** How do I update fields only in a specific part of a document, such as a header or a section?  
   **A:** Obtain the node that represents the part you want to update, get its `Range`, and call `Range.UpdateFields()`. This updates fields only within that range.  

   ```csharp
   Document doc = new Document("input.docx");
   HeaderFooter header = (HeaderFooter)doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary];
   header.Range.UpdateFields();      // Updates fields only in the header
   doc.Save("output.docx");
   ```

3. **Q:** Will page‑number fields be updated automatically when converting a document to PDF or XPS?  
   **A:** Yes. During rendering to a fixed‑page format, Aspose.Words automatically updates page‑related fields (`PAGE`, `PAGEREF`, etc.) found in headers and footers. If you also need other fields updated, call `Document.UpdateFields()` before rendering.  

   ```csharp
   Document doc = new Document("input.docx");
   doc.UpdateFields();               // Optional: update non‑page fields
   doc.Save("output.pdf");           // Page fields are refreshed automatically
   ```

4. **Q:** How can I update fields that have the **dirty** attribute when loading a document?  
   **A:** Set `LoadOptions.UpdateDirtyFields` to `true` when creating the `Document`. This forces Aspose.Words to refresh all fields marked as dirty on load.  

   ```csharp
   LoadOptions loadOptions = new LoadOptions
   {
       UpdateDirtyFields = true
   };
   Document doc = new Document("input.docx", loadOptions);
   doc.Save("output.docx");
   ```

5. **Q:** How do I ensure the **LastSavedTime** property is updated when saving a document?  
   **A:** Use `SaveOptions.UpdateLastSavedTimeProperty` and set it to `true` before calling `Save`. This updates the built‑in `LastSavedTime` property to the current time.  

   ```csharp
   Document doc = new Document("input.docx");
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions
   {
       UpdateLastSavedTimeProperty = true
   };
   doc.Save("output.docx", saveOptions);
   ```