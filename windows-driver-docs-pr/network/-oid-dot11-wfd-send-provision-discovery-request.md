---
title: OID\_DOT11\_WFD\_SEND\_PROVISION\_DISCOVERY\_REQUEST
author: windows-driver-content
description: When set, the OID\_DOT11\_WFD\_SEND\_PROVISION\_DISCOVERY\_REQUEST object identifier (OID) requests that the Wi-Fi Direct (WFD) device send a provision discovery request packet to a peer WFD device.
ms.assetid: 69490609-60CB-426F-8ED7-F8B35CDFCE2A
ms.author: windowsdriverdev
ms.date: 08/08/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
keywords: 
 -OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_REQUEST Network Drivers Starting with Windows Vista
---

#  OID\_DOT11\_WFD\_SEND\_PROVISION\_DISCOVERY\_REQUEST


**Important**  The [Native 802.11 Wireless LAN](https://msdn.microsoft.com/library/windows/hardware/ff560690) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](https://msdn.microsoft.com/library/windows/hardware/dn897672).

 

When set, the OID\_DOT11\_WFD\_SEND\_PROVISION\_DISCOVERY\_REQUEST object identifier (OID) requests that the Wi-Fi Direct (WFD) device send a provision discovery request packet to a peer WFD device.

The data type for OID\_DOT11\_WFD\_SEND\_PROVISION\_DISCOVERY\_REQUEST is the [**DOT11\_SEND\_PROVISION\_DISCOVERY\_REQUEST\_PARAMETERS**](https://msdn.microsoft.com/library/windows/hardware/hh406556) structure.

This OID is sent to the miniport as an **NdisRequestSetInformation** OID request type.

After receiving this OID, the miniport must create and populate all the required Peer-to-Peer (P2P) attributes in the P2P Information Element (IE) before it sends the provision discovery request packet.

After creating the packet for transmission, the miniport must complete the OID with status of **NDIS\_STATUS\_INDICATION\_REQUIRED**. The completion of the attempt to send the provision discovery request attempt must be indicated to the system with a [**NDIS\_STATUS\_DOT11\_WFD\_PROVISION\_DISCOVERY\_REQUEST\_SEND\_COMPLETE**](https://msdn.microsoft.com/library/windows/hardware/hh439783) indication. The miniport driver must send the **NDIS\_STATUS\_DOT11\_WFD\_PROVISION\_DISCOVERY\_REQUEST\_SEND\_COMPLETE** indication once it has stopped the attempt to send the provision discovery request. This must occur in either case of success or failure.

Miniport drivers should periodically attempt sending the Provision Discovery Request frame at intervals no longer than 50ms because a remote device may not be constantly available on its listen channel (or, operating channel in case of GO).

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version</p></td>
<td><p>Versions: Supported in Windows 8.</p></td>
</tr>
<tr class="even">
<td><p>Header</p></td>
<td>Windot11.h (include Windot11.h)</td>
</tr>
</tbody>
</table>

## See also


[**DOT11\_SEND\_PROVISION\_DISCOVERY\_REQUEST\_PARAMETERS**](https://msdn.microsoft.com/library/windows/hardware/hh406556)

[**NDIS\_STATUS\_DOT11\_WFD\_PROVISION\_DISCOVERY\_REQUEST\_SEND\_COMPLETE**](https://msdn.microsoft.com/library/windows/hardware/hh439783)

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bnetvista\netvista%5D:%20%20OID_DOT11_WFD_SEND_PROVISION_DISCOVERY_REQUEST%20%20RELEASE:%20%288/8/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


