---
title: Gate Entry Inward Transactions
description: Gate Entry Inward Transactions.

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create and Attach Inward Gate Entries


Gate Entry Inward is used to track the entry of goods into the organization.

The following processes describe how to create and attach an Inward Gate Entry.

 - To create an Inward Gate Entry
 - To attach an Inward Gate Entry

## Inward gate entry can be created and attached to following documents.

1. Purchase Order / Purchase Invoice
2. Transfer Order
3. Sales Return order / Sales Credit memo

## To create an inward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Inward Gate Entry List**, and then choose the related link.
2. Fill in the fields as described in the following table on the **Inward Gate Entry** header.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Location Code**|Select the location code.|
    |**Station from**|Enter the station name from where goods are coming to factory location.|
    |**Description**|Enter gate entry description.|
    |**Item Description**|Enter item's description.|
    |**Document Date**|Document Date will be populated automatically and it will be system's date. User can also change the document date.|
    |**Document Time**|Document time will be populated automatically and it will be system's time. User can also change the document time.|
    |**Posting Date**|Posting date will be populated automatically and it will be same as the document date. User can also change the posting date.|
    |**Posting Time**|Posting time will automatically flow and it   will be system's time. User can also change the posting time.|
    |**LR/RR No.**|Enter the transport details such as lorry receipt number or railway receipt number for the gate entry.|
    |**LR/RR Date**|Select the lorry receipt date or railway receipt date.|
    |**Vehicle No.**|Enter the vehicle number in which goods are coming.|

3. On the **Inward gate entry** FastTab, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Challan No.**|Enter the challan number received.|
    |**Challan Date**|Enter the challan date.|
    |**Source Type**|Specify the source type against which you are creating the gate entry. Available options are: Blank, Sales Return Order, Purchase Order, and Transfer Receipt.|
    |**Source No.**|Select the source number for the selected source type. There is no need to select the Source No. if the Source Type is blank|
    |**Source Name**| This field shows the source name depending on the **Source Type** you have selected. If the Source Type is selected as Sales Return Order then it will show the customer name. If the Source Type is selected as Purchase Order then it will show the vendor name. If the Source Type is Transfer Receipt then it will show the location name.|
    |**Description**|Specify description if Source Type is blank.|

4. Click on **Action** -> **Posting** -> **Post** and post the document.

> [!NOTE]
> You can create multiple lines on Inward Gate Entry with different source type.

### View posted inward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Inward Gate Entry**, and then choose the related link.
2. In the **Posted Inward Gate Entry**, the **Status** field on the line level has the value as **Open**, it means **Posted Gate Entry – Inward** is still open for attachment. 
3. **Status** field will be updated once **Purchase Order** gets posted.  


### To attach an inward gate entry if the source type is purchase order

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Order**, and then choose the related link.
2. Select the relevant purchase order and click on **Action** -> **Functions** -> **Get Gate Entry Lines**.
3. To view the attached gate entry, click on **Action** -> **Functions** -> **Attached Gate Entry**.
4. Post the purchase order document.

> [!NOTE]
> - Same steps also apply for attaching **Inward Gate Enry** to a **Purchase Invoice**.
> - Posted gate entry lines can also be attached to **Warehouse Receipts**.

### To attach an inward gate entry if the source type is transfer receipt

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Transfer Order**, and then choose the related link.
2. Select the required transfer order and click on **Action** -> **Functions** -> **Get Gate Entry Lines** and click.
3. To view the attached gate entry, click on **Related** -> **Receipt** -> **Attached Gate Entry**.
4. Post the transfer order document.

### To attach an inward gate entry if the source type is sales return order

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Return Order**, and then choose the related link.
2. Select the required sales return order and click on **Action** -> **Functions** -> **Get Gate Entry Lines** and click.
3. To view the attached gate entry, click on **Related** -> **Warehouse** -> **Attached Gate Entry**.
4. Post the sales return order document.

> [!NOTE]
> - Same steps also apply for attaching an **Inward Gate Enry** to a **Sales Credit Memo**.
> - Source Type  blank is applicable only if the goods are received against **Purchase Invoice** or **Sales Credit Memo**.



## Related information 
[Gate Entry Outward Transaction](Gate-Entry-Outward_Transactions.md)







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
