---
title: System Requirements
second_title: Aspose.Words for Python via .NET
articleTitle: System Requirements
linktitle: System Requirements
description: "Before you start working with Aspose.Words for Python via .NET, ensure that you meet the operating system, platform and environment requirements so the activities on your devices are properly accounted for."
type: docs
weight: 5
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/system-requirements/
aliases: [/python/system-requirements/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page lists the operating systems, platforms, and native dependencies required to run Aspose.Words for Python via .NET, including supported Windows, macOS, and Linux versions and specific library prerequisites.

{{% /alert %}}

Aspose.Words for Python via .NET does not require any third party product such as Microsoft Word to be installed. Aspose.Words itself is an engine for creating, modifying, converting, and rendering of documents in various formats, including Microsoft Word document formats.

## Supported Operating Systems

Aspose.Words for Python via .NET supports any 64-bit or 32-bit operating system where Python 3.5 or later is installed.

<table>  
    <tr>
        <td style="font-weight: bold; width:400px">Operating System</td>
        <td style="font-weight: bold; width:400px">Versions</td>
    </tr>
    <tr>
        <td>Microsoft Windows</td>
        <td><ul>
            <li>Windows 2003 Server (x64, x86)</li>
            <li>Windows 2008 Server (x64, x86)</li>
            <li>Windows 2012 Server (x64, x86)</li>
            <li>Windows 2012 R2 Server (x64, x86)</li>
            <li>Windows 2016 Server (x64, x86)</li>
            <li>Windows 2019 Server (x64, x86)</li>
            <li>Windows XP (x64, x86)</li>
            <li>Windows Vista (x64, x86)</li>
            <li>Windows 7 (x64, x86)</li>
            <li>Windows 8, 8.1 (x64, x86)</li>
            <li>Windows 10 (x64, x86)</li>
        </ul></td>
    </tr>
    <tr>
        <td>macOS</td>
        <td><ul>
            <li>macOS-x86_64: 10.14 or later</li>
            <li>macOS-arm64: 11.0 or later</li>
        </ul></td>
    </tr>
    <tr>
        <td>Linux</td>
        <td><ul>
            <li>Ubuntu</li>
            <li>OpenSUSE</li>
            <li>CentOS</li>
            <li>and others</li>
        </ul></td>
    </tr>
</table>

## System Requirements for Target Linux and macOS Platforms

- GCC-6 runtime libraries (or later).

- Dependencies of .NET Core Runtime. Installing .NET Core Runtime itself is `NOT` required.

- For Python 3.5-3.7: The `pymalloc` build of Python is needed. The `--with-pymalloc` Python build option is enabled by default. Typically, the `pymalloc` build of Python is marked with `m` suffix in the filename.

- `libpython` shared Python library. The `--enable-shared` Python build option is disabled by default, some Python distributions do not contain the `libpython` shared library. For some linux platforms, the `libpython` shared library can be installed using the package manager, for example: `sudo apt-get install libpython3.7`. The common issue is that `libpython` library is installed in a different location than the standard system location for shared libraries. The issue can be fixed by using the Python build options to set alternate library paths when compiling Python, or fixed by creating a symbolic link to the `libpython` library file in the system standard location for shared libraries. Typically, the `libpython` shared library file name is `libpythonX.Ym.so.1.0` for Python 3.5-3.7, or `libpythonX.Y.so.1.0` for Python 3.8 or later (for example: libpython3.7m.so.1.0, libpython3.9.so.1.0).

Supported Linux configurations are presented in [Aspose.Words-for-Python-via-.NET/Dockerfile](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Dockerfile).

------ 

## FAQ

1. **Q:** Does Aspose.Words for Python via .NET run on Linux and macOS?  
   **A:** Yes. The library supports most 64‑bit and 32‑bit Linux distributions (Ubuntu, OpenSUSE, CentOS, etc.) and macOS versions 10.14+ (x86_64) and 11.0+ (arm64). Only the standard GCC‑6+ runtime and .NET Core dependencies are required; the .NET runtime itself does not need to be installed separately.

2. **Q:** Do I need Microsoft Word or any other Office product installed on the machine?  
   **A:** No. Aspose.Words is a self‑contained engine and works independently of Microsoft Word or any other third‑party Office suite.

3. **Q:** Can a .NET license (e.g., Aspose.Total.NET.lic) be used with the Python‑via‑.NET API?  
   **A:** No. Licenses are product-specific: use an Aspose.Words for Python via .NET license (`Aspose.Words.Python.NET.lic`) or an Aspose.Total for Python via .NET license (`Aspose.Total.Python.NET.lic`). Learn more about licensing on page [Licensing and Subscription](/words/python-net/licensing/).

4. **Q:** What additional libraries are required on Linux for Python 3.5‑3.7?  
   **A:** You must have the `pymalloc` build of Python and the `libpython` shared library (e.g., `libpython3.7m.so.1.0`). Install it via the package manager (`sudo apt-get install libpython3.7`) or create a symbolic link to the library if it resides in a non‑standard location.

5. **Q:** Is the .NET Core Runtime required to be installed on the target machine?  
   **A:** No. The Aspose.Words for Python via .NET package bundles the necessary .NET Core runtime components, so a separate installation of .NET Core Runtime is not needed. Only the native dependencies listed above must be present.