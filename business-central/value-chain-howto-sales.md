---
title: Sustainability value chain in sales
description: Learn about working with items and their embedded carbon footprints during the sales process.
author: altotovi
ms.topic: article
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

## Sales Document Layouts  

You can find **Sales Quote** and **Sales Invoice** layouts with embedded sustainability information, enabling you to include carbon‑footprint information directly on these documents. These Word-layouts extend existing invoice and quote templates by adding CO₂e information per unit and a total emissions line.  

This is the list of existing sales document and layouts related to carbon footprint:  

* **Sales Invoice**   

  * Standard ESG Sales Invoice (Word) 
  * Standard ESG Sales Invoice – Blue (Word) 

* **Sales Quote**  

  * Standard ESG Sales Quote (Word)   
  * Standard ESG Sales Quote – Blue (Word) 

Each layout is based on the corresponding standard template and include additional sustainability fields. These additions allow you to provide transparent emissions information on both quotes (pre‑sales) and invoices (post‑sales) to ensure consistency between commercial documents and sustainability reporting. The layouts work with existing CO₂e values calculated using value chain operations from the **Sustainability** module and require no additional customization.  


## Related information  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
