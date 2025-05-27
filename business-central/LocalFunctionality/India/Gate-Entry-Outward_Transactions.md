---
title: Gate Entry Outward Transactions
description: Gate Entry Outward Transactions.

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create and Attach Outward Gate Entries



Gate Entry Outward is used to track the exist of goods from the organization.

The following processes describe how to create and attach an Outward Gate Entry.

- To create an Outward Gate Entry
- To view an attached Outward Gate Entry


## Outward gate entry can be created and attached to following documents.

1. Sales Order / Sales Invoice
2. Transfer Shipment
3. Purchase Return Order/ Purchase Credit Memo

### To create an outward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Outward Gate Entry List**, and then choose the related link.
2. Fill in the fields as described in the following table on the **Onward Gate Entry** header.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Location Code**|Select the location code.|
    |**Station To**|Enter the station name, to which goods are dispatching from factory location.|
    |**Description**|Enter general description in this field.|
    |**Item Description**|Enter item's description which you are dispatching.|
    |**Document Date**|Document date will automatically be populated and it will be system's date. User can also change the document date.|
    |**Document Time**|Document time will automatically be populated and it will be system's time. User can also change the document time.|
    |**Posting Date**|Posting date will automatically be populated and it will be same as the document date. User can also change the posting date.|
    |**Posting Time**|Posting time will automatically be populated and it will be system's time. User can also change the posting time.|
    |**LR/RR No.**|Enter the transport details such as lorry receipt number or railway receipt number for the gate entry.|
    |**LR/RR Date**|Select the lorry receipt date or railway receipt date.|
    |**Vehicle No.**|Enter the vehicle number in which goods are being dispatched.|

3.  On the **Onward gate entry** FastTab, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Challan No.**|Enter the challan number received.|
    |**Challan Date**|Enter the challan date.|
    |**Source Type**|Specify the source type against which you are creating the gate entry. Available options are: Blank, Sales Return Order, Purchase Order, and Transfer Receipt.|
    |**Source No.**|Select the source number for the selected source type. There is no need to select the Source No. if the Source Type is blank.|
    |**Source Name**| This field shows the source name depending on the **Source Type** you have selected. If the Source Type is selected as Sales Return Order then it will show the customer name. If the Source Type is selected as Purchase Order then it will show the vendor name. If the Source Type is Transfer Receipt then it will show the location name.|
    |**Description**|Specify description if Source Type is blank.|

4. Click on **Action** -> **Posting** -> **Post** and post the document.

> [!NOTE]
> - You can also create multiple lines on Outward Gate Entry with different source types.

### View posted outward gate entry

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Outward Gate Entry**, and then choose the related link.
2. In the **Posted Outward Gate Entry**, the **Status** field on the line level has the value as **Open**, it means **Posted Gate Entry – Outward** is still open for attachment. 
3. **Status** field will be updated once source document gets posted.  

System will automatically attach the Outward Gate Entry with the source number you have entered.
### To view attached outward gate entry if the source type is sales shipment


1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Shipment**, and then choose the related link.
2. Select the required posted sales shipment and click on **Related** -> **Shipment** -> **Attached Gate Entry** and click.


### To view attached outward gate entry if the source type is transfer shipment

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Transfer Shipment**, and then choose the related link.
2. Select the required posted transfer shipment and click on **Related** -> **Shipment** -> **Attached Gate Entry**.
3. On this page you can view the attached gate entry with the transfer shipment.


### To view an outward gate entry if the source type is purchase return shipment

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posted Return Shipment**, and then choose the related link.
2. Select the required posted return shipment and click on **Related** -> **Return Shpt.** -> **Attached Gate Entry**.
3. On this page you can view the attached gate entry with the purchase return shipment.





## Related information 
[Gate Entry Overview](Gate-Entry-001-Basic-Setup.md)







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
