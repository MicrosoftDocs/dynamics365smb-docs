---
title: Add extended text
description: You can add extra lines to extend the standard text that describes an item, a G/L account, and other data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 391, 30
ms.date: 08/21/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Add extended text

Use extended texts to communicate additional information for items, stock-keeping units, general ledger accounts, project planning lines, and resources. For example, the extra details might be about special prices, terms, or handling instructions. Provide the information by adding extra lines as extended text. You can also set up conditions for use of the extra lines.  

The following section describes how to add extended text to a description of an item. The same steps apply to stock-keeping units, general ledger accounts, project planning lines, and resources.  

## To define extended text for a description

1. Open the card for an item that you want to add extended text to, and then choose the **Extended Text** action.
2. Fill in the **Code** and **Description** fields.
3. Choose the **New**.
4. Fill in the **Language Code** field, or turn on the **All Language Codes** toggle if you use language codes.
5. Fill in the **Starting Date** and **Ending Date** fields if you want to limit the dates on which the extended text is used.
6. On the **Lines** FastTab, in the **Text** field, enter the extended text.
7. On the **Sales**, **Purchases**, and **Service** FastTabs, turn on the toggles for the documents you want to include the extended text.
8. Close the page.

You can now add this extended text to documents. The following procedure explains how to add extended text to a sales order, but the same steps apply to any other document that you specified for the extended text.  

## To add an extended item text on a sales order line

1. Open a sales order that has a sales line for an item with extended text. To learn more, go to [Sell Products](sales-how-sell-products.md).
2. Select the line, and then choose the **Insert Ext. Text** action.

## Related information

[Setting Up Inventory](inventory-setup-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
