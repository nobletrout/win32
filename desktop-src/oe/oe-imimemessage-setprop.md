---
title: IMimeMessage SetProp method
description: Sets a property value for the root header of the message.
ms.assetid: b3f64f09-969d-4946-9517-c1bf8f05abf4
keywords:
- SetProp method Windows Mail (formerly Outlook Express)
- SetProp method Windows Mail (formerly Outlook Express) , IMimeMessage interface
- IMimeMessage interface Windows Mail (formerly Outlook Express) , SetProp method
topic_type:
- apiref
api_name:
- IMimeMessage.SetProp
api_location:
- Inetcomm.dll
api_type:
- COM
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# IMimeMessage::SetProp method

Sets a property value for the root header of the message.

## Syntax


```C++
HRESULT SetProp(
  [in] LPCSTR         pszName,
  [in] DWORD          dwFlags,
  [in] LPCPROPVARIANT pValue
);
```



## Parameters

<dl> <dt>

*pszName* \[in\]
</dt> <dd>

Type: **LPCSTR**

Specifies the property name or ID.

</dd> <dt>

*dwFlags* \[in\]
</dt> <dd>

Type: **DWORD**

Specifies a bitmask that affects how the property value is stored.



| Value                                                                                                                                                                  | Meaning                                                                                                                                                                                 |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="PDF_ENCODED"></span><span id="pdf_encoded"></span><dl> <dt>**PDF\_ENCODED**</dt> </dl>                | The value of the property is encoded in an Internet character set and possibly [RFC 1522](http://www.ietf.org/rfc/rfc1522.txt). Used in both getting and setting a property.<br/> |
| <span id="PDF_NAMEINDATA"></span><span id="pdf_nameindata"></span><dl> <dt>**PDF\_NAMEINDATA**</dt> </dl>       | The name of the property must be prefixed to the property value.<br/>                                                                                                             |
| <span id="PDF_HEADERFORMAT"></span><span id="pdf_headerformat"></span><dl> <dt>**PDF\_HEADERFORMAT**</dt> </dl> | The value should be formatted according to [RFC 822](http://www.ietf.org/rfc/rfc822.txt) (character set encoded, wrapped, etc.).<br/>                                             |
| <span id="PDF_NOCOMMENTS"></span><span id="pdf_nocomments"></span><dl> <dt>**PDF\_NOCOMMENTS**</dt> </dl>       | Any comments embedded in the value must be stripped out.<br/>                                                                                                                     |
| <span id="PDF_SAVENOENCODE"></span><span id="pdf_savenoencode"></span><dl> <dt>**PDF\_SAVENOENCODE**</dt> </dl> | When the header is saved, this value must not be re-encoded.<br/>                                                                                                                 |
| <span id="PDF_VECTOR"></span><span id="pdf_vector"></span><dl> <dt>**PDF\_VECTOR**</dt> </dl>                   | If the property appears multiple times, the values are concatenated together (separated by carriage return line feeds).<br/>                                                      |



 

</dd> <dt>

*pValue* \[in\]
</dt> <dd>

Type: **LPCPROPVARIANT**

Specifies the value to set for the property.

</dd> </dl>

## Return value

Type: **HRESULT**

Returns one of the following values.



| Return code                                                                                                   | Description                                                                                                                                                                                                                                                                              |
|---------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                          | Indicates success.<br/>                                                                                                                                                                                                                                                            |
| <dl> <dt>**E\_FAIL**</dt> </dl>                        | Indicates that an unknown error has occurred. <br/>                                                                                                                                                                                                                                |
| <dl> <dt>**E\_OUTOFMEMORY**</dt> </dl>                 | Indicates that an attempt to allocate memory failed.<br/>                                                                                                                                                                                                                          |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>                  | Indicates that *pszName* or *pValue* is **NULL**. Also may indicate that *pValue*-&gt;[vt](https://msdn.microsoft.com/library/windows/desktop/aa380072) specifies a [VARTYPE](https://msdn.microsoft.com/library/windows/desktop/ms221127) that is not supported or that its corresponding member in the PROPVARIANT structure is invalid, such as **NULL** pointer. <br/> |
| <dl> <dt>**MIME\_E\_READ\_ONLY**</dt> </dl>            | Indicates that the property is read-only, that is, the property has the MPF\_READONLY flag set in the property schema. <br/>                                                                                                                                                       |
| <dl> <dt>**MIME\_E\_INVALID\_HEADER\_NAME**</dt> </dl> | Indicates that *pszName* is a new property that contains invalid characters.<br/>                                                                                                                                                                                                  |
| <dl> <dt>**MIME\_E\_NOT\_FOUND**</dt> </dl>            | Indicates that *pszName* specifies a property ID that does not exist in the property schema.<br/>                                                                                                                                                                                  |



 

## Remarks

A property ID can also be passed into this method through the *pszName* parameter using the PIDTOSTR macro.

MIMEOLE supports these variant types: VT\_LPSTR, VT\_LPWSTR, VT\_FILETIME, VT\_UI4, VT\_I4, and VT\_STREAM.

This method is equivalent to:

pMessage-&gt;[**BindToObject**](oe-imimemessagetree-bindtoobject.md)(HBODY\_ROOT, IID\_IMimePropertySet, (LPVOID \*)&pPropertySet);

pPropertySet-&gt;[**SetProp**](oe-imimepropertyset-setprop.md)(*pszName*, *dwFlags*, *pValue*);

## Requirements



|                                     |                                                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                                                    |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                           |
| Product<br/>                  | Outlook Express 6.0<br/>                                                                                 |
| Header<br/>                   | <dl> <dt>Mimeole.h</dt> </dl>                           |
| IDL<br/>                      | <dl> <dt>Mimeole.idl</dt> </dl>                         |
| DLL<br/>                      | <dl> <dt>Inetcomm.dll (version 6.0 or later)</dt> </dl> |



 

 




