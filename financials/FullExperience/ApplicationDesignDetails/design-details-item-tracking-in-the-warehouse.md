---
title: "Design Details: Item Tracking Availability"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "item tracking, availability"
ms.assetid: 34ed4603-883d-4e69-85d4-c2372091c4cd
caps.latest.revision: 7
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Design Details: Item Tracking Availability
The **Item Tracking Lines** and **Item Tracking Summary** windows provide dynamic availability information for serial or lot numbers. The purpose of this is to increase transparency for users on outbound documents, such as sales orders, by showing them which serial numbers or how many units of a lot number are currently assigned on other open documents. This reduces uncertainty that is caused by double allocation and instills confidence in order processors that the item tracking numbers and dates that they are promising on unposted sales orders can be fulfilled. For more information, see [Design Details: Item Tracking Lines Window](../ApplicationDesign/design-details-item-tracking-lines-window.md).  
  
 When you open the **Item Tracking Lines** window, availability data is retrieved from the **Item Ledger Entry** table and the **Reservation Entry** table, with no date filter. When you choose the **Serial No.** field or the **Lot No.** field, the **Item Tracking Summary** window opens and shows a summary of the item tracking information in the **Reservation Entry** table. The summary contains the following information about each serial or lot number on the item tracking line:  
  
|[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|---------------------------------|---------------------------------------|  
|**Total Quantity**|The total quantity of the serial or lot number that is currently in inventory.|  
|**Total Requested Quantity**|The total quantity of the serial or lot number that is currently requested in all documents.|  
|**Current Pending Quantity**|The quantity that is entered in the current instance of the **Item Tracking Lines** window but is not yet committed to the database.|  
|**Total Available Quantity**|The quantity of the serial or lot number that is available for the user to request.<br /><br /> This quantity is calculated from other fields in the window as follows:<br /><br /> total quantity – \(total requested quantity \+ current pending quantity\).|  
  
> [!NOTE]  
>  You can also see the information in the preceding table by using the **Select Entries** function in the **Item Tracking Lines** window.  
  
 To preserve database performance, availability data is only retrieved once from the database when you open the **Item Tracking Lines** window and use the **Refresh Availability** function in the window.  
  
## Calculation Formula  
 As described in the preceding table, the availability of a given serial or lot number is calculated as follows.  
  
 total available quantity \= quantity in inventory – \(all demands \+ quantity not yet committed to the database\)  
  
> [!IMPORTANT]  
>  This formula implies that the serial or lot number availability calculation considers only inventory and ignores projected receipts. Accordingly, supply that is not yet posted to inventory does not affect item tracking availability, as opposed to regular item availability where projected receipts are included.  
  
## See Also  
 [Design Details: Item Tracking](../ApplicationDesign/design-details-item-tracking.md)