---
title: How to Move Items in advanced warehouse configurations | Microsoft Docs
description: In advanced warehouse configurations, that is, locations with directed put-away and pick, warehouse movements between bins are performed by a senior employee preparing warehouse movements in the movement worksheet and then creating the warehouse movements for warehouse employees to perform.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Move Items in Advanced Warehouse Configurations
In advanced warehouse configurations, that is, locations with directed put-away and pick, warehouse movements between bins are performed by a senior employee preparing warehouse movements in the movement worksheet and then creating the warehouse movements for warehouse employees to perform.  

## To move items with the warehouse movement worksheet
The **Movement Worksheet** page has two functions that can assist in automatically filling in the lines. The first is the **Calculate Bin Replenishment** function. This function uses the bin rankings to suggest replenishment for high-ranking bins from low-ranking bins. The second is the **Get Bin Content** function, which fills in the worksheet lines with the entire bin contents of the bin or bins you specify.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheet**, and then choose the related link.  
2.  Enter the warehouse movement information on the worksheet lines as appropriate.  
3. Choose the **Create Movement** action to create a warehouse movement document which can then be registered when the warehouse movement is completed.  

### To register the warehouse movement  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movements**, and then choose the related link.  
2.  Open the warehouse movement that you want to process.  
3.  On lines of action type **Place**, specify where, which, and when to move the item in question by editing the **Zone Code**, **Bin Code**, **Qty. to Handle**, or **Due Date** fields.  

    If your warehouse has been set up so the bin codes follow the physical structure of the warehouse, you can take quantities of several items from successive bulk bins and then place them in forward picking bins, which also might be close to one another.  
4.  On lines of action type **Take**, specify in the **Qty. to Handle** field a part quantity of the bin content that you want to move. All other fields on lines of action type **Take** are read-only.  
5.  To move all suggested quantities as specified in the **Quantity** field, choose the **Autofill Qty. to Handle** action.  
6. Choose the **Register** action.  

> [!NOTE]  
>  If the location uses directed put-away and pick, then you cannot manually move items in or out of bins of bin type RECEIVE, because items in such bins must be registered as being put away before they are part of available inventory.

## To register the movement of an item that has already occurred  
If your location uses directed put-away and pick, and you need to move items to other bins without a pre-existing warehouse put-away, pick, or movement, you can register the correct placement of the items in the warehouse using the **Whse. Reclassification Journal**.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Reclassification Journal**, and then choose the related link.  
2.  Fill in the **Item No.**, **From Zone Code**, **From Bin Code**, **To Zone Code**, and **To Bin Code** fields.  
3.  Choose the **Register** action.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
