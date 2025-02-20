---
title: desktop:Extension
description: Declares an extensibility point for the app (desktop:Extension).
ms.date: 10/19/2022
ms.topic: reference
keywords: windows 10, uwp, schema, manifest, desktop, extension 
---

# desktop:Extension

Declares an extensibility point for the app.

## Element hierarchy

[\<Package\>](element-package.md)

&nbsp;&nbsp;&nbsp;&nbsp;[\<Applications\>](element-applications.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[<\Application\>](element-application.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;[<\Extensions\>](element-1-extensions.md)

&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;**<\Desktop:Extension\>**

## Syntax

```xml
<desktop:Extension
  Category = 'A string value that can be one of the following values: "windows.fullTrustProcess", "windows.startupTask", "windows.toastNotificationActivation", or "windows.searchProtocolHandler".'
  Executable = 'An optional string with a value between 1 and 256 characters in length that must end with ".exe" and cannot contain these characters: <, >, :, ", |, ?, or *. It specifies the default executable for the extension. If not specified, the executable defined for the app is used.  If specified, the EntryPoint property is also used. If that EntryPoint property isnt specified, the EntryPoint defined for the app is used.'
  EntryPoint = 'An optional string with a value between 1 and 256 characters in length, representing the  task handling the extension. This is normally the fully namespace-qualified name of a Windows Runtime type. If EntryPoint is not specified, the EntryPoint defined for the app is used instead.'
  RuntimeType = 'An optional string with a value between 1 and 255 characters in length that cannot start or end with a period or contain these characters: <, >, :, ", /, \, |, ?, or *.'
  StartPage = 'An optional string with a value between 1 and 256 characters in length that cannot contain these characters: <, >, :, ", |, ?, or *.'
  ResourceGroup =  'An optional alphanumeric string with a value between 1 and 255 characters in length. Must begin with a letter.'
  uap10:TrustLevel = 'An optional string that can have one of the following values: "appContainer" or "mediumIL".'
  uap10:RuntimeBehavior = 'An optional string that can have one of the following values: "windowsApp", "packagedClassicApp", or "win32App".'
  uap10:HostId = 'An optional alphanumeric string with a value between 1 and 255 characters in length. Must begin with an alphabetic character.'
  uap10:Parameters = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  previewappcompat:CompatMode = 'An optional string that can have one of the following values: "classic" or "modern".'
  previewappcompat:Scope = 'An optional string that can be one of the following values: "user" or "machine".'
  uap11:Id = 'An optional string with a value between 1 and 256 characters in length.'
  uap11:Subsystem = 'An optional string that can have one of the following values: "console" or "windows".'
  uap11:SupportsMultipleInstances = 'An optional boolean value.'
  uap11:ResourceGroup = 'An optional alphanumeric string with a value between 1 and 255 characters in length. Must begin with a letter.'
  uap11:CurrentDirectoryPath = 'An optional string with a value between 1 and 256 characters in length that cannot contain these characters: <, >, :, ", |, ?, or *.'
  uap11:Parameters = 'An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end.'
  desktop7:CompatMode = 'A string that can have one of the following values: "classic" or "modern".'
  desktop7:Scope = 'A string that can have one of the following values: "machine" or "user".' >

  <!-- Child elements -->
  desktop:FullTrustProcess?
  desktop:StartupTask?
  desktop:ToastNotificationActivation?
  desktop:SearchProtocolHandler?

</desktop:Extension>
```

### Key

`?` optional (zero or one)

## Attributes and elements

### Attributes

| Attribute | Description | Data type | Required | Default value |
|-|-|-|-|-|
| **Category** | The category of the extension. | A string value that can be one of the following values: *windows.fullTrustProcess*, *windows.startupTask*, *windows.toastNotificationActivation*, or *windows.searchProtocolHandler*. | Yes |  |
| **Executable** | The default launch executable. | An optional string with a value between 1 and 256 characters in length that must end with `.exe` and cannot contain these characters: `<`, `>`, `:`, `"`, `|`, `?`, or `*`. It specifies the default executable for the extension. If not specified, the executable defined for the app is used.  If specified, the EntryPoint property is also used. If that EntryPoint property isnt specified, the EntryPoint defined for the app is used. | No |  |
| **EntryPoint** | The activatable class ID. | An optional string with a value between 1 and 256 characters in length, representing the  task handling the extension. This is normally the fully namespace-qualified name of a Windows Runtime type. If EntryPoint is not specified, the EntryPoint defined for the app is used instead. | No |  |
| **RuntimeType** | The runtime provider. This attribute is used typically when there are mixed frameworks in an app. | An optional string with a value between 1 and 255 characters in length that cannot start or end with a period or contain these characters: `<`, `>`, `:`, `"`, `/`, `\`, `|`, `?`, or `*`. | No |  |
| **StartPage** | The web page that handles the extensibility point. | An optional string with a value between 1 and 256 characters in length that cannot contain these characters: `<`, `>`, `:`, `"`, `|`, `?`, or `*`. | No |  |
| **uap10:TrustLevel** | Specifies the trust level of the extension. | An optional string that can have one of the following values: *appContainer* or *mediumIL*. | No |  |
| **uap10:RuntimeBehavior** | Specifies the run time behavior of the extension. | An optional string that can have one of the following values: *windowsApp*, *packagedClassicApp*, or *win32App*. | No |  |
| **uap10:HostId** | Specifies the app ID of the host app for the extension. | An optional alphanumeric string with a value between 1 and 255 characters in length. Must begin with an alphabetic character. | No |  |
| **uap10:Parameters** | Contains command line parameters to pass to the extension. Only supported for desktop apps that have package identity. | An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **uap11:Id** | An identifier for the extension. | An optional string with a value between 1 and 255 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **uap11:Subsystem** | This attribute is inherited from the base extension syntax and is not applicable to the com4 extension. Other than syntactic validation, this value is ignored.  | An optional string that can have one of the following values: *console* or *windows*. | No |  |
| **uap11:SupportsMultipleInstances** | Specifies whether instances should run in different job object and process. The default value is false. | An optional boolean value. | No |  |
| **uap11:ResourceGroup** | A tag that you can use to group extension activations together for resource management purposes (for example, CPU and memory). The value you can set ResourceGroup is free-form and flexible. See [Application@ResourceGroup](element-application.md).  | An optional alphanumeric string with a value between 1 and 255 characters in length. Must begin with a letter. | No |  |
| **uap11:CurrentDirectoryPath** | Specifies the initial directory when the application process is launched.  | An optional string that cannot contain these characters: `<`, `>`, `|`, `?`, or `*`. > | No |  |
| **uap11:Parameters** | This attribute is inherited from the base extension syntax and is not applicable to the com4 extension. Other than syntactic validation, this value is ignored. | An optional string with a value between 1 and 32767 characters in length with a non-whitespace character at its beginning and end. | No |  |
| **desktop7:CompatMode** | Specifies whether the registrations in this extension are only visible to other applications via COM activation and other COM/OLE APIs (modern), or whether they should also be written to the registry in the classic format (classic). The default value is "modern". For more information, see the Remarks section. | An optional string the can have one of the following values: *classic* or *modern*. | No |  |
| **desktop7:Scope** | Specifies whether the registrations are only visible to other applications running as a user who has this package registered (user), or whether they are visible to all users and services on the machine (machine). The default value is "user". For more information, see the Remarks section. | An optional string that can have one of the following values: *machine* or *user*. | No |  |

### Child elements

| Child element | Description |
|-|-|
| [FullTrustProcess](element-desktop-fulltrustprocess.md) | Represents a desktop process that runs in full-trust. |
| [StartupTask](element-desktop-startuptasks.md) | Represents a desktop process that runs during app startup. |
| [ToastNotificationActivation](element-desktop-toastnotificationactivation.md) | Allows toast notification to be received within the app. |
| [SearchProtocolHandler](element-desktop-searchprotocolhandler.md) | Represents a desktop process handles the search protocol for the app. |

### Parent elements

| Parent element | Description |
|-|-|
| [Extensions](element-1-extensions.md) | Declares an extensibility point for the package. |

## Remarks
	
Use of the following desktop syntax semantics have capability requirements:
	
- CompatMode="classic" requires *Microsoft.classicAppCompat_8wekyb3d8bbwe*.
- Scope="machine" requires *Microsoft.classicAppCompatElevated_8wekyb3d8bbwe*.

## Requirements

| Item  | Value  |
|--|--|
| Namespace | `http://schemas.microsoft.com/appx/manifest/foundation/windows10` |
| **uap10** | `http://schemas.microsoft.com/appx/manifest/uap/windows10/10` |
