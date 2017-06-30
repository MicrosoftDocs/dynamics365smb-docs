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
# How to: Set Up Bin Contents
After you have set up your bins, you can set up the bin contents. In other words, you can set up the items you want to store in any given bin and set the rules that govern filling the bin with a particular item.  
  
### To set up bin contents  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Select the location where you want to set up bin contents. On the **Navigate** tab, in the **Location** group, choose **Bins**.  
  
3.  Select the bin where you want to set up contents. On the **Navigate** tab, in the **Bin** group, choose **Contents**.  
  
4.  For each item that you want to store in the bin, fill in a line in the **Bin Contents** window with the appropriate information. Some of the fields are filled in already with information about the bin.  
  
5.  First fill in the **Item No.** field, and then, if you are using directed put-away and pick, fill in the other fields such as the **Unit of Measure Code**, **Max. Qty.**, and **Min. Qty.** fields. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  
  
     Select the **Fixed** field if necessary. If the bin is to be used as the default bin for the item, select the **Default Bin** field.  
  
 If you are using directed put-away and pick, and if you have entered the correct dimensional information on the item card about each item’s units of measure, the maximum quantity that you enter in the **Bin Contents** window is verified against the physical capabilities of the bin. The minimum and maximum quantities are used when calculating bin replenishment and suggested put-aways.  
  
 If you select the **Fixed** field, you are fixing the item to the bin, meaning that [!INCLUDE[d365fin](includes/d365fin_md.md)] will try to put this item in the bin if there is space for it, and it will preserve the record fixing the item to the bin even when the quantity in the bin is 0. Other items can be put into the bin, even though a particular item has been fixed to the bin.  
  
> [!NOTE]  
>  You can set up several bin contents at the same time in the **Bin Content Creation Worksheet** window.  
  
## See Also  
 [How to: Set Up Locations to Use Bins](../how-to-set-up-locations-to-use-bins.md)   
 [How to: Create Bins in the Bin Creation Worksheet](../how-to-create-bins-in-the-bin-creation-worksheet.md)   
 [How to: Create Bin Content in Worksheets](../how-to-create-bin-content-in-worksheets.md)