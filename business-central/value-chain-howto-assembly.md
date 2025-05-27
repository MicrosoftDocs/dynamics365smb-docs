---
title: Sustainability value chain in assembly orders
description: Learn how to work with assembly orders related to the sustainability value chain process.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, assembly
ms.search.form: 900,
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---


# Sustainability value chain in assembly orders

The requirement for enabling the use of the sustainability value chain in the assembly orders processes is that you enable the **Enable Value Chain tracking**, **Item Emissions**, and **Resource Emissions** fields on the **Sustainability Setup** page.  

To do so, follow next steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link.
2. Check whether the basic setup already exists. If it doesn't, follow [these instructions](finance-sustainability-setup.md) to set it up.  
3. On the **Procurement** FastTab, fill in the following fields:
   1. **Enable Value Chain tracking** to enable sustainability value entries postings through value chain operations and the visibility of these fields in operational documents and journals.
   2. **Item Emissions** to enable a default sustainability account and emissions on the **Item Card** page.
   3. **Resource Emissions** to enable default a sustainability account and emissions on the **Resource Card** page.
5. Close the page.

## Working with assembly orders  

To learn more about how to work with assembly orders, go to [Assembly Management](assembly-assemble-items.md). However, the connection of assembly orders with the sustainability value chain is demonstrated two steps:

- Tracking emissions for items and resources consumed during the assembly process.
- Transfer the total emission values to the assembly items.  

To use an assembly order in the sustainability value chain process, add CO2e (carbon equivalent) emissions in all lines. For each line, fill in the **Total CO2e** field with the total emission for the quantity related to the item or resource on the assembly order line.

To do so, follow next steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly orders**, and then select the related link.
2. Create a new assembly order, or open the existing order you want to use. To learn more about assembly orders, go to [To assemble an item to stock](assembly-how-to-assemble-items.md#to-assemble-an-item-to-stock).
3. If your items and resources in the assembly order lines already have default sustainability accounts and emissions, the values are added in the **Sustainability Account No.** and **Total CO2e** fields. You can change these values if you want.
4. If you didn't have these default values for your items or resources, choose a **Sustainability Account No.**, and then fill in the **Total CO2e** field with the total emission amount for this line. The amount is for the whole quantity, regardless how many items are assembled at this moment. [!INCLUDE [prod_short](includes/prod_short.md)] recalculates the value for the specific consumption.

> [!NOTE]
> Although the total CO2e emission amount displays for each line, there's a field called **CO2e per Unit**. Its value comes from the item or resource, and is used for calculations. However, if you change the **Total CO2e** field on the line, the **CO2e per Unit** recalculates based on the total emission and quantity for that line.  

5. On the **Posting** FastTab, **CO2e per Unit** and **Total CO2e** fields show the total calculated emission per unit of the assembled item after posting.
6. If the values are correct, choose the **Post** action to post the order.
7. After you post the order, if your **Quantity to Assemble** was less than the **Quantity**, the **Posted Total CO2e** fields on the header and lines update with the belonging total CO2e emission.  

After you post the order, you can open the **Posted Assembly Order** page to find the **Total CO2e** field on the **Posting** FastTab. The value in the **CO2e per Unit** field is also updated for the newly assembled item. You can also check the result by opening the **Item Card** page for the item used as the assembled item to verify that the **CO2e per Unit** field updated based on the values from the posted assembly order.

## Related information

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
