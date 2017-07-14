---
title: NET\_BUFFER\_DATA\_LENGTH macro
description: NET\_BUFFER\_DATA\_LENGTH is a macro that NDIS drivers use to get the amount of used data space in a NET\_BUFFER structure.
MS-HAID:
- 'ndis\_netbuf\_macros\_ref\_9813f4e3-4674-4dbc-adb0-79fd30e552ca.xml'
- 'netvista.net\_buffer\_data\_length'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7fa9f67e-7b81-4bab-914b-cd02028fb21e
keywords: ["NET_BUFFER_DATA_LENGTH macro Network Drivers Starting with Windows Vista"]
topic_type:
- apiref
api_name:
- NET_BUFFER_DATA_LENGTH
api_location:
- Ndis.h
api_type:
- HeaderDef
---

# NET\_BUFFER\_DATA\_LENGTH macro


NET\_BUFFER\_DATA\_LENGTH is a macro that NDIS drivers use to get the amount of *used data space* in a [**NET\_BUFFER**](https://msdn.microsoft.com/library/windows/hardware/ff568376) structure.

Syntax
------

```ManagedCPlusPlus
ULONG NET_BUFFER_DATA_LENGTH(
   PNET_BUFFER _NB
);
```

Parameters
----------

*\_NB*   
A pointer to a NET\_BUFFER structure.

Return value
------------

NET\_BUFFER\_DATA\_LENGTH returns the amount of *used data space* in a NET\_BUFFER structure.

Remarks
-------

NET\_BUFFER\_DATA\_LENGTH gets the return value from the **DataLength** member of the [**NET\_BUFFER**](https://msdn.microsoft.com/library/windows/hardware/ff568376) structure.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Target platform</p></td>
<td>[Universal](http://go.microsoft.com/fwlink/p/?linkid=531356)</td>
</tr>
<tr class="even">
<td><p>Version</p></td>
<td><p>Supported in NDIS 6.0 and later.</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Ndis.h (include Ndis.h)</td>
</tr>
</tbody>
</table>

## See also


[**NET\_BUFFER**](https://msdn.microsoft.com/library/windows/hardware/ff568376)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bnetvista\netvista%5D:%20NET_BUFFER_DATA_LENGTH%20macro%20%20RELEASE:%20%287/10/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




