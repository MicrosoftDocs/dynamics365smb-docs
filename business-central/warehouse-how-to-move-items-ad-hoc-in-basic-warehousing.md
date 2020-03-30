---
title: How to Move Items Ad Hoc in Basic Warehouse Configurations | Microsoft Docs
description: You may occasionally need to move items between internal bins, not receiving or shipping bins, without a specific demand from a source document. You may perform these ad hoc movements, for example, to reorganize the warehouse, to bring items to an inspection area, or to move additional items to and from a production area without a system relation to the production order source document.
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
# Move Items Ad Hoc in Basic Warehouse Configurations
You may occasionally need to move items between internal bins, not receiving or shipping bins, without a specific demand from a source document. You may perform these ad hoc movements, for example, to reorganize the warehouse, to bring items to an inspection area, or to move additional items to and from a production area without a system relation to the production order source document.  

In basic warehouse configurations, that is locations that use the **Bin Mandatory** setup field and possibly the **Require Pick** and the **Require Put-away** setup fields, you can register ad hoc movements without source documents in the following ways:  

- With the **Internal Movement** page.  
- With the **Item Reclassification Journal** page.  

> [!NOTE]  
>  In advanced warehouse configurations, that is locations that use the **Directed Put-away and Pick** setup field, you use the **Movement Worksheet** page or the **Internal Whse. Pick** or the **Internal Whse. Put-away** pages to move items ad hoc between bins.  

## To move items as an internal movement  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Internal Movement**, and then choose the related link.  
2.  On the **General** FastTab, fill in the **No.** field, either by leaving the field or by choosing the **AssistEdit** button to select from the number series.  
3.  In the **Location Code** field, enter the location where the movement takes place.  

    If the location is set up as your default location as a warehouse employee, the location code is inserted automatically.  
4.  In the **To Bin Code** field, enter a code for the bin that you want to move the item to. For production purposes, this could be the open shop floor bin code, for example, as defined on the location card or work center.  
5.  In the **Due Date** field, enter the date by which the movement must be completed.  
6.  On the **Lines** FastTab, choose the **Item No.** field to open the **Bin Contents List** page, and then select the item to move based on its availability in bins. Alternatively, choose the **Get Bin Contents** action to fill the internal movement lines based on your filters. For more information, see the tooltip for the **Get Bin Content** action.   

    When you have selected the item, the **From Bin Code** field is automatically filled according to the selected bin content, but you can change it to any other bin where the item is available.  

    > [!NOTE]  
    >  Because the **Item No.** field and the **From Bin Code** field are connected, their values may change interdependently when you edit either field.  

    The **To Bin Code** field is filled with the value you entered on the header, but you can change it on the line to any other bin code that isn’t blocked or dedicated to special purposes. For more information about making bins dedicated, see Dedicated.  
7.  When you have defined which bins you want to move the item from and to, enter the quantity to move in the **Quantity** field.  

    > [!NOTE]  
    >  Quantity must be available in the From Bin code.  

8.  When you are ready to process the internal movement, choose the **Create Inventory Movement** action.  

    > [!NOTE]  
    >  When you have created the inventory movement, the internal movement lines are deleted.  

    You perform the remainder of the ad hoc movement on the **Inventory Movement** page in the same way as you would for a movement based on source documents. For more information, see for example [Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)  

## To move items with the item reclassification journal
In stead of using warehouse movement documents, you can record the moving of items by reclassifying their bin codes. For more information, see [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md).   
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Reclass. Journal**, and then choose the related link.  
2.  On each journal line, define the bins from which and to which you want to move items by filling in the **Bin Code** and the **New Bin Code** fields.  

    1.  To move a bin's entire contents to another bin, choose the **Get Bin Contents** action.  
    2.  Fill in the filters to find the bin whose contents you would like to move and then choose the **OK** button. The journal lines are filled with the contents of the bin.  
3.  Fill in the remaining fields on each journal line.   
4.  Post the reclassification journal.  

    > [!NOTE]  
    >  Unlike with movement documents, a movement posted with the reclassification journal does not create a warehouse request to perform the physical task.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
