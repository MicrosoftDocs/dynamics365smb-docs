---
title: Create bin contents
description: After you have set up your bins, you can specify the items that you want to store in them, and set up rules that control how often bins are refilled.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 7374,
ms.date: 10/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Create bin contents

After you set up your bins, you can set up bin contents. In other words, you can set up the items you want to store in any given bin and set the rules that govern how you fill the bin with a particular item. You can do this manually on the **Bin Content** page or automatically with the **Bin Content Creation Worksheet** page.

## To create bin content manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Locations**, and then choose the related link.  
2. Select the location where you want to set up bin contents,  and then choose the **Bins** action.  
3. Select the bin where you want to set up contents, and then choose the **Contents** action.  
4. For each item that you want to store in the bin, fill in a line on the **Bin Contents** page with the appropriate information. Some of the fields are filled in already with information about the bin.  
5. Fill in the **Item No.** field, and then, if you use directed put-away and pick, fill in the other fields such as the **Unit of Measure Code**, **Max. Qty.**, and **Min. Qty.** fields.  

Select the **Fixed** field if necessary. If the bin is to be used as the default bin for the item, select the **Default** field.  

If you use directed put-away and pick, and you have entered the relevant cubage or weight information for each item's units of measure and specified the bin's **Maximum Cubage** or **Maximum Weight**, the maximum quantity that you enter on the **Bin Content** page is checked against those limits. [!INCLUDE[prod_short](includes/prod_short.md)] uses the minimum and maximum quantities to calculate bin replenishment and suggest put-aways.  

When you select the **Fixed** checkbox, you fix the item to the bin, meaning that [!INCLUDE[prod_short](includes/prod_short.md)] can suggest this bin during put-away, depending on the put-away template and available space, and it preserves the record fixing the item to the bin even when the quantity in the bin is 0. Other items can be put into the bin, even though a particular item is fixed to the bin.  

> [!NOTE]  
> You can set up several bin contents at the same time on the **Bin Content Creation Worksheet** page.  

## To create bin content with a worksheet

When you have created your bins, you can create the bin content that you want for each bin in the bin content creation worksheet.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bin Content Creation Worksheet**, and then choose the related link.  
2. On the worksheet header, in the **Name** field, select the worksheet of the location where you want to create bin contents.  
3. In the **Bin Code** field, select the code of the bin for which you want to define bin content.  

    If you use directed put-away and pick in this location, the fields that relate to that particular bin, such as **Bin Type Code**, **Warehouse Class Code**, and **Bin Ranking**, fill in automatically. Consider this information as you define the bin content.  
4. Select the item that you want to assign to the bin, and fill in the fields related to the bin content. If you use directed put-away and pick, and you want to use the **Calculate Bin Replenishment** function, select **Fixed** and fill in the **Max. Qty.** and **Min. Qty.** fields.  

    To keep the item associated with the bin even if the bin quantity is **0**, select the **Fixed** field. Put-away suggestions depend on the put-away template.  
5. Repeat steps 3 through 4 for each item you want to assign to a bin.  
6. Select the **Print** action, and then preview or print the bin content you entered in the worksheet from the report request page. Continue to revise the bin content until you're satisfied.  
7. When you're ready, select the **Create Bin Content** action, and then confirm that you want to create the bin content.  

In this worksheet, you can work with a number of bin content lines for a number of bins and thereby obtain a good overview of what you are putting into various bins in a given zone, aisle, or rack.  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
