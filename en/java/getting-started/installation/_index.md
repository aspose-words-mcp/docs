---
title: Installation
second_title: Aspose.Words for Java
articleTitle: Installation
linktitle: Installation
description: "Install Aspose.Words for Java from Maven repository. Define the Aspose.Words for Java dependency in your pom.xml"
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/installation/
timestamp: 2024-01-27-14-07-04
---

Make sure your machine meets the [system requirements](/words/java/system-requirements/) before you begin.

This article explains how to install Aspose.Words for Java on your computer.

## Install Aspose.Words for Java from Maven Repository {#install-aspose-words-for-java-from-maven-repository}

Aspose hosts all Java APIs in [Maven repository](https://releases.aspose.com/words/java/). You can easily use Aspose.Words for Java API directly in your Maven Projects with simple configurations:

1. First, you need to specify Aspose Maven Repository configuration/location in your Maven pom.xml as shown below:
	{{< highlight html >}}
	<repositories>
		<repository>
			<id>AsposeJavaAPI</id>
			<name>Aspose Java API</name>
			<url>https://releases.aspose.com/java/repo/</url>
		</repository>
	</repositories>
	{{< /highlight >}}
2. Then, define the Aspose.Words for Java API dependency in your pom.xml as follows:
	{{< highlight html >}}
	<dependencies>
		<dependency>
			<groupId>com.aspose</groupId>
			<artifactId>aspose-words</artifactId>
			<version>22.11</version>
			<classifier>jdk17</classifier>
		</dependency>
		<dependency>
			<groupId>com.aspose</groupId>
			<artifactId>aspose-words</artifactId>
			<version>22.11</version>
			<classifier>javadoc</classifier>
		</dependency>
	</dependencies>
	{{< /highlight >}}
3. Congratulations! You have successfully defined the Aspose.Words for Java dependency in your Maven project.

## See Also

* [Download Aspose.Words from Maven](https://releases.aspose.com/words/java/)

------ 

## FAQ

1. **Q:** How do I apply a license for Aspose.Words for Java?  
   **A:** Place the license file (e.g., `Aspose.Words.Java.lic`) in a location accessible to your application and load it at startup:

   ```java
   com.aspose.words.License license = new com.aspose.words.License();
   license.setLicense("path/to/Aspose.Words.Java.lic");
   ```

   Loading the license disables evaluation limitations for the entire JVM process.

2. **Q:** Which Maven repository should I use for Aspose.Words for Java?  
   **A:** Use the Aspose Maven repository `https://releases.aspose.com/java/repo/`. Add it to the `<repositories>` section of your `pom.xml` as shown in the installation steps. This repository hosts all supported versions of the library.

3. **Q:** How can I select a specific version of Aspose.Words for Java?  
   **A:** Set the desired version number in the `<version>` element of the dependency. For example, `<version>22.11</version>` uses version 22.11. You can browse available versions on the Aspose Maven repository page.

4. **Q:** What Java versions are supported by the Aspose.Words for Java library?  
   **A:** The library provides classifiers for different JDKs (e.g., `jdk8`, `jdk11`, `jdk17`). Choose the classifier that matches the JDK you compile and run against. The `jdk17` classifier is recommended for Java 17 and later.

5. **Q:** Do I need to include the `javadoc` classifier in my Maven dependency?  
   **A:** The `javadoc` classifier is optional and only provides API documentation JARs. It is not required for runtime functionality. You can omit it if you do not need the generated Javadoc files.