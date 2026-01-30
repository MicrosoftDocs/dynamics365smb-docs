---
title: Design details - item tracking availability
description: The Item Tracking Lines and Item Tracking Summary pages provide dynamic availability information for serial or lot numbers, increasing transparency for users.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords:
ms.date: 01/30/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Design details: item tracking availability

The **Item Tracking Lines** and **Item Tracking Summary** pages provide dynamic availability information for serial or lot numbers. The information increases transparency on outbound documents. For example, on sales orders it shows which serial numbers or how many units of a lot number are already assigned on other open documents. This information helps reduce double allocation and gives confidence that you can fulfill the item tracking numbers and dates that they're promised for unposted sales orders. Learn more at [Design Details: Item Tracking Lines Page](design-details-item-tracking-lines-window.md).  

 When you open the **Item Tracking Lines** page, availability data is retrieved from the **Item Ledger Entry** table and the **Reservation Entry** table, with no date filter. When you choose the **Serial No.** field or the **Lot No.** field, the **Item Tracking Summary** page opens and shows a summary of the item tracking information in the **Reservation Entry** table. The summary contains the following information about each serial or lot number on the item tracking line:  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Total Quantity**|The total quantity of the serial or lot number that is currently in inventory.|  
|**Total Requested Quantity**|The total quantity of the serial or lot number that is currently reserved in all documents.|  
|**Current Pending Quantity**|The quantity that is entered in the current instance of the **Item Tracking Lines** page but isn't committed to the database.|  
|**Total Available Quantity**|The quantity of the serial or lot number that's available to request.<br /><br /> This quantity is calculated from other fields on the page as follows:<br /><br /> total quantity – (total requested quantity + current pending quantity).|  

> [!NOTE]  
>  You can also see the information in the preceding table by using the **Select Entries** function on the **Item Tracking Lines** page.  

 To preserve database performance, availability data is only retrieved once from the database when you open the **Item Tracking Lines** page and when you use the **Refresh Availability** function on the page.  

## Calculation Formula  
 As described in the preceding table, the availability of a given serial or lot number is calculated as follows.  

 total available quantity = quantity in inventory – (all demands + quantity not yet committed to the database)  

> [!IMPORTANT]  
>  This formula implies that the serial or lot number availability calculation considers only inventory and ignores projected receipts. Supply that isn't posted to inventory doesn't affect item tracking availability, as opposed to regular item availability that includes projected receipts.  

## Related information
  
[Design Details: Item Tracking](design-details-item-tracking.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
