---
title: Set Up Shipment Methods
description: You can set up a code for each of your offered shipment methods, and enter information about them.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: incoterms
ms.search.form: 11, 130
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up Shipment Methods

Shipment methods often depend on the items, the customers, and the vendors. For example, if the customer lives on an island, they can choose to have items always shipped by air or always by sea. Some customers may require next day delivery. Some may want to pick up the order. On the customer and vendor cards, you can specify what sort of delivery is desired.

You set up the description and code for each shipment method on the **Shipment Methods** page. For example, you can set up the code FOB, and enter Free on Board in the **Description** field. You can then enter the code in **Shipment Method Code** fields elsewhere in the system, such as on a customer card. Then when you create new orders, invoices, credit memos, and so on, the system will enter the description represented by the code. You can change it on the document as needed.

## To set up a shipment method

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Shipment Methods**, and then choose the related link.
2. On the **Shipment Methods** page, choose the **New** action.
3. On the new line, specify a code and description for the shipment method.

> [!TIP]
> If you use Incoterms, set up shipment methods to represent the relevant Incoterms rules.  

## Related information

[Set Up Shipping Agents](sales-how-to-set-up-shipping-agents.md)  
[Track Packages](sales-how-track-packages.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Incoterms on iccwbo.org](https://iccwbo.org/resources-for-business/incoterms-rules)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
