---
title: Download and Install NetCon
description: 
permalink: 
aliases: 
draft: false
date: 2024-09-30
tags:
  - GettingStarted
---
# Download and Install NetCon

### Download
You may download the Spatial Eye software from the support website (see links at the bottom of this page).

Install Spatial Workshop Ultimate and XY Server with Warehouse on your application server. The Spatial Eye service team has described best practices that you could use for the installation.

For example:

- It is recommended to work with an `environment_var.bat` file to facilitate DTAP-deployment (development -> test/ quality assurance -> user-acceptance -> production environment);
- Using a project store named after the environment to avoid mistakes;
- Using source control or data warehouse seProject naming conventions enables going back and seeing what changed, when. In particular, after an ETL spatial warehouse batch has run, the version number should be incremented and the seProject file should not be changed anymore;

### Installation of the DLLs:

- After download, first 'unblock' the downloaded files (or entire zip-file) in Windows Explorer | Properties (Alt-Enter). DLLs that are blocked by the operating system cannot be used by the software.
- Copy the NetCon DLLs for desktop to desktop add-in directory, e.g
  - C:\\Program Files\\Spatial Eye\\Spatial Workshop\\AddIns
- Copy the NetCon DLLs for server to server add-in directory, e.g
  - C:\\Program Files\\Spatial Eye\\XY Server\\AddIns

### Additional configuration for large networks

If your network is large (> 48.8 million network connections), besides having plenty internal memory in your system you will need to configure the .Net Framework to allow large data structures. In the *.config files (both for GSA or Spatial Workshop Ultimate and GSA or XY Server), enable "AllowVeryLargeObjects". Make a backup of the *.config file, open the *.config files with an XML-editor (or plain text editor), locate the configuration/runtime node, and enable gcAllowVeryLargeObjects (note, other configuration is in place, only add the ```<gcAllowVeryLargeObjects>``` node):

```xml
<configuration>
  <runtime>
    <!-- Allow for large networks ( > ~48 million connections) -->
    <gcAllowVeryLargeObjects enabled="true" />
  </runtime>
</configuration>
```

This allows the .Net runtime (64-bit) to create larger data blocks, exceeding the limits of some 32-bit runtime settings which it uses by default.
Without this setting you may encounter the following error:

> [!Error] OutOfMemoryException
> System.OutOfMemoryException: Array dimensions exceeded supported range.

See also https://learn.microsoft.com/en-us/dotnet/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element
