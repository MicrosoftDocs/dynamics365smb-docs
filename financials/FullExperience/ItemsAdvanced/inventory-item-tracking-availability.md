---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Item Tracking Availability
When you work with lot or serial numbers, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] calculates availability information for lot and serial numbers and shows it in the various item tracking windows. This lets you see how much of a lot or serial number is currently being used on other documents. This reduces errors and uncertainty caused by double allocations.  
  
 In the **Item Tracking Lines** window, a warning icon is shown in the **Availability, Lot No.** or **Availability, Serial No.** fields if some or all of the quantity you have selected is already being used in other documents or if the lot or serial number is not available.  
  
 In the **Lot No./Serial No.-List** window, the **Lot No./Serial No.-Availability** window, and the **Item Tracking – Select Entries** window, information is displayed about how much quantity of an item is being used. This includes the following information.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Total Quantity**|The total number of item currently in inventory.|  
|**Total Requested Quantity**|The total number of items that are requested that will be used in this and other documents.|  
|**Current Pending Quantity**|The number of items that are requested that will be used on the current document but that is not yet committed to the database.|  
|**Current Requested Quantity**|The number of items that are requested that will be used on the current document.|  
|**Total Available Quantity**|The total number of items in inventory, minus the quantity of the item that are requested on this and other documents (total requested quantity), and minus the quantity that is requested but not yet committed on this document (current pending quantity).|  
  
 As a performance measure, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] does not update the availability information during the time that you have the window open, even if changes occur in inventory or on other documents during that time. If you work in the **Item Tracking Lines** window for a long time or if there is a lot of activity with the item that you are working with, you can update the availability information by choosing **Refresh Availability**.  
  
 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] automatically checks the availability of the item when you close the window to confirm that there are no availability problems.  
  
## See Also  
 [How to: Select from Existing Serial Numbers and Lot Numbers](../how-to-select-from-existing-serial-numbers-and-lot-numbers.md)