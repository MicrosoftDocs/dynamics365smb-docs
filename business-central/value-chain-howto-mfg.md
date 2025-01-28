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

> [!IMPORTANT]
> As sustainability value chain works only with the carbon equivalent (CO2e), before you start you must configure the [**Carbon Equivalent Factors** in the **Emission Fees Page**](value-chain-howto-setup.md#emission-fees).  

## Working with production BOM

To learn how to work with the **Production BOM**, read [how to create production BOM](production-how-to-create-production-boms.md). In this article we explain only impact of CO2e emissions to the **Production BOM**.  

If you set up default emissions for items you plan to use in the **Production BOM** lines, the system will automatically populate the **CO2e per Unit** for each line when you create a new production BOM. However, if you have already created a **Production BOM** before configuring emissions for items, or if you have updated the emission values for items, you can simply run the **Calculate CO2e** action. The system will then update all **CO2e per Unit** values using the latest emission details from the items. You can even run the **Calculate CO2e** action from the **Production BOMs** page to update all production BOMs with the latest emissions.   

## Working with routings

To learn how to work with the **Routing**, read [how to create routing with production operations](production-how-to-create-routings.md). In this article we explain only impact of CO2e emissions to the **Routing**.

If you set up default emissions for work or machine centers you plan to use in the **Routing** lines, the system will automatically populate the **CO2e per Unit** for each line when you create a new routing. However, if you have already created a **Routing** before configuring emissions for work or machine centers, or if you have updated the emission values for them, you can simply run the **Calculate CO2e** action. The system will then update all **CO2e per Unit** values using the latest emission details from the work or machine centers you are using.   

## Working with production orders  

To learn how to work with the production orders read this instruction [about production orders](production-about-production-orders.md) and [how to create production order](production-how-to-create-production-orders.md). However, the connection of production orders with the sustainability value chain is demonstrated by tracking the emissions for items and work or machine centers consumed during the production process and transferring these total emission values to the produced items - finished goods.  

To use **Production Order** in the sustainability value chain process, you need to add CO2e (carbon equivalent) emission in all posted entries through journals used in production process. So, you can start with the process using the **Released Production Order**. To use sustainability value chain functionality in production orders, all items (raw materials) and work/machine centers you want to use must have preconfigured **Sustainability Account No.** and emissions.  

To do so, follow next steps:   

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released production orders**, and then select the related link.
2. Create new production order.   
3. Follow the instructions [how to create production order](production-how-to-create-production-orders.md).   
4. Run the **Refresh Production Order** action to calculate values for the line.  
5. After refresking the order, value in the **Total CO2e** field ahs been updated based on emissions in the **Production BOM** and **Routing** you used for the production items.   

When you refresh the **Production Order**, values from the **Production BOM** and **Routing** are transfered to the **Prod. Order Components** and **Prod. Order Routing** for the production order you are using. So, if you make some changes in the initial **Production BOM** and **Routing** it will not affect production order you refreshed previously.  

To check these values, run the **Routing** or **Components** actions from the production order lines to see emissions.  

> [!NOTE]
> Although the **Total CO2e** emission amount is displayed for each line in the **Prod. Order Components** and **Prod. Order Routing** pages, there is a field in the table called **CO2e per Unit** that is derived from the **Item**, **Work Center** or **Machine Center** card and is used for calculations. However, if the user modifies the **Total CO2e** field on the line, the **CO2e per Unit** will be recalculated based on the total emission and quantity for that line.  

### Posting transactions related to production order  

To post all transactions related to the production order and also record the emissions, you can choose one of the journals:  

- Production Journal
- Consumption Jornal
- Output Journal

#### Production journal  

Production journal combines the functions of the separate consumption journal and output journals into one journal. The combined journal is accessed directly from a released production order and you can read here [how to register consumption and output for one released production order line](production-how-to-register-consumption-and-output.md). Releated to emissions, you need to be sure all lines have populated the **CO2e per Unit** field. Every time when you post the journal, system will create **Sustainability Value Entries**.  

You can access to these entries from the **Release Production Order** running the **Sustainability Value Entries** action.  

#### Consumption journal 

You can find details [here about using consumption journals](production-how-to-post-consumption.md) It is important to know that all emissions will be updated posting these journals for all consumption transactions. When you post the journal system will create **Sustainability Value Entries** with the **Consumption** as the **Item Ledger Entry Type**.  

#### Output journal   

You can find details [here about using output journals](production-how-to-post-output-quantity.md) It is important to know that all emissions will be updated posting these journals for all output transactions based on routings you used. When you post the journal system will create **Sustainability Value Entries** with the **Output** as the **Item Ledger Entry Type** for the your finished good production, but also create transactions for work or machine centers you used related to the **Capacity Ledger Entry**.  

### Finishing production order   

When you finish production order, system will finally update the value of you produced item and update the **CO2e per Unit** field on the produced **Item** card.   

> [!NOTE]
> The system will calculate the **CO2e per Unit** for the produced item by summing the total emissions from all consumed items and executed operations (work and machine centers), and then dividing by the total output quantity.  


## See also  

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)   
[Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
