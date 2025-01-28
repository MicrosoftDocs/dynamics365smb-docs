---
title: Sustainability Value Chain in Assembly Orders
description: Learn how to work with assembly orders related to the sustainability value chain process.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, assembly
ms.search.form: 900
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---


# Sustainability Value Chain in Assembly Orders   

The preprequisite for enabling usage of sustainability value chain in the assembly orders processes is to have enabled the **Enable Value Chain tracking**, **Item Emissions** and **Resource Emissions** fields in the **Sustainability Setup**.  

To do so, follow next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link. 
2. First check if the basic setup already exists. If it doesn't exist, follow [this intstruction](finance-sustainability-setup.md) to setup it.  
3. On the **Procurement** FastTab, select the following fields:
   1. **Enable Value Chain tracking** to enable sustainability value entries postings through value chain operations and the visibility of these fields in operational documents and journals.
   2. **Item Emissions** to enable default sustainability account and emissions on the **Item** card.
   3. **Resource Emissions** to enable default sustainability account and emissions on the **Resource** card.
5. Close the page.   

## Working with assembly orders  

To learn how to work with the assembly orders read this instruction [about assembly management](assembly-assemble-items.md). However, the connection of assembly orders with the sustainability value chain is demonstrated by tracking the emissions for items and resources consumed during the assembly process and transferring these total emission values to the assembly items.  

To use **Assembly Order** in the sustainability value chain process, you need to add CO2e (carbon equivalent) emission in all lines. You can do it for each of lines using the **Total CO2e** field where you will add total emission for the quantity related to the **Item** or **Resource** in this assembly order line.   

To do so, follow next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly orders**, and then select the related link.
2. Create new assembly order or open the existing one you want to use.   
3. Follow these instructions to [create new assembly order](assembly-how-to-assemble-items.md#to-assemble-an-item-to-stock).   
4. If your items and resources in the assembly order lines had already configured default sustainability accounts and emissions, these values will be added in the **Sustainability Account No.** and **Total CO2e** fields. You can change these values if you want. 
5. If you didn't have these default values for your items or resources, you first need to choose the right **Sustainability Account No.** and after that to populate the **Total CO2e** field with the total emission amount for this line (for the whole quantity, regardless how many items will be assembled in this moment as system will recalculate for the specific consumption). 

> [!NOTE]
> Although the total CO2e emission amount is displayed for each line, there is a field in the table called **CO2e per Unit** that is derived from the **Item** or **Resource** card and is used for calculations. However, if the user modifies the **Total CO2e** field on the line, the **CO2e per Unit** will be recalculated based on the total emission and quantity for that line.  

6. Look at the fields **CO2e per Unit** and **Total CO2e** on the **Posting** FastTab to see total calculated emission as well as per unit of the assembled item after posting. 
7. If values are correct, you can run the **Post** action to post the order.   
8. After posting the order, if you **Quantity to Assemble** was less than **Quantity**, the **Posted Total CO2e** fields on header and lines will be updated with the belonging total CO2e emission.  

After posting the order, you can open the **Posted Assembly Order** to find the **Total CO2e** field for the posted document on the **Posting** FastTab. You will also see the updated value in the **CO2e per Unit** field for the newly assembled item. Additionally, you can check the result by opening the **Item** card used as the assembled item to see that the **CO2e per Unit** on the **Sustainability** FastTab has been updated based on the values from the posted assembly order.


## See also  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)   
[Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
