---
    title: How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions | Microsoft Docs
    description: You can add serial numbers and lot numbers to any outbound document, and its posted item tracking entries are displayed in the related item ledger entries. There are two ways to add serial and lot numbers to outbound transactions:
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
# How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions
You can add serial numbers and lot numbers to any outbound document, and its posted item tracking entries are displayed in the related item ledger entries. There are two ways to add serial and lot numbers to outbound transactions:  
  
-   Selecting from existing serial or lot numbers. This applies when item tracking numbers have already been assigned during an inbound transaction. For more information, see [How to: Select from Existing Serial Numbers and Lot Numbers](../how-to-select-from-existing-serial-numbers-and-lot-numbers.md).  
  
-   Assigning new serial or lot numbers during outbound transactions. This applies when item tracking numbers are not assigned to items until they are sold and ready to be shipped.  
  
 The different rules for item tracking numbers are set up in the **Item Tracking Code Card** window.  
  
> [!NOTE]  
>  To assign item tracking numbers in warehouse activities, the **SN Warehouse Tracking** and **Lot Warehouse Tracking** check boxes must be selected on the item’s item tracking code card.  
  
### To assign a serial or lot number during outbound transaction  
  
1.  Select the relevant document and, on the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Item Tracking Lines**.  
  
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
 Item Tracking Code Card   
 SN Warehouse Tracking   
 Lot Warehouse Tracking   
 [How to: Select from Existing Serial Numbers and Lot Numbers](../how-to-select-from-existing-serial-numbers-and-lot-numbers.md)