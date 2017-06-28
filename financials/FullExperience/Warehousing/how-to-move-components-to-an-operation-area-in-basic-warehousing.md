---
title: "How to: Move Components to an Operation Area in Basic Warehousing"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "operations, moving items between"
  - "assembly, picking"
  - "picking, assembly"
ms.assetid: cb29f20e-80d7-42d6-9f77-68ad8399d9e3
caps.latest.revision: 25
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
# How to: Move Components to an Operation Area in Basic Warehousing
If item processing operations occur at your warehouse location, then you may have to move items between internal bins to respond to internal source documents, such as production, assembly, or service orders at the location.  
  
> [!NOTE]  
>  For information about moving items between bins without source documents, see [\($ N\_7399 Internal Movement $\)](../Topic/\($%20N_7399%20Internal%20Movement%20$\).md).  
  
 In advanced warehouse configurations, which are locations that use the **Directed Put\-away and Pick** setup field, you can use the **Movement Worksheet** window to move items between bins. For more information, see [How to: Move Items in Advanced Warehousing](../WarehouseActivities/how-to-move-items-in-advanced-warehousing.md).  
  
 In basic warehouse configurations, which are locations that use the **Bin Mandatory** setup field and the **Require Pick** setup field, you can register movement of items to internal operation areas based on internal source documents in the following ways:  
  
-   With the **Inventory Movement** window.  
  
-   With the **Inventory Pick** window.  
  
> [!NOTE]  
>  Inventory picks also post negative item ledger entries as consumption and are only supported for production components. For more information, see the [\($ N\_7377 Inventory Pick $\)](../Topic/\($%20N_7377%20Inventory%20Pick%20$\).md) window.  
  
 For detailed information about inventory movements, see the [\($ N\_7382 Inventory Movement $\)](../Topic/\($%20N_7382%20Inventory%20Movement%20$\).md) window.  
  
 Two different roles can create the initial inventory movement. An assembly worker, for example, can create it from a released assembly order so that it shows up in the warehouse worker’s list of work to do. To create an inventory movement for assembly order lines that are ready to have components moved to their specified bins, the assembly worker uses the **Create Inventory Movement** function.  
  
 Alternatively, a warehouse worker can create it by pointing to the released assembly order in question. This is described in the following procedure.  
  
> [!NOTE]  
>  If the movement is for an assembly order where the item is assembled to a sales order, then you can define that the inventory movement document is automatically created when you create the inventory pick document that takes the finished assembly item and posts the shipment. To set this up, select the **\($ T\_905\_130 Create Movements Automatically $\)** field in the **\($ N\_905 Assembly Setup $\)** window  
>   
>  For more information about assembly orders and basic warehousing, see [Handling Assemble-to-Order Items in Inventory Picks](../Topic/\($%20N_7377%20Inventory%20Pick%20$\).md#BKMK_HandlingAssembletoOrderItemsinInventoryPicks).  
  
 This procedure shows how to create an inventory movement from the **Inventory Movement** window by referencing a released assembly order as a source document. The procedure is the same when you move components for production orders and service orders.  
  
### To move components to an operation area in basic warehousing  
  
1.  In the **Search** box, enter **\($ N\_7382 Inventory Movement $\)**, and choose the relevant link.  
  
2.  On the **General** FastTab, fill in the **No.** field. You can press the Enter key  to select from the number series.  
  
3.  In the **Location Code** field, enter the location where the movement occurs.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Get Source Documents**. Alternatively, fill in the **Source Document** field, and then choose the **AssistEdit** button in the **Source No.** field.  
  
5.  In the **Source Documents** window, select the assembly order that you want to move components for, and then choose the **OK** button.  
  
     For each needed component that can be moved, one Take line and one Place line are generated in the **Inventory Movements** window. All fields except the **Qty. to Handle** field are prefilled according to the source document lines. The **Qty. to Handle** field is set to zero until you enter the quantity that you have actually moved.  
  
     You can change the bin code on a Take line but only according to availability. If you choose the **AssistEdit** button in the **Bin Code** field on a Take line, then the **Bin Contents** window opens and only shows bins where the component is available.  
  
     You cannot change the bin code on a Place line. Only the bin code that is defined on the component line of the source document is accepted. This supports the principle that the role who requests a component, which is an assembly worker in this procedure, knows where the component must be placed. If you want to place the components in a different bin, then you must first change the bin code on the component line and then re\-create the inventory movement lines.  
  
6.  In the **Qty. to Handle** field, enter the full or partial quantity that you have actually moved. The value on the Take and the Place lines must be the same. Otherwise, you cannot register the movement.  
  
    > [!NOTE]  
    >  As in other warehouse activities, you can split the Place line by selecting **Actions** and then selecting **Split Line**. In that case, the sum of the two split Place lines must equal the quantity on the Take line.  
  
7.  When you are ready to register the movements that you have performed, choose the **Register Invt. Movement** button.  
  
     Warehouse entries are created reflecting that the components now exist in the bins specified on the assembly order lines.  
  
    > [!NOTE]  
    >  Unlike when you move components with an inventory pick, consumption is not posted when you register an inventory movement. That step must be performed separately by posting the assembly order output and consumption. For more information, see [\($ N\_900 Assembly Order $\)](../WarehouseActivities/-$-n_900-assembly-order-$-.md).  
  
## See Also  
 [\($ N\_7382 Inventory Movement $\)](../Topic/\($%20N_7382%20Inventory%20Movement%20$\).md)   
 [\($ N\_905 Assembly Setup $\)](../Topic/\($%20N_905%20Assembly%20Setup%20$\).md)   
 [\($ T\_5407\_33 Bin Code $\)](../Topic/\($%20T_5407_33%20Bin%20Code%20$\).md)   
 [\($ T\_905\_130 Create Movements Automatically $\)](../Topic/\($%20T_905_130%20Create%20Movements%20Automatically%20$\).md)   
 [\($ T\_14\_7330 To\-Assembly Bin Code $\)](../Topic/\($%20T_14_7330%20To-Assembly%20Bin%20Code%20$\).md)   
 [\($ T\_5409\_7302 To\-Production Bin Code $\)](../Topic/\($%20T_5409_7302%20To-Production%20Bin%20Code%20$\).md)   
 [How to: Pick for Production in Basic Warehousing](../WarehouseActivities/how-to-pick-for-production-in-basic-warehousing.md)   
 [\($ N\_7377 Inventory Pick $\)](../Topic/\($%20N_7377%20Inventory%20Pick%20$\).md)   
 [\($ N\_7399 Internal Movement $\)](../Topic/\($%20N_7399%20Internal%20Movement%20$\).md)   
 [\($ N\_7315 Warehouse Movement $\)](../Topic/\($%20N_7315%20Warehouse%20Movement%20$\).md)   
 [\($ N\_900 Assembly Order $\)](../WarehouseActivities/-$-n_900-assembly-order-$-.md)   
 [How to: Move Items in Advanced Warehousing](../WarehouseActivities/how-to-move-items-in-advanced-warehousing.md)