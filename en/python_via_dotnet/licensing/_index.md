---
title: Licensing and Subscription
second_title: Aspose.Words for Python via .NET
articleTitle: Licensing and Subscription
linktitle: Licensing and Subscription
description: "Aspose.Words for Python via .NET provides different plans for purchase or offers a Free Trial and a 30-day Temporary License for evaluation using Licensing and Subscription policies."
type: docs
weight: 13
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/licensing/
aliases: [/python/licensing/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains the licensing options for Aspose.Words for Python via .NET, including free trial, temporary, purchased, and metered licenses, and provides guidance on applying licenses via files, streams, or metered keys.  
{{% /alert %}}

Sometimes, in order to study the system better, you want to dive into the code as fast as possible. To make this easier, Aspose.Words provides different plans for purchase or offers a Free Trial and a 30-day Temporary License for evaluation.

{{% alert color="primary" %}}

Note that there are a number of general policies and practices that guide you on how to evaluate, properly license, and purchase our products. You can find them in the [Purchase Policies and FAQ](https://purchase.aspose.com/policies/) section.

{{% /alert %}}

## Free Trial or Temporary License

Aspose.Words is incredible software that developers can try before purchasing.

### Free Trial

The evaluation version is the same as the purchased one – the trial version simply becomes licensed when you add a few lines of code to apply the license.

The Trial version of Aspose.Words without the specified license provides full product functionality, but inserts an evaluative watermark at the top of the document upon loading and saving and limits the maximum document size to a few hundred paragraphs.

### Temporary License

If you wish to test Aspose.Words without the limitations of the Trial version, you can also request a 30-day Temporary License. For more details, see the [Get a Temporary License](https://purchase.aspose.com/temporary-license/) page.

## Purchased License

After purchase, you need to apply the license file or stream. This section describes options of how this can be done, and also comments on some common questions.

{{% alert color="primary" %}}

You need to set the license:

* only once per application domain

* before using any other Aspose.Words classes

{{% /alert %}}

{{% alert color="primary" %}}

You can find pricing information on the [Pricing Information](https://purchase.aspose.com/pricing/words/family/) page.

{{% /alert %}}

### Protecting Your Purchased License

After purchasing a license, you need to carefully read the information on page [Protecting Your Purchased License](https://purchase.aspose.com/orders/protecting-your-license-file) to protect your license file. Please note that this page is available for viewing only if you have a paid license.

### License Applying Options

Licenses can be applied from various locations:

* Explicit path
* The folder containing the python script that calls Aspose.Words for Python via .NET
* Stream
* As a Metered License – a new licensing mechanism

{{% alert color="primary" %}}

Use the [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) method to license a component.

Calling [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) multiple times is not harmful, it just wastes processor time.

Calling [set_metered_key](https://reference.aspose.com/words/python-net/aspose.words/metered/set_metered_key/#str_str) multiple times is not harmful either, but just wastes processor time and can accumulate consumption improperly.

{{% /alert %}}

#### Apply License Using a File or Stream Object

When developing your application, call [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) in your startup code before using Aspose.Words classes.

##### Load a License from a File

Using the [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) method, you can try to find the license file in the embedded resources or assembly folders for further use.

The following code example shows how to initialize a license from a folder:

{{< gist "aspose-words-gists" "45c97d37bef13067c82e741b922a2d4f" "apply-license-from-file.py" >}}

##### Load a License from a `Stream` Object

The following code example shows how to initialize a license from a stream using another [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) method:

{{< gist "aspose-words-gists" "45c97d37bef13067c82e741b922a2d4f" "apply-license-from-stream.py" >}}

#### Apply Metered License

Aspose.Words allows developers to apply a metered key. This is a new licensing mechanism.

The new licensing mechanism will be used along with the existing licensing method. Those customers who want to be billed based on the use of API features can use the Metered Licensing.

After completing all the necessary steps to obtain this type of license, you will receive the keys, not the license file. This metered key can be applied using the [Metered](https://reference.aspose.com/words/python-net/aspose.words/metered/) class specially introduced for this purpose.

Do not call the **set_metered_key** method frequently so that this licensing method properly accumulates consumption and reports it to us. Just instantiate the Aspose.Words library, call **set_metered_key** once, then leave the library instantiated and reuse it.

The following code example shows how to set metered public and private keys:

{{< gist "aspose-words-gists" "45c97d37bef13067c82e741b922a2d4f" "apply-metered-license.py" >}}

Normally it is enough to apply the metered license once on application start. However, if the metered licensing mechanism fails to communicate with the Aspose servers for 24 hours, Aspose.Words will exit licensed mode and switch to evaluation mode. To avoid such case, you can use the [is_metered_licensed](https://reference.aspose.com/words/python-net/aspose.words/metered/is_metered_licensed/#default) method to check the license status and reapply the metered license if necessary.

{{% alert color="primary" %}}

Please note that you must have a stable Internet connection for the correct use of the Metered license, since the Metered mechanism requires the constant interaction with our services for correct calculations. For more details, refer to the [Metered Licensing FAQ](https://purchase.aspose.com/faqs/licensing/metered/) section.

{{% /alert %}}

### Changing the License File Name

The license filename does not have to be "Aspose.Words.Python.NET.lic". You can rename it to your liking and use that name when setting a license in your application.

### “Cannot find license filename” Exception

When you purchase and download a license, the Aspose website names the license file *"Aspose.Words.Python.NET.lic"*. You download the license file using your browser. In this case, some browsers recognize the license file as XML and append the .xml extension to it, so the full file name on your computer becomes *"Aspose.Words.Python.NET.lic.XML"*.

When Microsoft Windows is configured to hide extensions for known file types (unfortunately, this is the default in most Windows installations), the license file will appear as *"Aspose.Words.Python.NET.lic"* in Windows Explorer. You will probably think that this is the real file name and call [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) passing it *"Aspose.Words.Python.NET.lic"*, but there is no such file, hence the exception.

To solve the problem, rename the file to remove the invisible .xml extension. We also recommend you disable the "hide extensions" option in Microsoft Windows.

## Using Multiple Aspose Products

If you use multiple Aspose products in your application, such as Aspose.Words and `Aspose.Cells`, here are a few useful tips:

* Set the License for each Aspose product separately. Even if you have a single license file for all components, for example, "Aspose.Total.Python.NET.lic", you still need to call [set_license](https://reference.aspose.com/words/python-net/aspose.words/license/set_license/) separately for each Aspose product that you use in your application.
* Use the Fully Qualified License Class Name. Each Aspose product has a **License** class in its own namespace. For example, Aspose.Words has [aspose.words.License](https://reference.aspose.com/words/python-net/aspose.words/license/) and `Aspose.Cells` has **aspose.cells.License** class. Using the fully qualified class name allows you to avoid confusion as to which license applies to which product.

------ 

## FAQ

1. **Q:** How do I apply a license from a file in Python via .NET?  
   **A:** Call `aspose.words.License().set_license("path/to/your/license.file")` early in your application, before creating any Aspose.Words objects. The method searches the specified path and loads the XML license. If the file is in the same folder as your script, you can pass just the file name.

2. **Q:** I get a “Cannot find license filename” exception – what should I check?  
   **A:** Verify that the actual file name matches what you pass to `set_license`. Windows may hide the “.xml” extension added by the browser, resulting in a name like `Aspose.Words.Python.NET.lic.XML`. Rename the file to remove the hidden extension or disable “hide extensions” in Explorer, then provide the correct name to `set_license`.

3. **Q:** Can an Aspose.Total .NET license be used with Aspose.Words for Python via .NET?  
   **A:** No. A .NET license is not valid for this product. Use an Aspose.Words for Python via .NET license (`Aspose.Words.Python.NET.lic`) or an Aspose.Total for Python via .NET license (`Aspose.Total.Python.NET.lic`). With an Aspose.Total license, call `set_license` for each product you use (e.g., `aspose.words.License().set_license(...)` and `aspose.cells.License().set_license(...)`).

4. **Q:** What are the requirements for using a metered license?  
   **A:** Obtain the public and private keys from the Aspose portal, then call `aspose.words.Metered.set_metered_key(public_key, private_key)`. A stable Internet connection is required because the library contacts Aspose servers to record usage. Call this once at startup; if connectivity is lost for more than 24 hours, the library reverts to evaluation mode, so you may need to re‑apply the key.

5. **Q:** Is it safe to call `set_license` multiple times in my code?  
   **A:** Yes. Re‑calling `set_license` does not cause errors, but it adds unnecessary overhead. It is best practice to set the license once during application initialization and avoid repeated calls.