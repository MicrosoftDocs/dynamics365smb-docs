---
title: "How to: Move Items Ad Hoc in Basic Warehousing"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "movements, between bins"
  - "movements, ad hoc"
  - "movements, registering"
  - "bins, moving items between"
ms.assetid: b0d09241-daeb-4e88-9e6c-97d21cafc70c
caps.latest.revision: 22
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
# How to: Move Items Ad Hoc in Basic Warehousing
You may occasionally need to move items between internal bins, not receiving or shipping bins, without a specific demand from a source document. You may perform these ad hoc movements, for example, to reorganize the warehouse, to bring items to an inspection area, or to move additional items to and from a production area without a system relation to the production order source document.  
  
> [!NOTE]  
>  For information about moving items between bins based on source documents, see Inventory Movement.  
  
 In basic warehouse configurations, that is locations that use the **Bin Mandatory** setup field and possibly the **Require Pick** and the **Require Put\-away** setup fields, you can register ad hoc movements without source documents in the following ways:  
  
-   With the **Internal Movement** window.  
  
-   With the **Item Reclassification Journal** window.  
  
> [!NOTE]  
>  In advanced warehouse configurations, that is locations that use the **Directed Put\-away and Pick** setup field, you use the **Movement Worksheet** window or the **Internal Whse. Pick** or the **Internal Whse. Put\-away** windows to move items ad hoc between bins.  
  
### To move items as an internal movement  
  
1.  In the **Search** box, enter **Internal Movement**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the **No.** field, either by leaving the field or by choosing the **AssistEdit** button to select from the number series.  
  
3.  In the **Location Code** field, enter the location where the movement takes place.  
  
     If the location is set up as your default location as a warehouse employee, the location code is inserted automatically.  
  
4.  In the **To Bin Code** field, enter a code for the bin that you want to move the item to. For production purposes, this could be the open shop floor bin code, for example, as defined on the location card or work center.  
  
5.  In the **Due Date** field, enter the date by which the movement must be completed.  
  
6.  On the **Lines** FastTab, choose the **Item No.** field to open the **Bin Contents List** window, and then select the item to move based on its availability in bins. Alternatively, choose **Get Bin Contents** to fill the internal movement lines based on your filters. For more information, see Whse. Get Bin Content.  
  
     When you have selected the item, the **From Bin Code** field is automatically filled according to the selected bin content, but you can change it to any other bin where the item is available.  
  
    > [!NOTE]  
    >  Because the **Item No.** field and the **From Bin Code** field are connected, their values may change interdependently when you edit either field.  
  
     The **To Bin Code** field is filled with the value you entered on the header, but you can change it on the line to any other bin code that isn’t blocked or dedicated to special purposes. For more information about making bins dedicated, see Dedicated.  
  
7.  When you have defined which bins you want to move the item from and to, enter the quantity to move in the **Quantity** field.  
  
    > [!NOTE]  
    >  Quantity must be available in the From Bin code.  
  
8.  When you are ready to process the internal movement, choose **Create Inventory Movement**.  
  
    > [!NOTE]  
    >  When you have created the inventory movement, the internal movement lines are deleted.  
  
     You perform the remainder of the ad hoc movement in the **Inventory Movement** window in the same way as you would for a movement based on source documents. For more information, see for example [How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)  
  
### To move items with the item reclassification journal  
  
1.  In the **Search** box, enter **Item Reclass. Journal**, and then choose the related link.  
  
2.  On each journal line, define the bins from which and to which you want to move items by filling in the **Bin Code** and the **New Bin Code** fields.  
  
    1.  To move a bin's entire contents to another bin, on the **Actions** tab, in the **Functions** group, choose **Get Bin Contents**.  
  
    2.  Fill in the filters to find the bin whose contents you would like to move and then choose the **OK** button. The journal lines are filled with the contents of the bin.  
  
3.  Fill in the remaining fields on each journal line.  
  
4.  Post the reclassification journal.  
  
    > [!NOTE]  
    >  Unlike with movement documents, a movement posted with the reclassification journal does not create a warehouse request to perform the physical task.  
  
## See Also  
 Internal Movement   
 Inventory Movement   
 Item Reclass. Journal   
 To\-Production Bin Code   
 Dedicated   
 Whse. Get Bin Content   
 [How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Move Items in Advanced Warehousing](../WarehouseActivities/how-to-move-items-in-advanced-warehousing.md)