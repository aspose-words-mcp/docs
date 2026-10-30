---
title: System Requirements
second_title: Aspose.Words for C++
articleTitle: System Requirements
linktitle: System Requirements
description: "Before you start working with Aspose.Words for C++, ensure that you meet the operating system, platform, frameworks, and environment requirements so the activities on your devices are properly accounted for."
type: docs
weight: 5
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/system-requirements/
timestamp: 2024-07-11-16-13-28
---

Aspose.Words for C++ does not require any third party product such as Microsoft Word to be installed. Aspose.Words itself is an engine for creating, modifying, converting, and rendering of documents in various formats, including Microsoft Word document formats.

## Supported Operating Systems

Aspose.Words for C++ supports the following 64-bit or 32-bit operating system and platforms:

<table>  
   <tr>
      <td style="font-weight: bold; width:400px">Operating System</td>
      <td style="font-weight: bold; width:400px">Versions</td>
   </tr>
   <tr>
      <td>Microsoft Windows</td>
      <td><ul>
         <li>Windows 2008 Server (x64, x86)</li>
         <li>Windows 2012 Server (x64, x86)</li>
         <li>Windows 2012 R2 Server (x64, x86)</li>
         <li>Windows 2016 Server (x64, x86)</li>
         <li>Windows 2019 Server (x64, x86)</li>
         <li>Windows 2022 Server (x64, x86)</li>
         <li>Windows Vista (x64, x86)</li>
         <li>Windows 7 (x64, x86)</li>
         <li>Windows 8, 8.1 (x64, x86)</li>
         <li>Windows 10 (x64, x86)</li>
      </ul></td>
   </tr>
   <tr>
      <td>Linux</td>
      <td><ul>
         <li>Ubuntu</li>
         <li>Fedora</li>
         <li>OpenSUSE</li>
         <li>CentOS</li>
         <li>and others</li>
      </ul></td>
   </tr>
   <tr>
      <td>macOS</td>
      <td><ul>
         <li>macOS-x86_64: 12.0 or later</li>
         <li>macOS-arm64: 12.0 or later</li>
      </ul></td>
   </tr>
</table>

## Development Environment

You can use Aspose.Words for C++ when developing applications for Windows, Linux or macOS.

### Windows

Aspose.Words for C++ can be used to develop applications in any development environment which supports [Microsoft Visual Studio v143 Platform Toolset](https://docs.microsoft.com/en-us/cpp/porting/binary-compat-2015-2017), but the environments listed in the following table are explicitly supported:

<table>  
	<tr>
			<td style="font-weight: bold; width:800px">Development environments</td>
		</tr>
  <tr>
			<td><ul><li>Microsoft Visual Studio 2022</li></ul></td>
			</tr>
</table>

### Linux

Aspose.Words for C++ can be used to develop application in the development environment which support [C++14 language standard](https://en.cppreference.com/cpp/14), but the following compilers are explicitly supported:

<table>  
	<tr>
			<td style="font-weight: bold; width:800px">Compilers</td>
		</tr>
  <tr>
			<td><ul><li>Clang 3.9.1 or later</li></ul></td>
			</tr>
</table>

### Additional Dependency on Linux

Aspose.Words for C++ on Linux depends on [fontconfig](https://www.freedesktop.org/wiki/Software/fontconfig/) binaries both dynamic library and tool. Please install it before using:

1. Installing fontconfig on Ubuntu or Debian</br>
`sudo apt install libfontconfig fontconfig`
2. Installing fontconfig on Fedora or CentOs</br>
   `sudo yum install fontconfig`

### macOS

Aspose.Words for C++ can be used to develop application in the following development environments:

<table>  
	<tr>
			<td style="font-weight: bold; width:800px">Development environments</td>
		</tr>
  <tr>
			<td><ul><li>Xcode 12.5.1 or later</li><li>Clang and libc++ (which are shipped by default with Xcode)</li></ul></td>
			</tr>
</table>

### Additional Dependency on macOS

Aspose.Words for C++ on macOS depends on [fontconfig](https://www.freedesktop.org/wiki/Software/fontconfig/) binaries both dynamic library and tool. Please install it before using:

Installing fontconfig on macOS with [homebrew](https://brew.sh)</br>
`brew install fontconfig`

------  

## FAQ

1. **Q:** Which operating systems can I run Aspose.Words for C++ on?  
   **A:** The library supports 64‑bit and 32‑bit versions of Windows (2008 Server through Windows 10), major Linux distributions such as Ubuntu, Fedora, OpenSUSE, CentOS, and macOS 12.0 or later for both x86_64 and arm64 architectures.

2. **Q:** Do I need Microsoft Word or any other Office product installed on the target machine?  
   **A:** No. Aspose.Words for C++ is a self‑contained engine and does not rely on Microsoft Word, Office, or any other third‑party Office component.

3. **Q:** What extra packages must be installed on Linux or macOS before using the library?  
   **A:** Both platforms require the **fontconfig** library (runtime binaries and tools). On Linux install `libfontconfig` via the package manager (`apt`, `yum`, etc.). On macOS install it with Homebrew: `brew install fontconfig`.

4. **Q:** Which compilers and language standards are required for building on Linux?  
   **A:** The library requires a compiler that supports the C++14 standard. Currently, Clang 3.9.1 or later is officially supported. Any compiler meeting C++14 compliance can be used, but Clang is the recommended choice.

5. **Q:** How do I apply a license for Aspose.Words for C++?  
   **A:** Create an instance of `Aspose::Words::License`, then call its `SetLicense` method with the path to your `.lic` file, e.g.:  

   ```cpp
   auto license = System::MakeObject<Aspose::Words::License>();
   license->SetLicense(u"myLicenseFile.lic");
   ```  

   The license must be loaded before any document processing operations to enable the licensed features.