---
title: Create Bin Contents
description: After you have set up your bins, you can specify the items that you want to store in them, and set up rules that control how often bins are refilled.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 7374
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create Bin Contents

After you have set up your bins, you can set up the bin contents. In other words, you can set up the items you want to store in any given bin and set the rules that govern filling the bin with a particular item. You can do this manually on the **Bin Contents** page or automatically with the **Create Bin Content Worksheet** page.

## To create bin content manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Locations**, and then choose the related link.  
2. Select the location where you want to set up bin contents,  and then choose the **Bins** action.  
3. Select the bin where you want to set up contents, and then choose the **Contents** action.  
4. For each item that you want to store in the bin, fill in a line on the **Bin Contents** page with the appropriate information. Some of the fields are filled in already with information about the bin.  
5. First fill in the **Item No.** field, and then, if you are using directed put-away and pick, fill in the other fields such as the **Unit of Measure Code**, **Max. Qty.**, and **Min. Qty.** fields.  

Select the **Fixed** field if necessary. If the bin is to be used as the default bin for the item, select the **Default Bin** field.  

If you are using directed put-away and pick, and if you have entered the correct dimensional information on the item card about each item's units of measure, the maximum quantity that you enter on the **Bin Contents** page is verified against the physical capabilities of the bin. The minimum and maximum quantities are used when calculating bin replenishment and suggested put-aways.  

If you select the **Fixed** field, you are fixing the item to the bin, meaning that [!INCLUDE[prod_short](includes/prod_short.md)] will try to put this item in the bin if there is space for it, and it will preserve the record fixing the item to the bin even when the quantity in the bin is 0. Other items can be put into the bin, even though a particular item has been fixed to the bin.  

> [!NOTE]  
> You can set up several bin contents at the same time on the **Bin Content Creation Worksheet** page.  

## To create bin content with a worksheet

When you have created your bins, you can create the bin content that you want for each bin in the bin content creation worksheet.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bin Content Creation Worksheet**, and then choose the related link.  
2. On the worksheet header, in the **Name** field, select the worksheet of the location where you want to create bin contents.  
3. In the **Bin Code** field, select the code of the bin for which you want to define bin content.  

    If you are using directed put-away and pick in this location, the fields relating to that particular bin, such as **Bin Type**, **Warehouse Class Code**, and **Bin Ranking**, will be filled in automatically. This is information that you need to consider as you define the bin content.  
4. Select the item that you want to assign to the bin, and fill in the fields related to the bin content. If you are using directed put-away and pick, and you want to use the **Calculate Bin Replenishment** function, fill in the **Max. Qty.** and **Min. Qty.** fields.  

    To set this bin as the preferred bin for the item even if the bin quantity is **0** and all other put-away criteria equal, select the **Fixed** field.  
5. Repeat steps 3 through 4 for each item you want to assign to a bin.  
6. Choose the **Print** action to preview and print the bin content you have entered in the worksheet. Continue to revise the bin content until you are satisfied.  
7. When you are ready, choose the **Create Bin Content** action.  

In this worksheet, you can work with a number of bin content lines for a number of bins and thereby obtain a good overview of what you are putting into various bins in a given zone, aisle, or rack.  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
