---
title: Convert a Document in Java
second_title: Aspose.Words for Java
articleTitle: Convert a Document
linktitle: Convert a Document
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/convert-a-document/
aliases: [/java/converting-a-document/]
description: "Easily convert documents from one format to another. You can work with all the most popular formats like Microsoft Word formats such as DOCX or DOC, OpenDocument formats such as ODT or  OTT, web formats such as HTML or XHTML, text formats such as MarkDown or TXT, and others using Java."
timestamp: 2024-09-25-11-08-55
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes the general workflow for converting documents between different formats and highlights key considerations for successful conversions.

{{% /alert %}}

The ability to easily and reliably convert documents from one format to another is one of the main feature areas of Aspose.Words. Such a conversion is nothing more than a combination of loading and saving operations.

## What Is Document Conversion {#what-is-document-conversion}

Almost any task that you want to perform with Aspose.Words involves loading or saving a document in some format. As mentioned in previous sections, the [LoadFormat](https://reference.aspose.com/words/java/com.aspose.words/loadformat/) enumeration specifies all *load* or *import* formats supported by Aspose.Words, and the [SaveFormat](https://reference.aspose.com/words/java/com.aspose.words/saveformat/) enumeration specifies all *save* or *export* formats supported by Aspose.Words. Thus, Aspose.Words can convert a document from any supported load format into any supported save format. As a rule, such a conversion requires several stages of calculation. However from the user perspective conversion from a document format to another one is itself very simple, and can be accomplished with just two steps:

1. Load your document into a [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) object using one of its constructors.
2. Invoke one of the [save()](https://reference.aspose.com/words/java/com.aspose.words/document/#save-java.lang.String-int) methods on the **Document** object and specify the desired output format.

{{% alert color="primary" %}}

**Try online**

You can try the conversion functionality by using our [Free online converter](https://products.aspose.app/words/conversion) tool.

{{% /alert %}}

## Popular Conversions {#popular-conversions}

The current section describes popular conversions, as well as ideas for working with some combinations of formats when loading and saving.  Using the examples of this section, you can understand that the conversion process itself is quite universal, and there is no point in describing all the possible options, since there are several hundred of them due to the large number of [formats supported by Aspose.Words for Java](/words/java/supported-document-formats/).

{{% alert color="primary" %}}

Please note that below are the most popular conversion combinations, and not every combination is linked to the definite page. This is the case because our articles do not have examples for every pair of conversions – almost all conversions are pretty similar. Make sure of this by studying the articles in the current section.

{{% /alert %}}

<div class="row">
	<div class="col-md-6">
		<h2>Convert Word to PDF</h2>
			<ul>
				<li><a href="/words/java/convert-a-document-to-pdf/#converting-doc-or-docx-to-pdf">Convert DOC to PDF</a></li>
				<li><a href="/words/java/convert-a-document-to-pdf/#converting-doc-or-docx-to-pdf">Convert DOCX to PDF</a></li>
				<li>and others</li>
			</ul>
		<h2>Convert Image to PDF</h2>
			<ul>
				<li><a href="/words/java/convert-a-document-to-pdf/#convert-an-image-to-pdf">Convert JPG to PDF</a></li>
				<li><a href="/words/java/convert-a-document-to-pdf/#convert-an-image-to-pdf">Convert TIFF to PDF</a></li>
				<li>and others</li>
			</ul>
		<h2>Convert Web to PDF</h2>
			<ul>
				<li>Convert Markdown to PDF</li>
				<li>Convert HTML to PDF</li>
				<li>Convert MHT (MHTML) to PDF</li>
				<li>and others</li>
			</ul>
		<h2>Convert Other Formats  to PDF</h2>
			<ul>
				<li>Convert RTF to PDF</li>
				<li>Convert ODT to PDF</li>
				<li>Convert TXT to PDF</li>
				<li>Convert Mobi to PDF</li>
				<li>and others</li>
			</ul>
	</div>
	<div class="col-md-6">
		<h2>Convert a Document to an Image</h2>
			<ul>
				<li><a href="/words/java/convert-a-document-to-an-image/">Convert DOCX to JPG</a></li>
				<li>Convert DOC to PNG</li>
				<li>and others</li>
			</ul>
		<h2>Convert a Document to Markdown</h2>
			<ul>
				<li><a href="/words/java/convert-a-document-to-markdown/">Convert a Document to Markdown</a></li>
				<li>Convert HTML to Markdown</li>
				<li>and others</li>
			</ul>
		<h2>Convert a Document to HTML</h2>
			<ul>
				<li><a href="/words/java/convert-a-document-to-html-mhtml-or-epub/#convert-a-document">Convert Word to HTML</a></li>
				<li>Convert Markdown to HTML</li>
				<li>Convert Mobi to EPUB</li>
				<li>and others</li>
			</ul>
		<h2>Work a Document in a Database</h2>
			<ul>
				<li><a href="/words/java/serialize-and-work-with-a-document-in-a-database/">Serialize and Work with a Document in a Database</a></li>
			</ul>
		<h2>Other Examples</h2>
			<ul>
				<li><a href="/words/java/convert-a-document-to-mhtml-and-send-it-by-email/">Convert a Document to MHTML and Send It by Email</a></li>
				<li>Convert DOCX to DOC</li>
				<li>Convert HTML to Word</li>
				<li>and others</li>
			</ul>
	</div>
</div>

------

## FAQ

1. **Q: How do I convert a Word document to PDF using Aspose.Words for Java?**  
   **A:** Load the source file with `Document doc = new Document("input.docx");` and then call `doc.save("output.pdf", SaveFormat.PDF);`. The `SaveFormat` enumeration defines the target format.

2. **Q: Which file formats can Aspose.Words for Java load and save?**  
   **A:** The library supports dozens of formats. Loading formats are listed in the `LoadFormat` enum (e.g., DOC, DOCX, RTF, ODT, HTML, MHTML, MD, TXT). Saving formats are listed in the `SaveFormat` enum (e.g., PDF, PNG, JPEG, HTML, EPUB, MD, TXT). See the supported‑document‑formats page for the full list.

3. **Q: Can I convert a Markdown file to PDF or Word directly?**  
   **A:** Yes. Load the Markdown file with `Document doc = new Document("input.md");` and then save it to the desired format, for example `doc.save("output.pdf", SaveFormat.PDF);` or `doc.save("output.docx", SaveFormat.DOCX);`.

4. **Q: How do I convert a password‑protected document?**  
   **A:** First set the password on the `LoadOptions` object, load the document, then save it without the password (or with a new one). Example:  
   ```java
   LoadOptions loadOptions = new LoadOptions();
   loadOptions.setPassword("oldPassword");
   Document doc = new Document("protected.docx", loadOptions);
   doc.save("unprotected.pdf", SaveFormat.PDF);
   ```

5. **Q: Do I need a license to perform document conversion in production?**  
   **A:** A license is not required for basic conversion, but without a license the output will contain a watermark and evaluation limits apply. Apply a license by loading the `.lic` file with `License license = new License(); license.setLicense("Aspose.Words.Java.lic");`. This removes watermarks and unlocks full functionality.