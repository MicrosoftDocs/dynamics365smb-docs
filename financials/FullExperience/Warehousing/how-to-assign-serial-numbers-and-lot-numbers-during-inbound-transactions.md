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
# How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions
Companies may want to keep track of items from the moment they enter the company. In this situation, the purchase order is often the central document, although item tracking may be handled from any inbound document and its posted entries displayed in the related item ledger entries.  
  
 The exact rules for handling item tracking numbers across your company are governed by the setup in the **Item Tracking Code Card** window.  
  
> [!NOTE]  
>  To use item tracking numbers in warehouse activities, the **Lot Warehouse Tracking** and **SN Warehouse Tracking** setup fields must be selected, as they define the special principles in handling serial and lot numbers in warehouse activities.  
  
### To assign serial or lot numbers during an inbound transaction  
  
1.  In the **Search** box, enter **Purchase Oders**, and then choose the related link.  
  
2.  Select the relevant document line and on the **Lines** FastTab, choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Item Tracking Lines**.  
  
     You can assign serial or lot numbers in the following ways:  
  
    -   Automatically, by choosing **Assign Serial No.** or **Assign Lot No.** to assign serial\/lot numbers from predefined number series.  
  
    -   Automatically, by choosing **Create Customized SN** to assign serial\/lot numbers based on number series you define specifically for the arrived items.  
  
    -   Manually, by entering serial or lot numbers directly, for example, the vendor's numbers.  
  
    -   Manually, by assigning a specific number to each item unit.  
  
3.  To assign automatically, on the **Actions** tab, in the **Functions** group, choose **Create Customized SN**.  
  
4.  In the **Customized SN** field, enter the starting number of a descriptive serial number series, for example **S\/N-Vend0001**.  
  
5.  In the **Increment** field, enter 1 to define that each sequential number increases by one.  
  
     The **Quantity to Create** field contains the line quantity by default, but you can modify it.  
  
6.  Place a check mark in the **Create New Lot No.** field to organize the new serial numbers in a distinct lot.  
  
7.  Choose the **OK** button.  
  
 A lot number with individual serial numbers is created according to the item quantity of the document line, starting from **S\/N-Vend0001**.  
  
 The matrix of quantity fields in the header displays dynamically the quantities and sums of the item tracking numbers you define in the window. The quantities must correspond to those of the document line, which is signified by 0 in the **Undefined** fields.  
  
 When the document is posted, the item tracking entries are carried to the associated item ledger entries.  
  
## See Also  
 Lot Warehouse Tracking   
 SN Warehouse Tracking   
 Item Tracking Code Card   
 [How to: Set Up Item Tracking Codes](../FullExperience/how-to-set-up-item-tracking-codes.md)