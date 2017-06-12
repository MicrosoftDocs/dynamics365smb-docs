---
title: "How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales orders, handling numbers"
  - "serial numbers, handling in inbound transactions"
  - "item tracking, handling in inbound transactions"
  - "sales orders, selecting numbers"
  - "lot numbers, handling in inbound transactions"
ms.assetid: 77f9eb04-6acc-416c-b842-0a3e53ae788b
caps.latest.revision: 7
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions
You can add serial numbers and lot numbers to any outbound document, and its posted item tracking entries are displayed in the related item ledger entries. There are two ways to add serial and lot numbers to outbound transactions:  
  
-   Selecting from existing serial or lot numbers. This applies when item tracking numbers have already been assigned during an inbound transaction. For more information, see [How to: Select from Existing Serial Numbers and Lot Numbers](../DesignAndEngineering/how-to-select-from-existing-serial-numbers-and-lot-numbers.md).  
  
-   Assigning new serial or lot numbers during outbound transactions. This applies when item tracking numbers are not assigned to items until they are sold and ready to be shipped.  
  
 The different rules for item tracking numbers are set up in the **Item Tracking Code Card** window.  
  
> [!NOTE]  
>  To assign item tracking numbers in warehouse activities, the **SN Warehouse Tracking** and **Lot Warehouse Tracking** check boxes must be selected on the item’s item tracking code card.  
  
### To assign a serial or lot number during outbound transaction  
  
1.  Select the relevant document and, on the **Lines** FastTab, choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Item Tracking Lines**.  
  
     You can assign item tracking numbers in the following ways:  
  
    -   Automatically, from predefined number series: On the **Actions** tab, in the **Functions** group, choose **Assign Serial No.** or **Assign Lot No.**.  
  
    -   Automatically, based on parameters you define specifically for the outbound item: On the **Actions** tab, in the **Functions** group, **Create Customized SN**.  
  
    -   Manually, by entering serial or lot numbers, without using a number series.  
  
2.  For this procedure, assign a serial number automatically by choosing **Assign Serial No.**  
  
     The **Quantity to Create** field contains the line quantity by default, but you can modify it.  
  
3.  Select the **Create New Lot No.** field to organize the new serial numbers in a distinct lot.  
  
4.  Choose the **OK** button to create a lot number and new individual serial numbers according to the quantity to handle on the related document line.  
  
 The matrix of quantity fields in the header displays dynamically the quantities and sums of the item tracking numbers that you define in the window. The quantities must correspond to those of the document line, which is signified by **0** in the **Undefined** fields.  
  
 When the document is posted, the item tracking entries are carried to the associated item ledger entries.  
  
## See Also  
 [Item Tracking Code Card](../Topic/\($%20N_6512%20Item%20Tracking%20Code%20Card%20$\).md)   
 [SN Warehouse Tracking](../Topic/\($%20T_6502_15%20SN%20Warehouse%20Tracking%20$\).md)   
 [Lot Warehouse Tracking](../Topic/\($%20T_6502_45%20Lot%20Warehouse%20Tracking%20$\).md)   
 [How to: Select from Existing Serial Numbers and Lot Numbers](../DesignAndEngineering/how-to-select-from-existing-serial-numbers-and-lot-numbers.md)