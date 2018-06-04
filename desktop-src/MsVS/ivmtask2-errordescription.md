---
title: IVMTask2 ErrorDescription property
description: The error description for this task.
ms.assetid: 7b1fca63-a417-4ff2-93d3-afebe77f18c4
keywords:
- ErrorDescription property Virtual Server
- ErrorDescription property Virtual Server , IVMTask2 interface
- IVMTask2 interface Virtual Server , ErrorDescription property
- ErrorDescription property Virtual Server , VMTask2 interface
- VMTask2 interface Virtual Server , ErrorDescription property
topic_type:
- apiref
api_name:
- IVMTask2.ErrorDescription
- IVMTask2.get_ErrorDescription
- VMTask2.ErrorDescription
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

# IVMTask2::ErrorDescription property

The error description for this task.

This property is read-only.

## Syntax


```C++
HRESULT get_ErrorDescription(
  [out] BSTR *outErrorDesc
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
<td><pre><code>VMTask2.ErrorDescription( _
  ByRef outErrorDesc _
)</code></pre></td>
</tr>
</tbody>
</table>



## Property value

The error description for this task.

This property value is read-only.

## Error codes

For information on other return values specific to Virtual Server, see [**HRESULT Codes Specific to the Virtual Server**](hresult-codes-specific-to-the-virtual-server.md).



| Name                                                                                                    | Meaning                                                                                                        |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| <dl> <dt>S\_OK</dt> </dl>                        | The operation was successful.<br/>                                                                       |
| <dl> <dt>E\_POINTER</dt> </dl>                   | The *outError* parameter is **NULL**.<br/>                                                               |
| <dl> <dt>VM\_E\_VM\_UNKNOWN</dt> </dl>           | The virtual machine could not be found.<br/>                                                             |
| <dl> <dt>VM\_E\_ADDITIONS\_NOT\_AVAIL</dt> </dl> | Additions are not installed in this virtual machine, or the virtual machine has never been started.<br/> |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl>           | An unexpected error has occurred.<br/>                                                                   |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMTask2**](ivmtask2.md)
</dt> <dt>

**VMTask2**
</dt> </dl>

 

 




