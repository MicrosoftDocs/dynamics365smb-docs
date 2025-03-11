---
title: Sustainability value chain in sales
description: Learn about working with items and their embedded carbon footprints during the sales process.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, sales, invoice
ms.search.form: 42, 43
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Sustainability value chain in sales

When you sell items, [!INCLUDE [prod_short](includes/prod_short.md)] updates the **CO2e per Unit** field from the **Item** card for each sales line that contains emission values. It uses the average calculation method to calculate the value.  

When you post all sales documents, the posted documents keep the **CO2e per Unit** and **Total CO2e** values for each line.

The result of posting shows as a new sustainability value entry for each line that has **Sale** as its **Item Ledger Entry Type**.

> [!NOTE]
> The **CO2e per Unit** and **Total CO2e** values aren't used in default report layouts. However, if you want to show these details when you print reports, you can create a new document report to show this data.  

## Related information  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
