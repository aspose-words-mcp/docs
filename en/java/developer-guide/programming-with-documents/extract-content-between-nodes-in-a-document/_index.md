---
title: How to Extract Content Between Document Nodes using Java
second_title: Aspose.Words for Java
articleTitle: Extract Content Between Nodes in a Document
linktitle: Extract Content Between Nodes
description: "Extracting document content in different using Java."
type: docs
weight: 140
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/extract-selected-content-between-nodes/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to extract selected content between nodes in a document.

{{% /alert %}}

When working with documents, it is important to be able to easily extract content from a specific range within a document. However, the content may consist of complex elements such as paragraphs, tables, images, etc.

Regardless of what content needs to be extracted, the method to extract that content will always be determined by which nodes are selected to extract content between. These can be entire text bodies or simple text runs.

There are many possible situations and therefore many different node types to consider when extracting content. For example, you might want to extract content between:

- Two specific paragraphs
- Specific runs of text
- Fields of various types, such as merge fields
- Start and end ranges of a bookmark or comment
- Various bodies of text contained in separate sections

In some situations, you may even need to combine different node types, such as extracting content between a paragraph and a field, or between a run and a bookmark.

This article provides the code implementation for extracting text between different nodes, as well as examples of common scenarios.

{{% alert color="primary" %}}

These examples are just a few demonstrations of the many possibilities. We plan for the text extraction functionality to be part of the public API in the future, and no extra code will be required. In the meantime, feel free to post your requests regarding this functionality on the [Aspose.Words forum](https://forum.aspose.com/c/words/8).

{{% /alert %}}

## Why Extract Content

Often the goal of extracting the content is to duplicate or save it separately in a new document. For example, you can extract content and:

- Copy it into a separate document
- Convert a specific part of a document to PDF or image
- Duplicate the content in the document many times
- Work with extracted content separate from the rest of the document

This can be easily achieved using Aspose.Words and the code implementation below.

## Extracting Content Algorithm

The code in this section addresses all of the possible situations described above with one generalized and reusable method. The general outline of this technique involves:

1. Gathering the nodes which dictate the area of content that will be extracted from your document. Retrieving these nodes is handled by the user in their code, based on what they want to be extracted.
1. Passing these nodes to the **ExtractContent** method provided below. You must also pass a boolean parameter which states whether these nodes, acting as markers, should be included in the extraction or not.
1. Retrieving a list of cloned content (copied nodes) specified to be extracted. You can use this list of nodes in any applicable way, for example, creating a new document containing only the selected content.

## How to Extract Content

To extract the content from your document you need to call the **ExtractContent** method below and pass the appropriate parameters. The underlying basis of this method involves finding block level nodes (paragraphs and tables) and cloning them to create identical copies. If the marker nodes passed are block level then the method is able to simply copy the content on that level and add it to the array.

However if the marker nodes are inline (a child of a paragraph) then the situation becomes more complex, as it is necessary to split the paragraph at the inline node, be it a run, bookmark fields etc. Content in the cloned parent nodes not present between the markers is removed. This process is used to ensure that the inline nodes will still retain the formatting of the parent paragraph. The method will also run checks on the nodes passed as parameters and throws an exception if either node is invalid. The parameters to be passed to this method are:

1. **StartNode** and **EndNode**. The first two parameters are the nodes which define where the extraction of the content is to begin and to end at respectively. These nodes can be both block level ([Paragraph](https://reference.aspose.com/words/java/com.aspose.words/paragraph/) , [Table](https://reference.aspose.com/words/java/com.aspose.words/table/)) or inline level (e.g [Run](https://reference.aspose.com/words/java/com.aspose.words/run/) , [FieldStart](https://reference.aspose.com/words/java/com.aspose.words/fieldstart/) , [BookmarkStart](https://reference.aspose.com/words/java/com.aspose.words/bookmarkstart/) etc.):
   1. To pass a field you should pass the corresponding **FieldStart** object
   1. To pass bookmarks, the **BookmarkStart** and [BookmarkEnd](https://reference.aspose.com/words/java/com.aspose.words/bookmarkend/) nodes should be passed
   1. To pass comments, the [CommentRangeStart](https://reference.aspose.com/words/java/com.aspose.words/commentrangestart/) and [CommentRangeEnd](https://reference.aspose.com/words/java/com.aspose.words/commentrangeend/) nodes should be used
1. **IsInclusive**. Defines if the markers are included in the extraction or not. If this option is set to false and the same node or consecutive nodes are passed, then an empty list will be returned:
   1. If a **FieldStart** node is passed then this option defines if the whole field is to be included or excluded.
   1. If a **BookmarkStart** or **BookmarkEnd** node is passed, this option defines if the bookmark is included or just the content between the bookmark range.
   1. If a **CommentRangeStart** or **CommentRangeEnd** node is passed, this option defines if the comment itself is to be included or just the content in the comment range.

The implementation of the **ExtractContent** method you can find [on Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/DocsExamples/Java/src/main/java/DocsExamples/Programming_with_documents/Contents_management/ExtractContentHelper.java). This method will be referred to in the scenarios in this article.

We will also define a custom method to easily generate a document from extracted nodes. This method is used in many of the scenarios below and simply creates a new document and imports the extracted content into it.

The following code example shows how to take a list of nodes and inserts them into a new document:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "generate-document.java" >}}

## Extract Content Between Paragraphs

This demonstrates how to use the method above to extract content between specific paragraphs. In this case, we want to extract the body of the letter found in the first half of the document. We can tell that this is between the 7th and 11th paragraphs.

The code below accomplishes this task. The appropriate paragraphs are extracted using the [getChild](https://reference.aspose.com/words/java/com.aspose.words/compositenode/#getChild-int-int-boolean) method on the document and passing the specified indices. We then pass these nodes to the **ExtractContent** method and state that these are to be included in the extraction. This method will return the copied content between these nodes which are then inserted into a new document.

The following code example shows how to extract the content between specific paragraphs using the `ExtractContent` method above:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-between-paragraphs.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## Extract Content Between Different Types of Nodes

We can extract content between any combinations of block-level or inline nodes. In this scenario below we will extract the content between first paragraph and the table in the second section inclusively. We get the markers nodes by calling [getFirstParagraph](https://reference.aspose.com/words/java/com.aspose.words/body/#getFirstParagraph) and [getChild](https://reference.aspose.com/words/java/com.aspose.words/compositenode/#getChild-int-int-boolean) methods on the second section of the document to retrieve the appropriate **Paragraph** and **Table** nodes. For a slight variation let's instead duplicate the content and insert it below the original.

The following code example shows how to extract the content between a paragraph and table using the **ExtractContent** method:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-between-block-level-nodes.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## Extract Content Between Paragraphs Based on Style

You may need to extract the content between paragraphs of the same or different style, such as between paragraphs marked with heading styles. The code below shows how to achieve this. It is a simple example which will extract the content between the first instance of the “Heading 1” and “Header 3” styles without extracting the headings as well. To do this we set the last parameter to false, which specifies that the marker nodes should not be included.

In a proper implementation this should be run in a loop to extract content between all paragraphs of these styles from the document. The extracted content is copied into a new document.

The following code example shows how to extract content between paragraphs with specific styles using the **ExtractContent** method:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-between-paragraph-styles.java" >}}

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "paragraphs-by-style-name.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## Extract Content Between Specific Runs

You can extract content between inline nodes such as a [Run](https://reference.aspose.com/words/java/com.aspose.words/run/) as well. **Runs** from different paragraphs can be passed as markers. The code below shows how to extract specific text in-between the same **Paragraph** node.

The following code example shows how to extract content between specific runs of the same paragraph using the **ExtractContent** method:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-between-runs.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## Extract Content using a Field

To use a field as marker, the `FieldStart` node should be passed. The last parameter to the `ExtractContent` method will define if the entire field is to be included or not. Let's extract the content between the “FullName” merge field and a paragraph in the document. We use the [moveToMergeField](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToMergeField-java.lang.String) method of [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) class. This will return the **FieldStart** node from the name of merge field passed to it.

In our case let's set the last parameter passed to the **ExtractContent** method to false to exclude the field from the extraction. We will render the extracted content to PDF.

The following code example shows how to extract content between a specific field and paragraph in the document using the **ExtractContent** method:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-using-field.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## Extract Content from a Bookmark

In a document the content that is defined within a bookmark is encapsulated by the `BookmarkStart` and BookmarkEnd nodes. Content found between these two nodes make up the bookmark. You can pass either of these nodes as any marker, even ones from different bookmarks, as long as the starting marker appears before the ending marker in the document. We will extract this content into a new document using the code below. The **IsInclusive** parameter option shows how to retain or discard the bookmark.

The following code example shows how to extract the content referenced a bookmark using the **ExtractContent** method:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-between-bookmark.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## Extract Content from a Comment

A comment is made up of the CommentRangeStart, CommentRangeEnd and Comment nodes. All of these nodes are inline. The first two nodes encapsulate the content in the document which is referenced by the comment, as seen in the screenshot below.

The **Comment** node itself is an [InlineStory](https://reference.aspose.com/words/java/com.aspose.words/inlinestory/) that can contain paragraphs and runs. It represents the message of the comment as seen as a comment bubble in the review pane. As this node is inline and a descendant of a body you can also extract the content from inside this message as well.

The comment encapsulates the heading, first paragraph and the table in the second section. Let's extract this comment into a new document. The **IsInclusive** option dictates if the comment itself is kept or discarded.

The following code example shows how to do this:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-between-comment-range.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## How to Extract Content using DocumentVisitor

Use the [DocumentVisitor](https://reference.aspose.com/words/java/com.aspose.words/documentvisitor/) class to implement this usage scenario. This class corresponds to the well-known Visitor design pattern. With **DocumentVisitor** **,** you can define and execute custom operations that require enumeration over the document tree.

**DocumentVisitor** provides a set of **VisitXXX** methods that are invoked when a particular document element (node) is encountered. For example, [DocumentVisitor](https://reference.aspose.com/words/java/com.aspose.words/documentvisitor/) is called when the beginning of a text paragraph is found and [visitParagraphStart()](https://reference.aspose.com/words/java/com.aspose.words/documentvisitor/#visitParagraphStart-com.aspose.words.Paragraph) is called when the end of a text paragraph is found. Each **DocumentVisitor.VisitXXX** method accepts the corresponding object that it encounters so you can use it as needed (say retrieve the formatting), e.g. both **DocumentVisitor.visitParagraphStart** and **DocumentVisitor.visitParagraphEnd** accept a [visitParagraphEnd()](https://reference.aspose.com/words/java/com.aspose.words/documentvisitor/#visitParagraphEnd-com.aspose.words.Paragraph) object.

Each **DocumentVisitor.VisitXXX** method returns a [VisitorAction](https://reference.aspose.com/words/java/com.aspose.words/visitoraction/) value that controls the enumeration of nodes. You can request either to continue the enumeration, skip the current node (but continue the enumeration), or stop the enumeration of nodes.

These are the steps you should follow to programmatically determine and extract various parts of a document:

- Create a class derived from **DocumentVisitor**
- Override and provide implementations for some or all of the **DocumentVisitor.VisitXXX** methods to perform some custom operations
- Call [DocumentVisitor](https://reference.aspose.com/words/java/com.aspose.words/documentvisitor/) on the node from where you want to start the enumeration, for example, if you want to enumerate the whole document, use [Node.accept](https://reference.aspose.com/words/java/com.aspose.words/node/#accept-com.aspose.words.DocumentVisitor)

**DocumentVisitor** provides default implementations for all of the **DocumentVisitor.VisitXXX** methods. This makes it easier to create new document visitors as only the methods required for the particular visitor need to be overridden. It is not necessary to override all of the visitor methods.

The following example shows how to use the Visitor pattern to add new operations to the Aspose.Words object model. In this case, we create a simple document converter into a text format:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-content-using-document-visitor.java" >}}

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "convert-doc-to-txt.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Extract%20content.docx).

{{% /alert %}}

## How to Extract Text Only

The ways to retrieve text from the document are:

- Use [Document.save](https://reference.aspose.com/words/java/com.aspose.words/document/#save-java.io.OutputStream-com.aspose.words.SaveOptions) with [SaveFormat](https://reference.aspose.com/words/java/com.aspose.words/saveformat/) to save as plain text into a file or stream
- Use [Node.toString](https://reference.aspose.com/words/java/com.aspose.words/node/#toString-com.aspose.words.SaveOptions) and pass the **SaveFormat.TEXT** parameter. Internally, this invokes save as text into a memory stream and returns the resulting string
- Use [Node.getText](https://reference.aspose.com/words/java/com.aspose.words/node/#getText) to retrieve text with all Microsoft Word control characters including field codes
- Implement a custom [DocumentVisitor](https://reference.aspose.com/words/java/com.aspose.words/documentvisitor/) to perform customized extraction

### Using `node.getText()` and `node.toString()`

A Word document can contains control characters that designate special elements such as field, end of cell, end of section etc. The full list of possible Word control characters is defined in the **ControlChar** class. The **Node.getText** method returns text with all of the control character characters present in the node.

Calling **toString()** returns the plain text representation of the document only without control characters. For further information on exporting as plain text see following section **"Using SaveFormat.TEXT"**.

The following code example shows the difference between calling the **GetText** and **toString()** methods on a node:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "simple-extract-text.java" >}}

## Extract Images from Shapes

You may need to extract document images to perform some tasks. Aspose.Words allows you to do this as well.

The following code example shows how to extract images from a document:

{{< gist "aspose-words-gists" "1975a35426bcd195a2e7c61d20a1580c" "extract-images.java" >}}

## Related APIs

- [Paragraph](https://reference.aspose.com/words/java/com.aspose.words/paragraph/)
- [Table](https://reference.aspose.com/words/java/com.aspose.words/table/)
- [Run](https://reference.aspose.com/words/java/com.aspose.words/run/)
- [FieldStart](https://reference.aspose.com/words/java/com.aspose.words/fieldstart/)
- [FieldEnd](https://reference.aspose.com/words/java/com.aspose.words/fieldend/)
- [getBookmarkStart()](https://reference.aspose.com/words/java/com.aspose.words/bookmark/#getBookmarkStart)
- [getBookmarkEnd()](https://reference.aspose.com/words/java/com.aspose.words/bookmark/#getBookmarkEnd)
- [CommentRangeStart](https://reference.aspose.com/words/java/com.aspose.words/commentrangestart/)
- [CommentRangeEnd](https://reference.aspose.com/words/java/com.aspose.words/commentrangeend/) 

## FAQ

1. **Q:** How can I extract content between two specific nodes in a Word document using Aspose.Words for Java?  
   **A:** Locate the start and end nodes (e.g., Paragraph, Run, FieldStart, BookmarkStart) using the document object model, then call the `ExtractContentHelper.extractContent(startNode, endNode, isInclusive, copySection)` helper from the example. The method returns a list of cloned nodes; the example's `ExtractContentHelper.generateDocument(srcDoc, nodes)` puts them into a new `Document`, or you can import each node individually.

2. **Q:** What does the **IsInclusive** parameter control in the `ExtractContent` method?  
   **A:** When **IsInclusive** is `true`, the start and end marker nodes themselves are included in the extracted range. When `false`, only the content *between* the markers is returned. This is useful for excluding merge fields, bookmarks, or comment markers from the result.

3. **Q:** Can I use a bookmark or a comment as markers for extraction?  
   **A:** Yes. Pass the `BookmarkStart`/`BookmarkEnd` nodes or the `CommentRangeStart`/`CommentRangeEnd` nodes as the start and end parameters. The helper will correctly handle inline markers and will retain or discard the bookmark/comment based on the **IsInclusive** flag.

4. **Q:** How do I extract only the plain text of a document without formatting or control characters?  
   **A:** Use `Node.getText()` for raw text with control characters, or `Node.toString(SaveFormat.TEXT)` to obtain clean plain text. Alternatively, save the whole document with `Document.save(outputStream, SaveFormat.TEXT)` for a UTF‑8 encoded text file.

5. **Q:** Is it possible to extract images from a document while extracting other content?  
   **A:** Yes. Iterate through the document's `NodeType.SHAPE` nodes, check `Shape.getShapeType() == ShapeType.IMAGE`, and call `Shape.getImageData().toByteArray()` to obtain the image bytes. You can store the images separately and still use the `ExtractContent` method for the surrounding text, tables, or paragraphs.