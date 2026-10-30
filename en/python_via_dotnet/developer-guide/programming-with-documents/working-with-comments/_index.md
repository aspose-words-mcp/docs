---
title: Working with Comments in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Comments
linktitle: Working with Comments
description: "How to add, remove, or manipulate comments in a document using Python."
type: docs
weight: 260
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-comments/
aliases: [/python/working-with-comments/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to add, extract, and remove comments and comment replies in Word documents using Aspose.Words for Python via .NET, providing code examples for each operation.

{{% /alert %}}

{{% alert color="primary" %}}

**Try online**

You can try this functionality with our [Free online remove annotations](https://products.aspose.app/words/annotation).

{{% /alert %}}

Aspose.Words allows users to work with comments – comments in a document in Aspose.Words are represented by the [Comment](https://reference.aspose.com/words/python-net/aspose.words/comment/) class. Also use the [CommentRangeStart](https://reference.aspose.com/words/python-net/aspose.words/commentrangestart/) and [CommentRangeEnd](https://reference.aspose.com/words/python-net/aspose.words/commentrangeend/) classes to specify the region of text that should be associated with a comment.

## Add a Comment

Aspose.Words allows you to add comments in several ways:

1. Using the [Comment](https://reference.aspose.com/words/python-net/aspose.words/comment/) class
2. Using the [CommentRangeStart](https://reference.aspose.com/words/python-net/aspose.words/commentrangestart/) and [CommentRangeEnd](https://reference.aspose.com/words/python-net/aspose.words/commentrangeend/) classes

The following code example shows how to add a comment to a paragraph using the **Comment** class:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "add-comments.py" >}}

The following code example shows how to add a comment to a paragraph using a region of text and the **CommentRangeStart** and **CommentRangeEnd** classes:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "anchor-comment.py" >}}

## Extract or Remove Comments

Using Comments in a Word document (in addition to Track Changes) is a common practice when reviewing documents, particularly when there are multiple reviewers. There can be situations where the only thing you need from a document is the comments. Say you want to generate a list of review findings, or perhaps you have collected all the useful information from the document and you simply want to remove unnecessary comments. You may want to view or remove the comments of a particular reviewer.

In this sample we are going to look at some simple methods for both gathering information from the comments within a document and for removing comments from a document. Specifically we'll cover how to:

- Extract all the comments from a document or only the ones made by a particular author
- Remove all the comments from a document or only from a particular author

### How to Extract or Remove Comments

The code in this sample is actually quite simple and all methods are based on the same approach. A comment in a Word document is represented by a [Comment](https://reference.aspose.com/words/python-net/aspose.words/comment/) object in the Aspose.Words document object model. To collect all the comments in a document use the [get_child_nodes](https://reference.aspose.com/words/python-net/aspose.words/compositenode/get_child_nodes/) method with the first parameter set to [NodeType.COMMENT](https://reference.aspose.com/words/python-net/aspose.words/nodetype/#comment). Make sure that the second parameter of the **get_child_nodes** method is set to true: this forces the **get_child_nodes** to select from all child nodes recursively, rather than only collecting the immediate children.

To illustrate how to extract and remove comments from a document, we will go through the following steps:

1. Open a Word document using the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) class
2. Get all comments from the document into a collection
3. To extract comments:
   1. Go through the collection using the foreach operator
   2. Extract and list the author name, date & time and text of all comments
   3. Extract and list the author name, date & time and text of comments written by a specific author, in this case the author `ks`
4. To remove comments:
   1. Go backwards through the collection using the for operator
   2. Remove comments
5. Save the changes

### How to Extract All Comments

The **get_child_nodes** method is very useful and you can use it every time you need to get a list of document nodes of any type. The resulting collection does not create an immediate overhead because the nodes are selected into this collection only when you enumerate or access items in it.

The following code example shows how to extract the author name, date&time and text of all comments in the document:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "extract-comments.py" >}}

### How to Extract Comments of a Specified Author

After you have selected **Comment** nodes into a collection, all you have to do is extract the information you need. In this sample, author initials, date, time and the plain text of the comment is combined into one string; you could choose to store it in some other ways instead.

The overloaded method that extracts the Comments from a particular author is almost the same, it just checks the author's name before adding the info into the array.

The following code example shows how to extract the author name, date&time and text of the comments by the specified author:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "extract-comments-by-author.py" >}}

### How to Remove Comments

If you are removing all comments, there is no need to move through the collection deleting comments one by one. You can remove them by calling the [clear](https://reference.aspose.com/words/python-net/aspose.words/nodecollection/clear/) method on the comments collection.

The following code example shows how to remove all comments in the document:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "remove-comments.py" >}}

When you need to selectively remove comments, the process becomes more similar to the code we used for comment extraction.

The following code example shows how to remove comments by the specified author:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "remove-comments-by-author.py" >}}

The main point to highlight here is the use of the for operator. Unlike the simple extraction, here you want to delete a comment. A suitable trick is to iterate the collection backwards from the last Comment to the first one. The reason for this if you start from the end and move backwards, the index of the preceding items remains unchanged, and you can work your way back to the first item in the collection.

The following code example shows the methods for the comments extraction and removal:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "process-comments.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Comments.docx).

{{% /alert %}}

### How to Remove a Comment between CommentRangeStart and CommentRangeEnd

Using Aspose.Words you can also remove comments between the **CommentRangeStart** and **CommentRangeEnd** nodes.

The following code example shows how to remove text between **CommentRangeStart** and **CommentRangeEnd**:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "remove-range-text.py" >}}

## Add or Remove Comment's Reply

The [add_reply](https://reference.aspose.com/words/python-net/aspose.words/comment/add_reply/) method adds a reply to this comment. Please note that due to the existing Microsoft Office limitations only 1 level of replies is allowed in the document. An exception of type **InvalidOperationException** will be raised if this method is called on the existing Reply comment.

You can use the [remove_reply](https://reference.aspose.com/words/python-net/aspose.words/comment/remove_reply/) method to remove the specified reply to this comment.

The following code example shows how to add a reply to comment and remove comment's reply:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "add-remove-comment-reply.py" >}}

## Read Comment's Reply

The [replies](https://reference.aspose.com/words/python-net/aspose.words/comment/replies/) property returns a collection of the [Comment](https://reference.aspose.com/words/python-net/aspose.words/comment/) objects that are immediate children of the specified comment.

The following code example shows how to iterate through a comment's replies and resolved them:

{{< gist "aspose-words-gists" "1b6e88920a5377e910e70fb211bcf1b3" "comment-resolved-and-replies.py" >}} 

## FAQ

1. **Q:** How can I extract all comments from a Word document using Python?  
   **A:** Load the document with `aw.Document`, then call `doc.get_child_nodes(aw.NodeType.COMMENT, True)` to obtain a `NodeCollection` of `Comment` objects. Iterate the collection to read each comment's `author`, `date_time`, and `text`. Example:  

   ```python
   doc = aw.Document("input.docx")
   comments = doc.get_child_nodes(aw.NodeType.COMMENT, True)
   for comment in comments:
       print(f"Author: {comment.author}, Date: {comment.date_time}, Text: {comment.text}")
   ```

2. **Q:** How do I extract only the comments made by a specific author?  
   **A:** After retrieving the full comment collection, filter it by the `author` property.  

   ```python
   target_author = "ks"
   for comment in comments:
       if comment.author == target_author:
           print(f"[{target_author}] {comment.text}")
   ```

3. **Q:** What is the recommended way to remove all comments or only those from a particular author?  
   **A:** For removing all comments, call `clear()` on the `NodeCollection`. To remove selectively, iterate the collection **backwards** and call `remove()` on matching comments.  

   ```python
   # Remove all
   comments.clear()

   # Remove only author "ks"
   for i in range(comments.count - 1, -1, -1):
       if comments[i].author == "ks":
           comments[i].remove()
   ```

4. **Q:** How can I add a reply to a comment and what limitation should I be aware of?  
   **A:** Use the `add_reply(author, initial, date_time, text)` method on a `Comment` object. Microsoft Word supports only one level of replies, so calling `add_reply` on a reply raises an `InvalidOperationException`.  

   ```python
   comment = comments[0]                     # first comment
   comment.add_reply("John Doe", "JD", datetime.now(), "Thanks for the suggestion.")
   ```

5. **Q:** Does `get_child_nodes` also retrieve comments that are located in headers or footers?  
   **A:** Yes. When the `recursive` parameter is set to `True`, `get_child_nodes` searches the entire document tree, including headers, footers, footnotes, and other story ranges, and returns any `Comment` nodes it finds.  

   ```python
   all_comments = doc.get_child_nodes(aw.NodeType.COMMENT, True)  # includes header/footer comments
   ```