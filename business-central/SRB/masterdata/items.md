---
title: Service commitments for items
description: You can use service commitments for items in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Service commitments for items

You can set up items so that when they're used in a sales document, they either bring additional service commitments with them or they represent service commitments themselves. The setting for this can be made via the **Service Commitment Option** field on the **Prices and Sales** FastTab. 

The following table describes the available options.

|Option|Meaning|
|--|--|
|Sales without Service Commitment| The item is for sale only and not for service commitments or contracts. This is the default option. It's also used when subscription billing isn't used. <br/>For items with this setting, service objects aren't created upon delivery, and you can't create them manually.|
|Sales with Service Commitment|The item can be sold with additional service commitments. If additional service commitments are stored, these are used either automatically (**Default** is selected in the assigned service commitment package) or on request in the sales process. <br/> For items with this setting, a service object is created automatically upon delivery.
|Service Commitment Item|The item can be used in a sales document, but invoicing is done only through the contract in the form of service commitments. When a sales order line is delivered, it's set as **Invoiced**. You can select this option only if the item's **Type** is **Non-Inventory**. <br/> For items with this setting, a service object is created automatically upon delivery.
|Invoicing Item|The item is used for billing additional service commitments sold for another item. You can select this option only if the item's **Type** is **Non-Inventory**. This item can't be used on document lines. For example, on sales quotes, sales orders, sales invoice, purchase invoices, and so on. <br/> You can't create service objects for items with this setting.

## Service commitments

On the **Items** and **Item Card** pages, you can access service commitments in the **Service Commitments** FactBox. In addition to the name of the service commitment package, the FactBox also shows whether the respective service commitment package is marked as **Standard**. If an item marked as standard is used in the sales process, all the services from the corresponding service commitments packages are transferred to the sales item in the document. To learn more, go to [Sales process](../sales/sales-service-commitments.md).

Clicking on the header of the FactBox opens the **Service Commitment Packages per Item** page. The page provides an overview of all service commitment packages stored for the item, including the details in service commitment package lines. For visual assignment, the service commitment package lines for the selected package display in bold. For example, this cue is helpful if there are several service commitment packages for the item. To add a service commitment package to an item, insert in a new line. If you delete a line, the service commitments aren't available for sales orders or quotes.

Similar to the FactBox, you can also use the **Service Commitments** action to access the service commitments for items.

## Related information

