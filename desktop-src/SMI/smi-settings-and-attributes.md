---
title: SMI Attributes
description: Lists the values and descriptions of various attributes that apply to settings.
ms.assetid: 7aed83af-c18d-4ea9-a903-811e90beb1b3
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# SMI Attributes

The following table lists the values and descriptions of various attributes that apply to settings.



| Attribute     | Value(s)                                                                                                                                                                                                                                                                                                                                                                                                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| type          | xsd:int<br/> xsd:byte<br/> xsd:short<br/> xsd:boolean<br/> xsd:long<br/> xsd:unsignedByte<br/> xsd:unsignedShort<br/> xsd:unsignedInt<br/> xsd:unsignedLong<br/> xsd:integer<br/> xsd:positiveInteger<br/> xsd:nonNegativeInteger<br/> xsd:negativeInteger<br/> xsd:nonPositiveInteger<br/> xsd:string<br/> xsd:hexBinary<br/> | Indicates the setting type.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| displayName   | string                                                                                                                                                                                                                                                                                                                                                                                                                         | Represents friendly name of a setting.                                                                                                                                                                                                                                                                                                                                                                                                                  |
| description   | string                                                                                                                                                                                                                                                                                                                                                                                                                         | Indicates the description of a setting.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| default       | Depends on the setting                                                                                                                                                                                                                                                                                                                                                                                                         | Indicates the default value that is assigned to a setting on install.                                                                                                                                                                                                                                                                                                                                                                                   |
| scope         | "perUser"                                                                                                                                                                                                                                                                                                                                                                                                                      | Indicates that the setting is unique for each user on the system. If a user changes a perUser setting, then no other user on the system will notice the change. Settings that reside in **HKEY\_CURRENT\_USER** are generally "perUser" settings. The setting is installed in user space and there is one for each user.                                                                                                                                |
| scope         | "allUsers"                                                                                                                                                                                                                                                                                                                                                                                                                     | Indicates that setting is shared globally by all users of the application. If one user changes a shared setting, then all users are affected, as they all see the change. Settings that reside in **HKEY\_LOCAL\_MACHINE** are usually "allUsers" settings. The setting is installed in a shared space and there is only one value shared between all users.                                                                                            |
| subscope      | See below.                                                                                                                                                                                                                                                                                                                                                                                                                     | Some settings have a strong binding to an instance of the operating system (or the computer in many cases). IP address is a classic example. Other settings such as user preference are generally independent of the operating system (computer). This attribute indicates if a setting has a strong binding to this instance of the operating system or not.                                                                                           |
| subscope      | "machineSpecific"                                                                                                                                                                                                                                                                                                                                                                                                              | Indicates that this setting strongly binds to the instance of the operating system (and the computer in many cases). If this setting is roamed to a different computer it will not have meaning.                                                                                                                                                                                                                                                        |
| subscope      | "machineIndependent"                                                                                                                                                                                                                                                                                                                                                                                                           | Indicates that the setting has no strong binding to the computer or this operating system instance.                                                                                                                                                                                                                                                                                                                                                     |
| visible       | True<br/> False<br/>                                                                                                                                                                                                                                                                                                                                                                                               | Indicates if a setting is visible by a management tool such as image manager. This attribute can also used to indicate if a setting can be overridden by the use of an unattend (answer) file.                                                                                                                                                                                                                                                          |
| accessControl | A security descriptor definition language ([SDDL](https://msdn.microsoft.com/library/windows/desktop/aa379567)) value.                                                                                                                                                                                                                                                                                                                    | Describes the access control of a setting.                                                                                                                                                                                                                                                                                                                                                                                                              |
| changeImpact  | See below.                                                                                                                                                                                                                                                                                                                                                                                                                     | Indicates the type of system response that should be invoked when the value of a setting is changed.                                                                                                                                                                                                                                                                                                                                                    |
| changeImpact  | "systemRestart"                                                                                                                                                                                                                                                                                                                                                                                                                | Restart the system when this setting value changes.                                                                                                                                                                                                                                                                                                                                                                                                     |
| changeImpact  | "processRestart"                                                                                                                                                                                                                                                                                                                                                                                                               | Restart the process that uses this setting when this setting value changes.                                                                                                                                                                                                                                                                                                                                                                             |
| changeImpact  | "notSpecified"                                                                                                                                                                                                                                                                                                                                                                                                                 | The impact of this setting has not been defined. This is the default value for this attribute.                                                                                                                                                                                                                                                                                                                                                          |
| changeImpact  | "noImpact"                                                                                                                                                                                                                                                                                                                                                                                                                     | There is no impact when this setting value changes.                                                                                                                                                                                                                                                                                                                                                                                                     |
| readOnly      | True<br/> False<br/>                                                                                                                                                                                                                                                                                                                                                                                               | **True** indicates that the setting is displayed to users, but cannot be changed by them. **False** indicates that the setting is displayed to users and may be modified by users with appropriate permission.                                                                                                                                                                                                                                          |
| xsd:nillable  | True<br/> False<br/>                                                                                                                                                                                                                                                                                                                                                                                               | **True** indicates that the setting may exist even without a value. **False** indicates that the setting cannot exist without a value.                                                                                                                                                                                                                                                                                                                  |
| handler       | Format: "type(location)"                                                                                                                                                                                                                                                                                                                                                                                                       | Indicates where the setting is stored.                                                                                                                                                                                                                                                                                                                                                                                                                  |
| handler       | "regKey('**HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet**')"                                                                                                                                                                                                                                                                                                                                                                | Indicates that the setting is in location **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet**<br/> in the registry.                                                                                                                                                                                                                                                                                                                               |
| handler       | "ini('$(runtime.system32)\\mapisvc.inf')"                                                                                                                                                                                                                                                                                                                                                                                      | Indicates that the setting is located in $(runtime.system32)\\mapisvc.inf.                                                                                                                                                                                                                                                                                                                                                                              |
| legacyName    | String. For example:"Content Type"                                                                                                                                                                                                                                                                                                                                                                                             | If present, the value of this attribute represents the name in the legacy store (registry or .ini file).                                                                                                                                                                                                                                                                                                                                                |
| legacyType    | "REG\_DWORD"<br/> "REG\_DWORD\_LITTLE\_ENDIAN"<br/> "REG\_DWORD\_BIG\_ENDIAN"<br/> "REG\_EXPAND\_SZ"<br/> "REG\_MULTI\_SZ"<br/> "REG\_QWORD"<br/> "REG\_QWORD\_LITTLE\_ENDIAN"<br/> "REG\_SZ"<br/>                                                                                                                                                                             | Indicate the legacy type of a setting. For more information about registry value types, see [Registry Value Types](https://msdn.microsoft.com/library/windows/desktop/ms724884).                                                                                                                                                                                                                                                                                                          |
| migrate       | "no"<br/> "yes" <br/> "yesCreateOnly"<br/>                                                                                                                                                                                                                                                                                                                                                                   | Indicates if a setting can be migrated. A value "no" indicates that the element or object should not be migrated. A value "yes" indicates that the element or object can be migrated using default conflict resolution rules. The rules are that the source has priority if there is a conflict in the value of the setting. A value of "yesCreateOnly" indicates that the setting should migrate only if it does not already exist on the destination. |
| xsd:minOccurs | Common values: "0"<br/> "1"<br/>                                                                                                                                                                                                                                                                                                                                                                                   | Indicates the minimum number of instances of this setting. A value of "0" indicates that the setting is optional. A value of "1" indicates that the setting is mandatory.                                                                                                                                                                                                                                                                               |
| xsd:maxOccurs | Common values: "1"<br/> "unbounded"<br/>                                                                                                                                                                                                                                                                                                                                                                           | Indicates the maximum number of instances of this setting. A value of "1" indicates that at most, one instance of this setting may exist. It is the value on scalar and complex settings. A value of "unbounded" denotes that any number of instances of this setting may exist. It is the value on list settings.                                                                                                                                      |
| dataOnly      | **True**<br/> **False**<br/>                                                                                                                                                                                                                                                                                                                                                                                       | **True** indicates that this is a data only setting, which means that it does not require code to be run to activate its value. **False** indicates that this setting has a matched API or executable that must be run for its value to be fully-enabled. Unattend settings commonly have the attribute value **False**.                                                                                                                                |
| passes        | "windowsPE"<br/> "offlineServicing"<br/>                                                                                                                                                                                                                                                                                                                                                                           | The value indicates the pass during which the setting will be applied.                                                                                                                                                                                                                                                                                                                                                                                  |



 

 

 




