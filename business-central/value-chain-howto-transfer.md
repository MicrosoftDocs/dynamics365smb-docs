---
title: Sustainability value chain in transfers
description: Learn how to work with transfer orders and their effect on the sustainability value chain process.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, transfer
ms.search.form: 5740,
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---


# Sustainability value chain in transfers

To use the sustainability value chain with transfer orders, you must enable the **Enable Value Chain Tracking** field on the **Sustainability Setup** page.  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link.
2. Check whether the basic setup already exists. If it doesn't, follow [these instructions](finance-sustainability-setup.md) to set it up.  
3. On the **Procurement** FastTab, select the **Enable Value Chain tracking** field.
4. Close the page.

## Work with transfer orders  

To learn how to work with transfer orders, go to [To transfer items with a transfer order](inventory-how-transfer-between-locations.md#to-transfer-items-with-a-transfer-order).  

To use transfer orders in the sustainability value chain process, you must add the carbon equivalent (CO2e) emission that you produce in the transfer process. For example, if you transfer goods by truck. You can add it in the **Total CO2e** field for each line on a transfer order. The value is the total emissions for the item quantities on the lines.

After you post a transfer order, you can find entries related to the transfer on the **Posted Transfer Shipment** page. To find the entries, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted transfer shipments**, and then select the related link.
2. Open the **Posted Transfer Shipment** you want to check, and then choose the **Find entries** action.
3. On the **Find entries** page, choose **Sustainability Value Entry** to review the transactions related to this document.
4. Close the page.

> [!NOTE]
> Regardless of whether you select the **Direct Transfer** field on the **Transfer Order** page, [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability value entries only for transactions related to the posted transfer shipment. The transactions increase the **CO2e per Unit** value for transferred items using the average method.  

## Related information  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
