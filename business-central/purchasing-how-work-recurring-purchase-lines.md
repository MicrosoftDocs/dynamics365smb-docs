---
title: Standard recurring purchase lines
description: Set up frequently used purchase lines to insert them on purchase documents and quickly fill the lines with standard information.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: trade, purchase, replenishment, vendor order
ms.search.form: 177
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create recurring purchase lines

If you often need to create purchase lines with similar information, you can set up standard lines that you can then insert on recurring purchase documents, for example, for recurring replenishment orders.

## Set up recurring purchase lines

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Recurring Purchase Lines**, and then choose the related link.
2. On the **Recurring Purchase Lines** page, choose the **New** action.
3. On the **General** FastTab, fill the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. On the **Lines** FastTab, enter the information in the fields that reflect the standard lines you expect to use as recurring lines on purchase documents.

> [!NOTE]
> You can't define prices on recurring purchase lines because prices, discounts, etc. are calculated on the actual purchase documents after you insert the recurring purchase lines.

[!INCLUDE [line-no-info](includes/line-no-info.md)]

## Assign recurring purchase lines to a vendor

Assign one or more recurring purchase lines to a vendor so that they're available to insert on purchase documents from that vendor.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.
2. Open the card for a relevant vendor.
3. Choose the **Recurring Purchase Lines** action.
4. On the **Recurring Purchase Lines** page, select codes for the recurring purchase lines that you want to be able to insert on purchase documents for the vendor.
5. Fill in the other fields to define when, how, and where the recurring purchase lines are to be used.
6. In the four fields where you select how the lines are inserted on each document type, select one of the following options:

|Option|Description|
|------|-----------|
|**Manual**|You must manually look up and insert a recurring purchase line that exists for the vendor.|
|**Automatic**|If multiple recurring purchase lines exist for the vendor, you get a notification from where you can pick which one to insert. If only one recurring purchase line exists, it's inserted automatically.<br /><br />This only works if the new document was created from a document list, for example by choosing the **New** action on the **Purchase Orders** page. It doesn't work if the document was created from a vendor card, for example.|
|**Always Ask**|A notification appears and all existing recurring purchase lines are shown so that you can select one.

## Insert recurring purchase lines on a purchase invoice

If recurring purchase lines exist for the vendor, you can insert them, or have them automatically added, on all types of purchase documents, such as a purchase invoice. If you have activated the **Always Ask** options while assigning recurring purchase lines to vendors, you're informed if recurring purchase lines exist.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.
2. Open the purchase invoice that you want to insert one or more standard purchase lines on.
3. Choose the **Get Recurring Purchase Lines** action.
4. On the **Recurring Purchase Lines** page, choose the lookup button in the **Code** field, and then select a set of standard purchase lines.
5. Choose the **OK** button to insert the standard purchase lines on the invoice where you can reuse them as is or edit the information.

## Related information

- [Purchasing](purchasing-manage-purchasing.md)  
- [Set Up Purchasing](purchasing-setup-purchasing.md)  
- [Create Recurring Sales](sales-how-work-standard-lines.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
