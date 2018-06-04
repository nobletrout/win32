---
title: IVMDVDDrive HostDriveLetter property
description: The HostDriveLetter property contains the letter of the host drive captured by this DVD drive.
ms.assetid: 89982afd-7dbc-434e-9bb9-cc9a77d35cd8
keywords:
- HostDriveLetter property Virtual Server
- HostDriveLetter property Virtual Server , IVMDVDDrive interface
- IVMDVDDrive interface Virtual Server , HostDriveLetter property
- HostDriveLetter property Virtual Server , VMDVDDrive interface
- VMDVDDrive interface Virtual Server , HostDriveLetter property
topic_type:
- apiref
api_name:
- IVMDVDDrive.HostDriveLetter
- IVMDVDDrive.get_HostDriveLetter
- VMDVDDrive.HostDriveLetter
api_location:
- VsComInterfaces.h
api_type:
- COM
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# IVMDVDDrive::HostDriveLetter property

The **HostDriveLetter** property contains the letter of the host drive captured by this DVD drive.

This property is read-only.

## Syntax


```C++
HRESULT get_HostDriveLetter(
  [out] BSTR *driveLetter
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>VMDVDDrive.HostDriveLetter( _
  ByRef driveLetter _
)</code></pre></td>
</tr>
</tbody>
</table>



## Property value

The letter of the host drive captured by this DVD drive.

This property value is read-only.

## Error codes



| Name                                                                                                 | Meaning                                                              |
|------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| <dl> <dt>S\_OK</dt> </dl>                     | The operation was successful.<br/>                             |
| <dl> <dt>E\_POINTER</dt> </dl>                | The parameter is **NULL**.<br/>                                |
| <dl> <dt>VM\_E\_VM\_UNKNOWN</dt> </dl>        | The virtual machine could not be found.<br/>                   |
| <dl> <dt>VM\_E\_MEDIA\_WRONG\_TYPE</dt> </dl> | The media captured by this DVD drive is not a host drive.<br/> |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl>        | An unexpected error occurred.<br/>                             |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server 2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMDVDDrive**](ivmdvddrive.md)
</dt> </dl>

 

 




