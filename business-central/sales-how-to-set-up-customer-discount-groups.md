---
title: Set up customer discount groups
description: Learn how to set up customer discount groups and create sales line discounts for those groups.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 07/05/2024
ms.author: bholtorf
ms.reviewer: bholtorf
---
# Set up customer discount groups

You can define sales line discounts for a group of customers instead of applying them individually.

**Customer Discount Groups** are similar to [customer price groups](sales-how-to-set-up-customer-price-groups.md), but can be combined with Item Discount Groups to quickly set line discounts to many items for selected customers.

## Create sales line discounts for a customer group

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Disc. Groups**, and then choose the related link.
2. On the **Customer Disc. Groups** page, select **New** to create a new discount group and give it a name under the **Code** column and add a description.
3. Choose the **Sales Line Discounts** action.
4. Fill in the **Sales Code** column with the discount group created on the previous page.
5. Fill in the fields on the lines with the **Type** (Item or Item Discount Group), **Code**, **Unit of Measure Code**, and the **Line Discount %**.
6. If the customer group needs to purchase a minimum quantity in order to gain the discount, fill in the **Minimum Quantity** field.
7. If necessary, enter the **Starting Date** and **Ending Date** for the discount group.
8. If relevant, you can also specify the **Currency Code** or **Variant Code** after [personalizing the columns](ui-personalization-user.md).

Repeat steps 4 through 8 for each item or item discount group you want to create a sales line discount for.

## Assign a customer to a discount group

After you set up the customer discount groups, you can enter the customer discount group codes on the customer cards.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the **Customer Card** for a customer you want to be part of a customer discount group.
3. On the **Invoicing** FastTab, in the **Customer Disc. Group** field, select the group code.

## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Recording Special Sales Prices and Discounts](sales-how-record-sales-price-discount-payment-agreements.md)  
[Setting Up Customer Price Groups](sales-how-to-set-up-customer-price-groups.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
