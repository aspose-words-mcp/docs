---
title: Update Fields in C++
second_title: Aspose.Words for C++
articleTitle: Update Fields
linktitle: Update Fields
description: "Learn how to update fields in C++. Update fields programmatically or use automatic field update using C++ API."
type: docs
weight: 30
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/update-fields/
aliases: [/cpp/updating-and-removing-a-field/]
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

To explicitly update fields in the whole document, simply call the [UpdateFields](https://reference.aspose.com/words/cpp/aspose.words/document/updatefields/) method. To update fields contained in part of a document, obtain a [Range](https://reference.aspose.com/words/cpp/aspose.words/range/) object and call the [UpdateFields](https://reference.aspose.com/words/cpp/aspose.words/range/updatefields/) method. In Aspose.Words, you can obtain a **Range** for any node in the document tree, such as [Section](https://reference.aspose.com/words/cpp/aspose.words/section/), [HeaderFooter](https://reference.aspose.com/words/cpp/aspose.words/headerfooter/) , [Paragraph](https://reference.aspose.com/words/cpp/aspose.words/paragraph/), etc. using the [Node::get_Range()](https://reference.aspose.com/words/cpp/aspose.words/node/get_range/) property. You can update the result of a single field by calling the [Update](https://reference.aspose.com/words/cpp/aspose.words.fields/field/update/) method.

### Automatic Update of Page-Related Fields During Rendering

When you execute conversion of a document to a fixed-page format e.g. to PDF or XPS, then Aspose.Words will automatically update page layout-related fields `PAGE`, `PAGEREF` found in headers/footers of the document. This behavior mimics the behavior of Microsoft Word when printing a document.

If you want to update all other fields in the document, then you need to call [UpdateFields](https://reference.aspose.com/words/cpp/aspose.words/document/updatefields/) before rendering the document.

The following code example shows how to update all fields before rendering a document:

{{< gist "aspose-words-gists" "e5783d55cbae460927e547f5f67e42b8" "update-doc-fields.h" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

### Automatic Field Update During Mail Merge

When you execute a mail merge, all fields in the document will be automatically updated. This is because the Mail Merge is a case of a field update. The program encounters a Mail Merge field and needs to update its result, which involves grabbing the value from the data source and inserting it into the field. The logic is of course more complicated, for example, when the end of the document/mail merge region is reached but there is still further data to be merged, then the region needs to be duplicated and the new set of fields updated.

## Update Fields Having Dirty Attribute

The w:dirty is a field-level attribute that will refresh only the field you specify when the document is opened. It tells MS Word to only refresh this field the next time the document is opened. You can use the [get_UpdateDirtyFields()](https://reference.aspose.com/words/cpp/aspose.words.loading/loadoptions/get_updatedirtyfields/) property to specify whether to update the fields with the dirty attribute. When the value of **get_UpdateDirtyFields()** is set to *true*, all fields having *true* value for [Field::get_IsDirty()](https://reference.aspose.com/words/cpp/aspose.words.fields/field/get_isdirty/) or [FieldChar::get_IsDirty()](https://reference.aspose.com/words/cpp/aspose.words.fields/fieldchar/get_isdirty/) property are updated on document load.

The following code example shows how to update fields having the dirty attribute:

{{< gist "aspose-words-gists" "e5783d55cbae460927e547f5f67e42b8" "update-dirty-fields.h" >}}

## Update LastSavedTime Property Before Saving

You can use the [get_UpdateLastSavedTimeProperty()](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/get_updatelastsavedtimeproperty/) property whether to update the corresponding built-in document property [get_LastSavedTime()](https://reference.aspose.com/words/cpp/aspose.words.properties/builtindocumentproperties/get_lastsavedtime/) when saving the document.

The following code example shows how to update this property:

{{< gist "aspose-words-gists" "d143f183bd5dfe07f1f289704e64133c" "update-last-saved-time.h" >}}

## Related APIs

- Document::UpdateFields() – Updates all fields in the document.
- Range::UpdateFields() – Updates fields within a specific range (e.g., section, header, paragraph).
- Field::Update() – Updates a single field.
- LoadOptions::set_UpdateDirtyFields(bool) / LoadOptions::get_UpdateDirtyFields() – Gets or sets whether to update dirty fields when loading a document.
- Field::IsDirty – Gets or sets a value indicating whether the field result is out of date.
- FieldChar::IsDirty – Gets or sets a value indicating whether the field result is out of date.
- SaveOptions::set_UpdateLastSavedTimeProperty(bool) / SaveOptions::get_UpdateLastSavedTimeProperty() – Gets or sets whether to update the LastSavedTime built‑in document property when saving.
- BuiltInDocumentProperties::LastSavedTime – Gets or sets the date and time the document was last saved.

------ 

## FAQ

1. **Q:** How can I update all fields in a document using C++?  
   **A:** Load the document, call `Document::UpdateFields()`, and then save the document. This updates every field, including TOC, page numbers, and formula fields.  

2. **Q:** How do I update fields only in a specific part of a document, such as a header or a section?  
   **A:** Obtain the `Range` of the target node (e.g., `auto range = header->get_Range();` for a `HeaderFooter`) and call `range->UpdateFields()`. Only fields inside that range are refreshed.  

3. **Q:** Are page‑related fields like `PAGE` and `PAGEREF` updated automatically when converting to PDF or XPS?  
   **A:** Yes. During rendering to fixed‑page formats, Aspose.Words automatically updates page‑related fields in headers and footers. For other fields you must call `UpdateFields()` before rendering.  

4. **Q:** Does Mail Merge automatically update fields, or must I call `UpdateFields()` after a merge?  
   **A:** Mail Merge automatically updates all fields in the document, so no additional call to `UpdateFields()` is required.  

5. **Q:** How can I ensure the `get_LastSavedTime()` built‑in property reflects the current time when saving?  
   **A:** Set `SaveOptions::UpdateLastSavedTimeProperty` to `true` before saving the document. This updates the `set_LastSavedTime()` property to the current system time.  