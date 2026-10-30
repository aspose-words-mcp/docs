---
title: Node.js and .NET Version Differences
second_title: Aspose.Words for Node.js via .NET
articleTitle: Node.js and .NET Version Differences
linktitle: Node.js and .NET Version Differences
description: "Aspose.Words for Node.js via .NET is a native Node.js module based on Aspose.Words for .NET with [Node-API](https://nodejs.org/api/n-api.html). This page describes the differences in features and API of these two products."
type: docs
weight: 15
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/nodejs-notes/
aliases: [/nodejs/nodejs-notes/]
timestamp: 2025-04-17-14-07-04
---

Aspose.Words for Node.js via .NET is a native Node.js module based on Aspose.Words for .NET with [Node-API](https://nodejs.org/api/n-api.html), that is why the two products have almost the same set of features. Nevertheless, there are some nuances of work and differences in features and API, which are described on this page.

## Feature Differences

Aspose.Words for Node.js has some differences as compared to its equivalent .NET version of the API. This section contains information about all such functionality that is not available in the current release. The missing features will be added in the future releases.
* Implementation of interfaces is not supported yet, that is why it is not possible to use callbacks such as [IWarningCallback](https://reference.aspose.com/words/net/aspose.words/iwarningcallback/), [IReplacingCallback](https://reference.aspose.com/words/net/aspose.words.replacing/ireplacingcallback/), [IFieldUpdatingCallback](https://reference.aspose.com/words/net/aspose.words.fields/ifieldupdatingcallback/), [IFieldMergingCallback](https://reference.aspose.com/words/net/aspose.words.mailmerging/ifieldmergingcallback/) etc.
* It does not support [Printing](https://docs.aspose.com/words/net/print-a-document-programmatically-or-using-dialogs/) features.
* [DocumentVisitor](https://reference.aspose.com/words/net/aspose.words/documentvisitor/) implementation is currently not possible from the Node.js code.
* [Reporting](https://docs.aspose.com/words/net/linq-reporting-engine/) features are very .NET specific and aren't not supported in Node.js.
* [MailMerge](https://docs.aspose.com/words/net/mail-merge-and-reporting/) functionality is not implemented.
* [Low Code API](https://reference.aspose.com/words/net/aspose.words.lowcode/) is not implemented yet.
* Reading of PDF documents is not implemented.
* All .NET-specific APIs like OleDB and ADO are not supported. 
* The first release only supports Microsoft Windows┬о x64 platform and Node.js 14.17.0 or higher.

## Casting Aspose.Words Objects in Node.js

Though type casting is not natural for Node.js developers some tasks cannot be accomplished without casting documents nodes or fields to concrete type. Aspose.Words for Node.js via .NET provides special methods that allow casting objects where this is necessary.

### Casting Nodes

Base class for all document nodes in Aspose.Words DOM is [Node](https://reference.aspose.com/words/nodejs-net/aspose.words/node/) class. For example [getChild](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/getChild/) method returns and instance of [Node](https://reference.aspose.com/words/nodejs-net/aspose.words/node/) class, but if you need to modify the returned node, in most cases you should to cast it to concrete type. The following code demonstrates how to change font color of the first [Run](https://reference.aspose.com/words/nodejs-net/aspose.words/run/) in the document:

{{< highlight js >}}
let doc = new aw.Document("Document.docx");

// Get the first Run node and cast it to Run object.
let run = doc.getChild(aw.NodeType.Run, 0, true).asRun();

// Make changes to the run 
run.font.color = "red";

// Save the result
doc.save("WorkingWithNode.change_run_color.docx");
{{< /highlight >}}

Casting might be also required when [clone](https://reference.aspose.com/words/nodejs-net/aspose.words/document/clone/) method is used:

{{< highlight js >}}
let doc = new aw.Document("Document.docx");

let clone = doc.clone().asDocument();
clone.save("CloneAndCombineDocuments.cloning_document.docx");
{{< /highlight >}}

As you might noticed where in C# code you would use `(Paragraph)node` for casting, in Node.js you have to use `node.asParagraph()` method. In the Node.js version of Aspose.Words [Node](https://reference.aspose.com/words/nodejs-net/aspose.words/node/) class introduces the following link of `asXxx` methods:

* [asDocument()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asdocument/)
* [asSection()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/assection/)
* [asBody()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asbody/)
* [asHeaderFooter()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asheaderfooter/)
* [asTable()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/astable/)
* [asRow()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asrow/)
* [asCell()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/ascell/)
* [asParagraph()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asparagraph/)
* [asBookmarkStart()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asbookmarkstart/)
* [asBookmarkEnd()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asbookmarkend/)
* [asEditableRangeStart()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/aseditablerangestart/)
* [asEditableRangeEnd()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/aseditablerangeend/)
* [asGroupShape()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asgroupshape/)
* [asShape()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asshape/)
* [asComment()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/ascomment/)
* [asFootnote()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asfootnote/)
* [asRun()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asrun/)
* [asFieldStart()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asfieldstart/)
* [asFieldSeparator()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asfieldseparator/)
* [asFieldEnd()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asfieldend/)
* [asFormField()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asformfield/)
* [asSpecialChar()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asspecialchar/)
* [asSmartTag()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/assmarttag/)
* [asStructuredDocumentTag()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asstructureddocumenttag/)
* [asStructuredDocumentTagRangeStart()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asstructureddocumenttagrangestart/)
* [asStructuredDocumentTagRangeEnd()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asstructureddocumenttagrangeend/)
* [asGlossaryDocument()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asglossarydocument/)
* [asBuildingBlock()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asbuildingblock/)
* [asCommentRangeStart()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/ascommentrangestart/)
* [asCommentRangeEnd()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/ascommentrangeend/)
* [asOfficeMath()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/asofficemath/)
* [asSubDocument()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/assubdocument/)
* [asCompositeNode()](https://reference.aspose.com/words/nodejs-net/aspose.words/node/ascompositenode/)

The `asXxx` method raise a `RuntimeError` with the message like the following if the node cannot be cased to the specified type:

> RuntimeError: Unable to cast object of type 'Aspose.Words.XXX' to type 'Aspose.Words.Drawing.YYY'.

### Casting Fields
The same situation applied to fields. The following code example demonstrates how to replace hyper link links:

{{< highlight js >}}
let doc = new aw.Document();
let builder = new aw.DocumentBuilder(doc);
builder.write("This document was written by ");
let fieldAuthor = builder.insertField(aw.Fields.FieldType.FieldAuthor, true).asFieldAuthor();
fieldAuthor.authorName = "John Doe";
{{< /highlight >}}

As you might noticed [Field](https://reference.aspose.com/words/nodejs-net/aspose.words/field/) object also provides set of `asXxx` methods, which are listed below:

* [asFieldUnknown()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldunknown/)
* [asFieldMergeBarcode()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldmergebarcode/)
* [asFieldDisplayBarcode()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddisplaybarcode/)
* [asFieldPrint()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldprint/)
* [asFieldPrivate()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldprivate/)
* [asFieldAdvance()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldadvance/)
* [asFieldFormCheckBox()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldformcheckbox/)
* [asFieldFormDropDown()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldformdropdown/)
* [asFieldIndex()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldindex/)
* [asFieldRD()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldrd/)
* [asFieldTA()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldta/)
* [asFieldToa()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldtoa/)
* [asFieldAsk()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldask/)
* [asFieldAutoText()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldautotext/)
* [asFieldAutoTextList()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldautotextlist/)
* [asFieldBibliography()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldbibliography/)
* [asFieldCitation()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldcitation/)
* [asFieldDde()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddde/)
* [asFieldDdeAuto()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldddeauto/)
* [asFieldFillIn()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldfillin/)
* [asFieldGlossary()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldglossary/)
* [asFieldImport()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldimport/)
* [asFieldInclude()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldinclude/)
* [asFieldShape()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldshape/)
* [asFieldDatabase()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddatabase/)
* [asFieldSkipIf()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldskipif/)
* [asFieldListNum()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldlistnum/)
* [asFieldRevNum()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldrevnum/)
* [asFieldSection()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldsection/)
* [asFieldSectionPages()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldsectionpages/)
* [asFieldData()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddata/)
* [asFieldEmbed()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldembed/)
* [asFieldOcx()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldocx/)
* [asFieldAutoNum()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldautonum/)
* [asFieldAutoNumLgl()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldautonumlgl/)
* [asFieldAutoNumOut()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldautonumout/)
* [asFieldAddIn()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldaddin/)
* [asFieldBarcode()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldbarcode/)
* [asFieldBidiOutline()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldbidioutline/)
* [asFieldEQ()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldeq/)
* [asFieldFootnoteRef()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldfootnoteref/)
* [asFieldInfo()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldinfo/)
* [asFieldUserAddress()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielduseraddress/)
* [asFieldUserInitials()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielduserinitials/)
* [asFieldUserName()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldusername/)
* [asFieldIncludePicture()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldincludepicture/)
* [asFieldPage()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldpage/)
* [asFieldCreateDate()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldcreatedate/)
* [asFieldEditTime()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldedittime/)
* [asFieldPrintDate()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldprintdate/)
* [asFieldSaveDate()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldsavedate/)
* [asFieldGoToButton()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldgotobutton/)
* [asFieldAuthor()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldauthor/)
* [asFieldComments()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldcomments/)
* [asFieldFileName()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldfilename/)
* [asFieldFileSize()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldfilesize/)
* [asFieldKeywords()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldkeywords/)
* [asFieldLastSavedBy()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldlastsavedby/)
* [asFieldNumChars()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldnumchars/)
* [asFieldNumPages()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldnumpages/)
* [asFieldNumWords()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldnumwords/)
* [asFieldSubject()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldsubject/)
* [asFieldTemplate()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldtemplate/)
* [asFieldTitle()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldtitle/)
* [asFieldFormula()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldformula/)
* [asFieldSymbol()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldsymbol/)
* [asFieldQuote()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldquote/)
* [asFieldSet()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldset/)
* [asFieldAddressBlock()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldaddressblock/)
* [asFieldCompare()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldcompare/)
* [asFieldDate()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddate/)
* [asFieldDocProperty()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddocproperty/)
* [asFieldDocVariable()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfielddocvariable/)
* [asFieldGreetingLine()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldgreetingline/)
* [asFieldHyperlink()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldhyperlink/)
* [asFieldIf()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldif/)
* [asFieldIncludeText()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldincludetext/)
* [asFieldLink()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldlink/)
* [asFieldMacroButton()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldmacrobutton/)
* [asFieldMergeField()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldmergefield/)
* [asFieldMergeRec()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldmergerec/)
* [asFieldMergeSeq()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldmergeseq/)
* [asFieldNext()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldnext/)
* [asFieldNextIf()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldnextif/)
* [asFieldNoteRef()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldnoteref/)
* [asFieldPageRef()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldpageref/)
* [asFieldRef()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldref/)
* [asFieldSeq()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldseq/)
* [asFieldStyleRef()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldstyleref/)
* [asFieldTC()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldtc/)
* [asFieldTime()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldtime/)
* [asFieldToc()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldtoc/)
* [asFieldXE()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldxe/)
* [asFieldFormText()](https://reference.aspose.com/words/nodejs-net/aspose.words/field/asfieldformtext/)

### Casting Styles
Casting is also required to work with table styles:
{{< highlight js >}}
let doc = new aw.Document();
let builder = new aw.DocumentBuilder(doc);

let table = builder.startTable();
builder.insertCell();
builder.write("Name");
builder.insertCell();
builder.write("Value");
builder.endRow();
builder.insertCell();
builder.insertCell();
builder.endTable();

// Add a table style and modify it's properties.
let tableStyle = doc.styles.add(aw.StyleType.Table, "MyTableStyle1").asTableStyle();
tableStyle.borders.lineStyle = aw.LineStyle.Double;
tableStyle.borders.lineWidth = 1;
tableStyle.leftPadding = 18;
tableStyle.rightPadding = 18;
tableStyle.topPadding = 12;
tableStyle.bottomPadding = 12;

table.style = tableStyle;

doc.save("WorkingWithTableStylesAndFormatting.create_table_style.docx");
{{< /highlight >}}

### Casting Ole Controls
The following code example demonstrates how to read ActiveX control properties:
{{< highlight js >}}
let doc = new aw.Document("ActiveX controls.docx");
let shape = doc.getShape(0, true);
let oleControl = shape.oleFormat.oleControl;
console.log(oleControl.name); // "CheckBox1"
if (oleControl.isForms2OleControl) {
  console.log(oleControl);
  let checkBox = oleControl.asForms2OleControl();
  console.log(checkBox.caption);
  console.log(checkBox.groupName);
}
{{< /highlight >}}

### Casting Font Sources

[FontSourceBase](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/fontsourcebase/) class provides set of `asXxx` methods, which are listed below:

* [asFileFontSource()](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/fontsourcebase/asfilefontsource/)
* [asFolderFontSource()](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/fontsourcebase/asfolderfontsource/)
* [asMemoryFontSource()](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/fontsourcebase/asmemoryfontsource/)
* [asStreamFontSource()](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/fontsourcebase/asstreamfontsource/)
* [asSystemFontSource()](https://reference.aspose.com/words/nodejs-net/aspose.words.fonts/fontsourcebase/assystemfontsource/)

## Accessing Indexer Properties
Aspose.Words for Node.js does not support [.NET indexers](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/indexers/). To fill this gap the following classes have an additional at() and setAt() methods.

C# code:
{{< highlight csharp >}}
var doc = new Document("Bookmarks.docx");
var bookmarks = doc.Range.Bookmarks;
// Bookmarks can be accessed in the bookmark collection by index or name, and their names can be updated.
bookmarks[0].Name = "New name";
bookmarks["MyBookmark_2"].Text = $"Updated text contents of {bookmarks[1].Name}";
{{< /highlight >}}

Node.js code:
{{< highlight js >}}
let doc = new aw.Document("Bookmarks.docx");
let bookmarks = doc.range.bookmarks;
// Bookmarks can be accessed in the bookmark collection by index or name, and their names can be updated.
bookmarks.at(0).name = "New name";
bookmarks.at("MyBookmark_2").text = `Updated text contents of ${bookmarks.at(1).name}`;
{{< /highlight >}}

C# code:
{{< highlight csharp >}}
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
ToaCategories toaCategories = new ToaCategories();
toaCategories[1] = "My Category 1";
doc.FieldOptions.ToaCategories = toaCategories;
{{< /highlight >}}

Node.js code:
{{< highlight js >}}
let doc = new aw.Document();
let builder = new aw.DocumentBuilder(doc);
let toaCategories = new aw.Fields.ToaCategories();
toaCategories.setAt(1, "My Category 1");
doc.fieldOptions.toaCategories = toaCategories;
{{< /highlight >}}

## API Members Naming
To be closer to Node.js world, API members of Aspose.Words for Node.js via .NET uses camelCase for identifier names (variables and functions).