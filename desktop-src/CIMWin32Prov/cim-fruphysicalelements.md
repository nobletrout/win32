---
Description: The CIM\_FRUPhysicalElements class represents the physical elements that make up a field replaceable unit (FRU).
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: ecdb19a8-5169-4370-8d2d-a21a0021ea5b
ms.prod: windows-server-dev
ms.technology:
- cimwin32
- windows-management-instrumentation
ms.tgt_platform: multiple
title: CIM\_FRUPhysicalElements class
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# CIM\_FRUPhysicalElements class

The **CIM\_FRUPhysicalElements** class represents the physical elements that make up a field replaceable unit (FRU).

> \[!Important\]  
> The DMTF (Distributed Management Task Force) CIM (Common Information Model) classes are the parent classes upon which WMI classes are built. WMI currently supports only the [CIM 2.x version schemas](Http://Go.Microsoft.Com/FWLink/p/?LinkID=309367).

 

The following syntax is simplified from Managed Object Format (MOF) code and includes all inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[Abstract, UUID("{977E36CA-DB2A-11d2-85FC-0000F8102E5F}"), Aggregation, Association, AMENDMENT]
class CIM_FRUPhysicalElements
{
  CIM_PhysicalElement REF Component;
  CIM_FRU             REF FRU;
};
```

## Members

The **CIM\_FRUPhysicalElements** class has these types of members:

-   [Properties](#properties)

### Properties

The **CIM\_FRUPhysicalElements** class has these properties.

<dl> <dt>

**Component**
</dt> <dd> <dl> <dt>

Data type: **CIM\_PhysicalElement**
</dt> <dt>

Access type: Read-only
</dt> </dl>

Reference to a physical element that is a part of the FRU.

</dd> <dt>

**FRU**
</dt> <dd> <dl> <dt>

Data type: **CIM\_FRU**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Aggregate**](https://msdn.microsoft.com/library/aa393650), [**Max**](https://msdn.microsoft.com/library/aa393650) (1)
</dt> </dl>

Reference to the FRU.

</dd> </dl>

## Remarks

WMI does not implement this class.

This documentation is derived from the CIM class descriptions published by the DMTF. Microsoft may have made changes to correct minor errors, conform to Microsoft SDK documentation standards, or provide more information.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



 

 



