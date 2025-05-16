---
title: Sales Quick Start
description: Learn how to fill in the first critical fields about products and customers in Business Central so that you can start your sales processes.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: quickstart
ms.date: 09/29/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Sales Quick Start

To be able to sell products and services, you must first set up items and customers. Once that is done, you can start registering sales orders and sending out invoices.

## Set up items to sell

This video shows how to set up an item to sell in [!INCLUDE[prod_short](includes/prod_short.md)].

<br>

> [!Video https://learn-video.azurefd.net/vod/player?id=a5e825b2-e309-4753-bdff-a6947dc314e6]

### Set up a new item

[!INCLUDE[create_new_item](includes/create_new_item.md)]

For more information and additional things you can do when setting up items, see [Register New Items](inventory-how-register-new-items.md).  

## Set up customers

This video shows how to set up a new customer in [!INCLUDE[prod_short](includes/prod_short.md)].  

<br>

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=37d3ec2a-71c2-4f0d-9a94-62c83805fbfa]

### Set up a new customer

[!INCLUDE[create_new_customer](includes/create_new_customer.md)]

For more information and additional things you can do when setting up customers, see [Register New Customers](sales-how-register-new-customers.md)

## Create a sales order  

When you sell something to a customer, you have two options. The first, and simplest, is to just create a sales invoice. However, if your sales process is more complex, for example if you have situations where you only ship parts of an order quantity, you use a sales order.

### To create a sales order  

1. Choose the ![Lightbulb that opens the Tell Me feature 10.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Select **New** to create a new entry.
3. In the **Customer** field, enter the name of an existing customer.

    Other fields on the **Sales Order** page are now filled with the standard information of the selected customer.  

4. Fill in the remaining fields on the **Sales Order** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

5. On the **Lines** FastTab, in the **Type** field, select what type of product, charge, or transaction that you will post for the customer with the sales line.

6. In the **No.** field, enter the number of an inventory item or service.

7. In the **Quantity** field, enter the number of items to be sold.

8. In the **Line Discount %** field, enter a percentage if you want to grant the customer a discount on the product.

9. To add a comment about the order line that the customer can see on the printed sales order, write a comment in the **Description** field on an empty line.

10. Repeat steps 5 through 9 for every item that you want to sell to the customer.

11. To only ship a part of the order quantity, enter that quantity in the **Qty. to Ship** field. The value is copied to the **Qty. to Invoice** field.

12. To only invoice a part of the shipped quantity, enter that quantity in the **Qty. to Invoice** field. The quantity must be lower than the value in the **Qty. to Ship** field.

13. When the sales order lines are completed, choose the **Post and Send** action.

For more information and additional things you can do when creating customer sales orders, see [Sell Products with a Customer Sales Order](sales-how-sell-products.md).  

## Create a sales invoice

When you create and post a sales invoice, you not only create the invoice document you send to the customer, you also create the related quantity and value entries in [!INCLUDE[prod_short](includes/prod_short.md)].

### To create and post a sales invoice  

1. Choose the ![Lightbulb that opens the Tell Me feature 20.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  

2. Select **New** to create a new entry.

3. In the **Customer** field, enter the name of an existing customer.

4. Fill in the remaining fields on the **Sales Invoice** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

5. On the **Lines** FastTab, in the **Type** field, select what type of product, charge, or transaction that you will post for the customer with the sales line.

6. In the **No.** field, select a record to post according to the value in the **Type** field.

7. In the **Quantity** field, enter how many units of the product, charge, or transaction that the line will record for the customer.  

8. If you want to give a discount, enter a percentage in the **Line Discount %** field. The value in the **Line Amount** field updates accordingly.  

9. Repeat steps 5 through 8 for every product or charge that you want to invoice the customer for.  

10. In the **Invoice Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field.

11. When the sales invoice lines are completed, choose the **Post and Send** action.  

For more information and additional things you can do when creating customer sales invoices, see [Invoice Sales](sales-how-invoice-sales.md)

## Related information

[Business Central Quick Starts](quick-start-business-central.md)  
[Sales Overview](sales-manage-sales.md)  
[Sell Products with a Customer Sales Order](sales-how-sell-products.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
