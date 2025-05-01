---
title: Subscription lines for items
description: You can use subscription lines for items in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Subscription lines for items

You can set up items so that when they're used in a sales document, they either bring additional subscription lines with them or they represent subscription lines themselves. The setting for this can be made via the **Subscription Line Option** field on the **Prices and Sales** FastTab. 

The following table describes the available options.

|Option|Meaning|
|--|--|
|Sales without Subscription Line| The item is for sale only and not for subscription lines or contracts. This is the default option. It's also used when subscription billing isn't used. <br/>For items with this setting, service objects aren't created upon delivery, and you can't create them manually.|
|Sales with Subscription Line|The item can be sold with additional subscription lines. If additional subscription lines are stored, these are used either automatically (**Default** is selected in the assigned subscription line package) or on request in the sales process. <br/> For items with this setting, a service object is created automatically upon delivery.
|Subscription Line Item|The item can be used in a sales document, but invoicing is done only through the contract in the form of subscription lines. When a sales order line is delivered, it's set as **Invoiced**. You can select this option only if the item's **Type** is **Non-Inventory**. <br/> For items with this setting, a service object is created automatically upon delivery.
|Invoicing Item|The item is used for billing additional subscription lines sold for another item. You can select this option only if the item's **Type** is **Non-Inventory**. This item can't be used on document lines. For example, on sales quotes, sales orders, sales invoice, purchase invoices, and so on. <br/> You can't create service objects for items with this setting.

## Subscription lines

On the **Items** and **Item Card** pages, you can access subscription lines in the **Subscription Lines** FactBox. In addition to the name of the subscription line package, the FactBox also shows whether the respective subscription line package is marked as **Standard**. If an item marked as standard is used in the sales process, all the services from the corresponding subscription line packages are transferred to the sales item in the document. To learn more, go to [Sales process](../sales/sales-subscription-lines.md).

Clicking on the header of the FactBox opens the **Subscription Line Packages per Item** page. The page provides an overview of all subscription line packages stored for the item, including the details in subscription line package lines. For visual assignment, the subscription line package lines for the selected package display in bold. For example, this cue is helpful if there are several subscription line packages for the item. To add a subscription line package to an item, insert in a new line. If you delete a line, the subscription lines aren't available for sales orders or quotes.

Similar to the FactBox, you can also use the **Subscription Lines** action to access the subscription lines for items.

## See also

