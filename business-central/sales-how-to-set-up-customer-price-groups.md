---
title: Set Up Customer Price Groups
description: Learn how to set up customer price groups and create sales prices for those groups.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: customer price groups, discounts, sales prices
ms.date: 09/30/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set Up Customer Price Groups
  
Sales prices can be made dependent on the customer groups to which you sell. These are called customer price groups.

Before you set up customer price groups, you must decide how many groups you want and which customers will belong to each group.  

## How to create sales prices for a group of customers  

When you have agreed on the prices that the group of customers will pay for certain items, you register the agreement for the individual items on the lines in the **Sales Prices** page.

### To create sales prices for a group of customers

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customer Price Groups**, and then choose the related link.  

2. Select the line for the customer price group. If a line does not already exist you can create a new line. Select **New** to create a new entity and give it a name.  
    
    For the selected line, verify the contents of the fields **Allow Line Disc.**, **Allow Invoice Disc.**, **Price Includes Tax** and **Tax Bus. Posting Gr. (Price)**. 
  
3. Select the **Navigate** action, and choose **Sales Prices**. The **Sales Prices** page opens. The **Sales Type** field will be filled in with **Customer Price Group**.  
  
4. Fill in the **Sales Code** with the sales code you selected on the previous page.  
  
5. Fill in the fields on the lines with the **Item No.**, **Unit of Measure Code**, and the agreed **Unit Price**. You can also show the **Variant Code** column and specify the **Variant Code** if there are several variants of the item.  
  
6. If the customer group needs to purchase a minimum quantity in order to gain the price agreed on, fill in the **Minimum Quantity** field.  

7. If required, enter the **Starting Date** and **Ending Date** of the price agreement.  
  
8. If relevant, you can also specify the **Currency Code**.

Repeat steps 4 through 8 for each item that you want to create a Sales Price for.

## How to enter customer price group codes on customer cards  

After you have set up the customer price groups, you can enter the customer price group codes on the customer cards.

### To enter customer price group codes on a customer card  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then choose the related link.  

2. Open the relevant **Customer Card** for a customer that you want to be part of a customer price group.  

3. On the **Invoicing** FastTab, in the **Customer Price Group** field, select the **Customer Price Group** code.  


## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Record Special Sales Prices and Discounts](sales-how-record-sales-price-discount-payment-agreements.md)  
[Setting Up Customer Discount Groups](sales-how-to-set-up-customer-discount-groups.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
