---
title: Sustainability Value Chain in Sales
description: Learn about working with items and their embedded carbon footprints during the sales process.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, sales, invoice
ms.search.form: 42, 43
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---
# Sustainability Value Chain in Sales    

When you sell the items, system will update teh **CO2e per Unit** field from the **Item** card for each of the sales lines where emissions exist. This information will come from the **Item** card calculated using the average calculation method.  

When you post all sales document, posted document will keep the **CO2e per Unit** and **Total CO2e** values for each of lines.   

The result of posting will be shown as a new **Sustainability Value Entry** for each of lines with the **Sale** as an **Item Ledger Entry Type**

> [!NOTE]
> In this moment, the **CO2e per Unit** and **Total CO2e** values are not used in default report layouts, but if users want to show these details on prinouts, they can create new document report to show this data.  


## See also  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)   
[Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
