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
# How to: Assign Locations to Entries
You can assign a location to an entry after you have posted it, for example, if you have forgotten to define a location for a purchase or sales order.  
  
### To assign a locations to a posted entry  
  
1.  In the **Search** box, enter **Item Reclass. Journal**, and then choose the related link.  
  
2.  In the **Item No.** field, enter the number of the item on the entry you want to assign a location to.  
  
3.  In the **New Location Code** field, enter the location you want to assign to the entry.  
  
4.  In the **Applies-to Entry** field, enter the entry number of the entry to which you want to add the location information.  
  
5.  Post the entry.  
  
 When you use a journal line to add information on an entry, two item ledger entries are created, one with a negative quantity and the location code from the **Location Code** field, and one with a positive quantity and the location code from the **New Location Code** field.  
  
> [!NOTE]  
>  You cannot use the item reclassification journal to change a location if either the old or new location uses directed put-away and pick. You must instead use the transfer order.  
  
## See Also  
 Item Ledger Entries   
 Item Reclass. Journal   
 [Count, Adjust, and Reclassify Inventory](../count-adjust-and-reclassify-inventory.md)   
 [How to: Set Up Locations](../how-to-set-up-locations.md)