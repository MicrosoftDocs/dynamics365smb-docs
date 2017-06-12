---
title: "How to: Put Away Production Output"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "production orders, putting away output"
  - "inbound warehouse, putting away"
  - "putting away, movement"
  - "putting away, production output"
  - "putting away, with internal put-away"
ms.assetid: 1273ba6f-7f21-433a-b9e7-2388bfe90c9b
caps.latest.revision: 11
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
# How to: Put Away Production Output
How you put away your output from production depends on how your warehouse is set up as a location.  
  
 The first step in creating the inventory put\-away is to create the inbound warehouse request. This request informs the warehouse that the production order output is ready for put\-away. Someone working in the warehouse creating inventory put\-aways can then see that the production order is ready and can create the inventory put\-away for the output.  
  
 In basic warehousing where your warehouse location requires put\-away processing, but not receive processing, you use the **Inventory Put\-away** document to organize and record the put\-away of output.  
  
 In advanced warehousing where your location requires both put\-away and receive processing, you create either an internal put\-away document or a movement document to put away the output.  
  
### To create the inbound warehouse request  
  
1.  In the **Search** box, enter **Released Production Order**, and then choose the related link.  
  
2.  On the production order that is ready for put\-away, on the **Actions** tab, in the **Warehouse** group, choose **Create Inbound Whse. Request**.  
  
 You can also create the inbound warehouse request automatically when you refresh the production order. For more information, see the **Create inbound Request** field in the [Refresh Production Order](../Production/-$-b_99001025-refresh-production-order-$-.md) window.  
  
### To put output away with an inventory put\-away  
  
1.  In the **Search** box, enter **Inventory Put\-away**, and then choose the related link.  
  
2.  Create a new inventory put\-away.  
  
3.  To access the production order output, on the **Actions** tab, in the **Functions** group, choose **Get Source Documents** and select the released production order.  
  
4.  Fill in the put\-away lines as appropriate. To print a put\-away list, choose the **Print** button.  
  
5.  When the lines are ready for posting, on the **Actions** tab, in the **Posting** group, choose **Post**. The posting will create the necessary warehouse entries and post the output of the items.  
  
 You can also create an **Inventory Put\-away** directly from the released production order. For more information, see [Create Invt. Put\-Away \- Pick](../Topic/\($%20R_7323%20Create%20Invt.%20Put-Away%20-%20Pick%20$\).md).  
  
 When you do an inventory put\-away, posting it assumes that all the operations are posted according to the standard routing, that is, output quantity is posted according to the last operation. You can use the output journal to post variances in output quantity and the setup and run times. If it is required to post partially after you have created the inventory put\-away, you can do so on setup times and quantities for all operations except the last one. In that case, the last operation is controlled by the inventory put\-away.  
  
 If you only need to post setup or run time on the last operation, then set the output quantity on the last operation to 0. Alternatively, you can choose not to post the last line at all by simply deleting it  
  
### To put output away with a warehouse internal put\-away  
  
1.  In the **Search** box, enter **Whse. Internal Put\-away**, and then choose the related link.  
  
     Create a new warehouse internal put\-away.  
  
2.  Fill in the header of a new internal put\-away with at least the **Location Code**.  
  
3.  Fill in a line for each item you wish to move to the warehouse. You only have to fill in the **Item No.** and the **Quantity** fields.  
  
    > [!NOTE]  
    >  When you select the **Item No.** field, the **Bin Contents List** opens instead of the **Item List**. This is because you want to put away an item that is in a particular bin \- a Bin Content \- not just an item, and you already know the bin the item should be taken from.  
  
4.  To fill the worksheet lines with the entire bin content or the filtered bin content of bins in the location, on the **Actions** tab, in the **Functions** group, choose **Get Bin Content**.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create Put\-away**, and the items you want to move out of production are now on put\-away instructions waiting to be stored in the warehouse.  
  
> [!NOTE]  
>  When your warehouse location is set up to use directed put\-away and pick, the warehouse is linked to your manufacturing facility through the default production bins: the inbound and outbound production bins and the open shop bin, all of which you define on the **Bins** FastTab of the location card. When you post the output of a production order, the output is placed in the **Outbound Production Bin**. You follow the same procedure as described above to put\-away the production output, except that instead of using the item's default bin, you will move or put\-away the items from the **Outbound Production Bin** to the item's default bin.  
  
### To manually specify a bin to store items from production output  
  
1.  In the **Search** box, enter **Movement Worksheet**, and then choose the related link.  
  
2.  Fill in the header, and create a line for each item you wish to move to the warehouse.  
  
3.  Fill in both the **From Bin Code** and the **To Bin Code** fields, and enter the quantity in the **Quantity** field.  
  
4.  To fill the worksheet lines with the entire bin content or the filtered bin content of bins in the location, on the **Actions** tab, in the **Functions** group, choose **Get Bin Content**.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create Movement.** The warehouse movement instructions are created with Take and Place lines for warehouse employees to perform.  
  
> [!NOTE]  
>  You cannot enter the source document number, such as the Production Order No., in the internal put\-away, put\-away, or movement documents for either of these procedures.  
  
## See Also  
 [Put Items Away](../WarehouseActivities/put-items-away.md)   
 [How to: Put Items Away with Inventory Put\-aways](../DesignAndEngineering/how-to-put-items-away-with-inventory-put-aways.md)   
 [How to: Put Items Away with Warehouse Put\-aways](../WarehouseActivities/how-to-put-items-away-with-warehouse-put-aways.md)   
 [How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Pick for Internal Operations in Advanced Warehousing](../WarehouseActivities/how-to-pick-for-internal-operations-in-advanced-warehousing.md)