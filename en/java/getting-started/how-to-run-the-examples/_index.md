---
title: How to Run the Examples
second_title: Aspose.Words for Java
articleTitle: How to Run the Examples
linktitle: How to Run the Examples
type: docs
description: "Download Aspose.Words for Java examples from our GitHub repository and learn how to run them to become more familiar with the Aspose.Words possibilities and features."
weight: 130
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/how-to-run-the-examples/
timestamp: 2024-01-27-14-07-04
---

## Download from GitHub

All examples of Aspose.Words for Java are hosted on [Github](https://github.com/aspose-words/Aspose.Words-for-Java). You can either clone the repository using your favorite Github client or download the ZIP file from [here](https://github.com/aspose-words/Aspose.Words-for-Java/archive/master.zip).

Extract the contents of ZIP file to any folder on your computer. All the examples are located in the **Examples** folder.

![how-to-run-examples-aspose-words-java-1](how-to-run-examples-aspose-words-java-1.png)

The project uses Maven build system. Any modern IDE can easily open or import the project and its dependencies. Below we show you how to use popular IDEs to build and run the examples.

## IntelliJ IDEA

Click on the **File** menu and choose **Open**. Browse to the project folder and select the **pom.xml** file.

![how-to-run-examples-aspose-words-java-2](how-to-run-examples-aspose-words-java-2.png)

It will open the project and download the dependencies automatically. From the Project tab, browse the examples in **src/main/java** folder. To run an example, just right click on the file and choose "Run ..", the example will be executed and the output will be shown in the built in console output window.

![how-to-run-examples-aspose-words-java-3](how-to-run-examples-aspose-words-java-3.png)

## Eclipse

Click on **File** menu and choose **Import**. Select **Maven** - Existing Maven Projects.

![how-to-run-examples-aspose-words-java-4](how-to-run-examples-aspose-words-java-4.png)

Browse to the folder that you cloned or downloaded from GitHub and select **pom.xml** file.

![how-to-run-examples-aspose-words-java-5](how-to-run-examples-aspose-words-java-5.png)

It will open the project and download the dependencies automatically. From the Package Explorer tab, browse the examples in **src/main/java** folder. To run an example, just right click on the file and choose **Run As** - **Java Application**, the example will be executed and the output will be shown in the built in console output window.

![how-to-run-examples-aspose-words-java-6](how-to-run-examples-aspose-words-java-6.png)

## NetBeans

Click on the **File** menu and choose **Open Project**. Browse to the folder that you cloned or downloaded from GitHub. The icon of **Examples** folder will show that its a Maven project. Select Examples and open it.

![how-to-run-examples-aspose-words-java-7](how-to-run-examples-aspose-words-java-7.png)

It will open the project and download the dependencies automatically. From the Projects tab, browse the examples in **source packages**. To run an example, just right click on the file and choose **Run File**, the example will be executed and the output will be shown in the built in console output window.

![how-to-run-examples-aspose-words-java-8](how-to-run-examples-aspose-words-java-8.png)

## Contribute

If you like to add or improve an example, we encourage you to contribute to the project. All examples and showcase projects in this repository are open source and can be freely used in your own applications.

To contribute, you can fork the repository, edit the source code and create a pull request. We will review the changes and include it in the repository if found helpful.

------

## FAQ


1. **Q:** How can I build and run the Aspose.Words for Java examples from the command line?  
   **A:** Open a terminal in the `Examples/DocsExamples/Java` folder of the cloned repository (the folder with `pom.xml`) and run `mvn test -Dtest=<ClassName>`. The examples are TestNG tests in `src/main/java`; Maven downloads the dependencies, compiles the sources, and runs the tests of the specified class.

2. **Q:** Which Java Development Kit (JDK) version is required for the examples?  
   **A:** The examples target JDK 8 or higher. Using a recent LTS JDK (e.g., 11, 17) is recommended to avoid compatibility warnings and to benefit from the latest language features and performance improvements.

3. **Q:** Do I need a license file to run the example projects?  
   **A:** A license is not mandatory for running the examples; they work in evaluation mode with limited functionality (e.g., watermarks). To test full features, place a valid `Aspose.Words.Java.lic` file in the project's root directory or set the license programmatically as shown in the “Licensing” example.

4. **Q:** How do I run a specific example in IntelliJ IDEA, Eclipse, or NetBeans?  
   **A:** Open the class that contains the example (under `src/main/java/DocsExamples`). The examples are TestNG test methods: right‑click the method or the class and run it with the IDE's test runner (TestNG support is needed in Eclipse). The IDE compiles the class and displays the console output.

5. **Q:** Can I run the examples on Linux or macOS without an IDE?  
   **A:** Yes. After installing Maven and a compatible JDK, use the same command‑line approach described above. Ensure that the `JAVA_HOME` environment variable points to your JDK installation, then execute the Maven command to run any example.
