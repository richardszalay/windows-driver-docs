---
title: OID_WDI_TASK_SEND_RESPONSE_ACTION_FRAME
author: windows-driver-content
description: OID_WDI_TASK_SEND_RESPONSE_ACTION_FRAME requests that the IHV component sends Response Action Frames.
ms.assetid: DA2FF006-BA81-48B9-8AAD-694818E78AEF
ms.author: windowsdriverdev 
ms.date: 07/18/2017 
ms.topic: article 
ms.prod: windows-hardware 
ms.technology: windows-devices 
keywords:
 - OID_WDI_TASK_SEND_RESPONSE_ACTION_FRAME Network Drivers Starting with Windows Vista
---

# OID\_WDI\_TASK\_SEND\_RESPONSE\_ACTION\_FRAME


OID\_WDI\_TASK\_SEND\_RESPONSE\_ACTION\_FRAME requests that the IHV component sends Response Action Frames.

| Object | Abort capable                                           | Default priority (host driver policy) | Normal execution time (seconds) |
|--------|---------------------------------------------------------|---------------------------------------|---------------------------------|
| Port   | Yes. The port must be in a clean state after the abort. | 3                                     | 5                               |

 

This task is time sensitive and must be serviced within 100 milliseconds of receiving this packet.

While the maximum timeout has not expired, the port shall retry sending the frame to the remote device on the specified channel.

The task is complete either when local device receives an acknowledgment from the remote device for the action frame that was sent, the timeout expires, or the host aborts the operation. The device may indicate task completion after the same-channel dwell time has expired.

The host may decide to abort this operation and continue/retry the action frame exchange, so it is important that the device is able to abort this operation quickly.

## Task parameters


| TLV                                                                                                               | Multiple TLV instances allowed | Optional | Description                                      |
|-------------------------------------------------------------------------------------------------------------------|--------------------------------|----------|--------------------------------------------------|
| [**WDI\_TLV\_SEND\_ACTION\_FRAME\_RESPONSE\_PARAMETERS**](https://msdn.microsoft.com/library/windows/hardware/dn898054) |                                |          | Parameters for sending an Action Frame Response. |
| [**WDI\_TLV\_ACTION\_FRAME\_BODY**](https://msdn.microsoft.com/library/windows/hardware/dn926118)                                           |                                |          | The Action Frame body.                           |

 

## Task completion indication


[NDIS\_STATUS\_WDI\_INDICATION\_SEND\_RESPONSE\_ACTION\_FRAME\_COMPLETE](ndis-status-wdi-indication-send-response-action-frame-complete.md)
Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum supported client</p></td>
<td><p>Windows 10</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2016</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Dot11wdi.h</td>
</tr>
</tbody>
</table>

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bnetvista\netvista%5D:%20OID_WDI_TASK_SEND_RESPONSE_ACTION_FRAME%20%20RELEASE:%20%286/30/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


