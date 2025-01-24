---
title: Sustainability Value Chain in Purchase
description: Learn about understanding how value chain process starts with the purchase process.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain
ms.search.form: 50, 51
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Sustainability Value Chain in Purchase   

Preprequisite for enabling usage of sustainability value chain in purchase process is to have enabled the following fields in the **Sustainability Setup**: 

- **Enable Value Chain tracking** to enable value chain capabilities in all processes  
- **Use Emissions In Purchase Documents** to enable emission fields in the purchase document lines 

To do so, follow next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link. 
2. Firt check if the basic setup already exists. If it doesn't exist, follow [this intstruction](finance-sustainability-setup.md) to setup it.  
3. On the **Procurement** FastTab, configure the required fields that are related to the Sustainability Value Chain functionallity.  
   1. Select the **Use Emissions In Purchase Documents** field 
   2. Select the **Enable Value Chain tracking**   
5. Close the page.   

## Working with Purchase Documents

To learn how to work with the purchase documents related to sustainability read this instruction [how to record emissions with the purchase documents](finance-sustainability-journal.md#purchase-documents).  

If you enabled value chain in the **Sustainability Setup** and properly created purchase document with the **Sustainability Accounts** and emissions (minimum one emission), system will automatically start the sustainability value chain and post details to the **Sustainability Value Entries** table.  

> [!NOTE]
> Only items can create the **Sustainability Value Entry**. In this release Business Central does not support emissions from the **Item Charges**.   

> [!IMPORTANT]
> As sustainability value chain works only with the carbon equivalent (CO2e), before you start you must configure the [**Carbon Equivalent Factors** in the **Emission Fees Page**](value-chain-howto-setup.md#emission-fees).  

After posting the purchase documents, you can find results in the **Posted Purchase Invoice** or **Posted Purchase Credit Memo**. To see results, run the **Find entries** action. In the list of entries you can find the **Sustainability Value Entry** and you can click on this table to open list of value chain transactions related to your purchase documents.  

Additionally, when you post the document, system will update the **CO2e per Unit** field for all items you had in your purchase document. If this purchase document was the first for this item, system will update value from document, but if you had documents earlier, system will use average model for calculation **CO2e per Unit** for your item. 

## See also  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)   
[Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
