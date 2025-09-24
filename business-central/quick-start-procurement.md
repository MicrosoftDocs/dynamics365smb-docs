---
title: Procurement Quick Start
description: Learn how to fill in the first critical fields about vendors in Business Central so that you can start purchasing products and services.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: quickstart
ms.search.form: 26, 27, 50, 56
ms.date: 09/29/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Procurement Quick Start

To be able to buy products and services, you must first set up vendors. Once that is done, you can start registering purchase orders and receiving invoices.  

## Set up vendors

The following video shows you how to set up a vendor in [!INCLUDE[prod_short](includes/prod_short.md)].

<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=7188b662-bc49-45ef-8152-82898076b235]

### Set up a new vendor

[!INCLUDE[create_new_vendor](includes/create_new_vendor.md)]

For more information and additional things you can do when you register vendors, see [Register New Vendors](purchasing-how-register-new-vendors.md).  

## Create new purchase orders

When you buy something from a vendor you have two options. The first, and simplest, is to just create a purchase invoice. However, you must use purchase orders if your purchasing process requires that you record partial receipts of an order quantity, for example, because the full quantity was not available at the vendor.

The following video shows you how to create a purchase order in [!INCLUDE[prod_short](includes/prod_short.md)].

<br><br>

> [!Video https://learn-video.azurefd.net/vod/player?id=f04b1ed3-5cb0-4fa8-8cd0-24069ee893d2]

### To create a purchase order  

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  

2. On the **Purchase Orders** page, select the **New** action to create a new Purchase Order.

3. In the **Vendor Name** field, enter the name of an existing vendor.

    Other fields on the **Purchase Header** are now filled with the standard information about the selected vendor.  

4. Fill in the remaining fields on the **Purchase Order** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    You are now ready to fill in the purchase order lines with items or resources that you have purchased from the vendor.

5. On the **Lines** FastTab, in the **Item No.** field, enter the number of an inventory item or service.

6. In the **Quantity** field, enter the number of items to be purchased.

    The **Line Amount** field is updated to show the value in the **Direct Unit Cost** field multiplied by the value in the **Quantity** field.

7. In the **Order Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field at the bottom of the order.

8. When you receive the purchased items or services, choose **Post**.

For more information and additional things you can do when creating a purchase order, see [Purchasing](purchasing-manage-purchasing.md).  

## Create a purchase invoice  

You create a purchase invoice to record the cost of purchases and to track accounts payable. Creating a purchase invoice is similar to creating a purchase order.

### How to create and post a purchase invoice  

1. Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. On the **Purchase Invoice** page, select the **New** action to create a new Purchase Invoice.
3. In the **Vendor** field, enter the name of an existing vendor.

    Other fields on the **Purchase Invoice** page are now filled with the standard information of the selected vendor.

4. Fill in the remaining fields on the **Purchase Invoice** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    You are now ready to fill in the purchase invoice lines with items or resources that you have purchased from the vendor.

5. On the **Lines** FastTab, in the **Item No.** field, enter the number of an inventory item or service.
6. In the **Quantity** field, enter the number of items to be purchased.

    The **Line Amount** field is updated to show the value in the **Direct Unit Cost** field multiplied by the value in the **Quantity** field.

7. In the **Invoice Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field at the bottom of the invoice.

8. When you receive the purchased items or services, choose **Post**.

The purchase is now reflected in inventory, resource ledgers, and financial records, and the vendor payment is activated. The purchase invoice is removed from the list of purchase invoices and replaced with a new document in the list of posted purchase invoices.  

For more information and additional things you can do when creating a purchase invoice, see [Record Purchases with Purchase Invoices](purchasing-how-record-purchases.md).

## Related information

[Business Central Quick Starts](quick-start-business-central.md)  
[Purchasing Overview](Purchasing-manage-purchasing.md)  
[Record Purchases with Purchase Invoices](purchasing-how-record-purchases.md)  
