---
title: Perl
second_title: Aspose.Words for Java
articleTitle: Perl and Aspose.Words for Java
linktitle: Perl and Aspose.Words for Java
type: docs
description: "Perl: how to use Aspose.Words for Java."
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/perl-and-aspose-words-for-java/
timestamp: 2024-01-27-14-07-04
---

## Prerequisites

{{% alert color="primary" %}}

The **Inline::Java** module allows you to put Java source code directly "inline" in a Perl script or module. A Java compiler is launched and the Java code is compiled. Then Perl asks the `Java` classes what public methods have been defined. These classes and methods are available to the Perl program as if they had been written in Perl. See [search.cpan.org](https://metacpan.org/dist/Inline-Java) to learn more about Inline::Java.

Here are the steps to install the Inline::Java module: 

1. Install the Inline::Java module from CPAN: **C:\Perl\bin> cpan Inline::Java** 
1. Set path to your JDK: **C:\Perl\bin> set** **PERL** **_INLINE_JAVA_J2SDK=C:\Program Files\Java\jdk1.6.0_03** 

Download the [latest version of Aspose.Words for Java](https://releases.aspose.com/words/java/) . Extract files and copy the lib folder with jar files to the root folder of your project. 

{{% /alert %}}

## Hello World!

This is a simple application that creates an empty document, inserts some content and saves it as a Microsoft Word .DOC document.

**Perl**

{{< highlight csharp >}}

#!C:\Perl\bin\perl.exe

use Inline Java => <<'END_OF_JAVA_CODE', CLASSPATH=> 'lib/Aspose.Words.jdk16.jar';
    import com.aspose.words.*;
    class Words
    {
        public Words()
        {
        }
        public void HelloWorld() throws Exception
        {
            //Create new Document
            Document doc = new Document();
            //Create DocumentBuilder
            DocumentBuilder builder = new DocumentBuilder(doc);
            //Insert some text into the document
            builder.write("Hello world!!!");
            //Save output document
            doc.save("C:\\Temp\\out.doc");
        }
    }
END_OF_JAVA_CODE
my $words = new Words();
$words->HelloWorld();
{{< /highlight >}}

You can also use Aspose.Words classes directly from Perl, without writing Java code. The `study` option of Inline::Java makes the listed Java classes available in Perl:

**Perl**

{{< highlight csharp >}}
use Inline (
    Java => 'study',
    study => ['com.aspose.words.Document', 'com.aspose.words.DocumentBuilder'],
    classpath => 'lib/Aspose.Words.jdk16.jar',
);

my $doc = new com::aspose::words::Document();
my $builder = new com::aspose::words::DocumentBuilder($doc);
$builder->write("Hello world!");
$doc->save("C:\\Temp\\out.doc");
{{< /highlight >}}

## Simple Mail Merge

Aspose.Words provides a reporting generation facility similar to Microsoft Word's mail merge. Here is a code example to perform a simple Mail Merge using Aspose.Words.

**Perl**

{{< highlight csharp >}}

#!C:\Perl\bin\perl.exe

use Inline Java => <<'END_OF_JAVA_CODE', CLASSPATH=> 'lib/Aspose.Words.jdk16.jar';
    import com.aspose.words.*;
    class Words
    {
        public Words()
        {
        }
        public void MailMerge() throws Exception
        {
            //Open template document
            Document doc = new Document("C:\\Temp\\in.doc");
            //Fill the merge fields with data
            doc.getMailMerge().execute(
                new String[] { "FullName", "Company", "City" },
                new Object[] { "James Bond", "MI5", "London" });
            //Save generated document
            doc.save("C:\\Temp\\out.doc");
        }
    }
END_OF_JAVA_CODE
my $words = new Words();
$words->MailMerge();
{{< /highlight >}}

## Save or Convert a Document

With Aspose.Words, you can save a document in a variety of formats. For the full list of formats and identifiers see the **SaveFormat** enumeration. 

**Perl**

{{< highlight csharp >}}

#!C:\Perl\bin\perl.exe

use Inline Java => <<'END_OF_JAVA_CODE', CLASSPATH=> 'lib/Aspose.Words.jdk16.jar';
    import com.aspose.words.*;
    class Words
    {
        public Words()
        {
        }
        public void SaveInFormats() throws Exception
        {
            //Open the document
            Document doc = new Document("C:\\Temp\\in.doc");
            //The SaveFormat value sets the output format
            doc.save("C:\\Temp\\out.doc", SaveFormat.DOC);
            doc.save("C:\\Temp\\out.txt", SaveFormat.TEXT);
            doc.save("C:\\Temp\\out.html", SaveFormat.HTML);
            doc.save("C:\\Temp\\out.rtf", SaveFormat.RTF);
            doc.save("C:\\Temp\\out.docx", SaveFormat.DOCX);
        }
    }
END_OF_JAVA_CODE
my $words = new Words();
$words->SaveInFormats();
{{< /highlight >}}
