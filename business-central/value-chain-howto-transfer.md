---
title: Sustainability Value Chain in Transfers
description: Learn how to work with transfer order related to their impact to the sustainability value chain process.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, transfer
ms.search.form: 5740
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---


# Sustainability Value Chain in Transfers    

Preprequisite for enabling usage of sustainability value chain in the location transfer processes is to have enabled the **Enable Value Chain tracking** field in the **Sustainability Setup**.  

To do so, follow next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link. 
2. First check if the basic setup already exists. If it doesn't exist, follow [this intstruction](finance-sustainability-setup.md) to setup it.  
3. On the **Procurement** FastTab, select the **Enable Value Chain tracking** field.   
5. Close the page.   

## Working with transfer orders  

To learn how to work with the transfer orders read this instruction [how to transfer items between localitions with **Transfer Orders**](inventory-how-transfer-between-locations.md#to-transfer-items-with-a-transfer-order).  

To use **Transfer Order** in the sustainability value chain process, you need to add CO2e (carbon equivalent) emission produced in this transfer process (i.e. this is transfer done by trucks...). You can do it for each of lines using the **Total CO2e** field where you will add total emission for the quantity related to the item in this transfer order line.   

When you post the **Transfer Order**, you can find entries related to the transfer only in the **Posted Transfer Shipment**. To find these entries, follow next steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted transfer shipments**, and then select the related link.
2. Open the **Posted Transfer Shipment** you want to check and run the **Find entries** action.   
3. On the **Find entries** page find the **Sustainability Value Entry** and click to open the page with the transactions related to this document. 
4. Close the page.   

> [!NOTE]
> Whether or not you select the **Direct Transfer** field on the **Transfer Order** header, the system will create new **Sustainability Value Entries** only for transactions related to the **Posted Transfer Shipment**.

This transactions will increase the **CO2e per Unit** for transferred items using the average method.  


## See also  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)   
[Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
