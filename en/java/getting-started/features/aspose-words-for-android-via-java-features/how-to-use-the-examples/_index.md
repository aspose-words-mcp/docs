---
title: How to use the Examples
second_title: Aspose.Words for Java
articleTitle: How to use the Examples
linktitle: How to use the Examples
description: "How to run Aspose.Words for Android via Java examples."
type: docs
weight: 70
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/how-to-use-the-examples/
timestamp: 2024-01-27-14-07-04
---

Firstly make sure that you have the ADT bundle installed and that you have downloaded and extracted the latest version of [Aspose.Words for Android via Java](https://releases.aspose.com/words/androidjava/).

- Install Aspose.Words for Android via Java by following the instructions at [here](/words/java/installation/)
- Open the project in your workspace using Eclipse with ADT.
- Click **Run** to start and choose the appropriate emulator to run the package on.

------ 

## FAQ

1. **Q:** How do I set up the development environment to run the Aspose.Words for Android via Java examples?  
   **A:** Install the Android SDK and ADT bundle, download the Aspose.Words for Android via Java package, extract it, and open the example project in Eclipse (or Android Studio). Configure the SDK path in the IDE and ensure an Android emulator or device is available.

2. **Q:** How can I run the example projects on an Android emulator?  
   **A:** In Eclipse select the example project, choose **Run → Android Application**, and pick a configured AVD that matches the target API level. The IDE will build, install, and launch the app on the emulator. Make sure the emulator has sufficient memory and storage.

3. **Q:** Can I run the examples on a physical Android device instead of an emulator?  
   **A:** Yes. Enable **USB debugging** on the device, connect it via USB, and Eclipse will detect the device. Choose the device from the Run dialog and the example will be deployed and started on the phone or tablet.

4. **Q:** Where do I add my Aspose.Words license file in the example projects?  
   **A:** Place the license file (e.g., `Aspose.Words.lic`) in the **assets** folder of the example project. Then add the following code early in your activity (typically in `onCreate`):  

   ```java
   License license = new License();
   license.setLicense("Aspose.Words.lic");
   ```

5. **Q:** How do I modify an example to generate a PDF from my own code?  
   **A:** Use the `Document` class to load or create a document and then save it as PDF:  

   ```java
   Document doc = new Document("input.docx");
   doc.save("output.pdf", SaveFormat.PDF);
   ```  

   Replace the sample file paths with your own data and ensure the required file‑system permissions are declared in the Android manifest.