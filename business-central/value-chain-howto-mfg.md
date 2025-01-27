---
title: Sustainability Value Chain in Production
description: Learn how to work with production orders related to the sustainability value chain process, but also with other elements related to manufacturing.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, production, manufacturing, BOM, routing
ms.search.form: 5510, 99000766, 99000786, 99000817, 99000818, 99000831
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---


# Sustainability Value Chain in Production   

The preprequisite for enabling usage of sustainability value chain in the manufacturing processes is to have enabled the **Enable Value Chain tracking**, **Item Emissions** and **Work/Machine Center Emissions** fields in the **Sustainability Setup**.  

To do so, follow next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link. 
2. First check if the basic setup already exists. If it doesn't exist, follow [this intstruction](finance-sustainability-setup.md) to setup it.  
3. On the **Procurement** FastTab, select the following fields:
   1. **Enable Value Chain tracking** to enable sustainability value entries postings through value chain operations and the visibility of these fields in operational documents and journals. 
   2. **Item Emissions** to enable default sustainability account and emissions on the **Item** card.  
   3. **Work/Machine Center Emissions** to enable default sustainability accounts and emissions on the **Work Center** and **Machine Center** cards.  
4. Close the page.   

## Working with production BOM


## Working with routings


## Working with production orders  

To learn how to work with the production orders read this instruction [about production orders](production-about-production-orders.md) and [how to create production order](production-how-to-create-production-orders.md). However, the connection of production orders with the sustainability value chain is demonstrated by tracking the emissions for items and work or machine centers consumed during the production process and transferring these total emission values to the produced items - finished goods.  

To use **Production Order** in the sustainability value chain process, you need to add CO2e (carbon equivalent) emission in all lines. You can do it for each of lines using the **Total CO2e** field where you will add total emission for the quantity related to the **Item** or **Resource** in this assembly order line.   ????????????????????????????????????????????????????????????????????????????????????????????????????????????

To do so, follow next steps:   ?????????????????????????????????????????????????????????

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly orders**, and then select the related link.
2. Create new assembly order or open the existing one you want to use.   
3. Follow these instructions to [create new assembly order](assembly-how-to-assemble-items.md#to-assemble-an-item-to-stock).   
4. If your items and resources in the assembly order lines had already configured default sustainability accounts and emissions, these values will be added in the **Sustainability Account No.** and **Total CO2e** fields. You can change these values if you want. 
5. If you didn't have these default values for your items or resources, you first need to choose the right **Sustainability Account No.** and after that to populate the **Total CO2e** field with the total emission amount for this line (for the whole quantity, regardless how many items will be assembled in this moment as system will recalculate for the specific consumption). 
6. 
