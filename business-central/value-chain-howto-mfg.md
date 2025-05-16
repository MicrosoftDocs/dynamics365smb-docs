---
title: Sustainability value chain in production
description: Learn how to work with production orders related to the sustainability value chain process, but also with other elements related to manufacturing.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain, production, manufacturing, BOM, routing
ms.search.form: 5510, 99000766, 99000786, 99000817, 99000818, 99000831
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---


# Sustainability value chain in production

The requirement for enabling the sustainability value chain in manufacturing processes is to enable the **Enable Value Chain tracking**, **Item Emissions**, and **Work/Machine Center Emissions** fields on the **Sustainability Setup** page.  

To do so, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link.
2. Check whether the basic setup already exists. If it doesn't, follow [these instructions](finance-sustainability-setup.md) to set it up.  
3. On the **Procurement** FastTab, fill in the following fields:
   1. **Enable Value Chain tracking** to enable sustainability value entry posting through value chain operations and the visibility of these fields on operational documents and journals.
   2. **Item Emissions** to enable a default sustainability account and emissions on the **Item Card** page.  
   3. **Work/Machine Center Emissions** to enable default sustainability accounts and emissions on the **Work Center** and **Machine Center** pages.  
4. Close the page.

> [!IMPORTANT]
> Because the sustainability value chain works only with the carbon equivalent (CO2e), before you start, configure the **Carbon Equivalent Factors** on the **Emission Fees** page. To learn more, go to [Emission fees](value-chain-howto-setup.md#emission-fees).  

## Working with a production BOM

To learn more about how to work with the **Production BOM**, go to [How to create a production BOM](production-how-to-create-production-boms.md). This article only covers the effect of CO2e emissions on production BOMs.  

If you set up default emissions for items you plan to use on production BOM lines, [!INCLUDE [prod_short](includes/prod_short.md)] automatically fills in the **CO2e per Unit** field for each line when you create a new production BOM. However, if you created a production BOM before you configured emissions for items, or if you updated the emission values for items, you can run the **Calculate CO2e** action. [!INCLUDE [prod_short](includes/prod_short.md)] updates all **CO2e per Unit** values using the latest emission details from the items. You can even run the **Calculate CO2e** action from the **Production BOMs** page to update all production BOMs with the latest emissions.

## Working with routings

To learn more about how to work with routes, go to [How to create a route with production operations](production-how-to-create-routings.md). This article only explains the effect of CO2e emissions on routes.

If you set up default emissions for work or machine centers you plan to use in the **Routing** lines, [!INCLUDE [prod_short](includes/prod_short.md)] automatically fills in the **CO2e per Unit** field for each line when you create a new routing. However, if you created a routing before you configured emissions for work or machine centers, or if you updated the emission values for them, you can run the **Calculate CO2e** action. [!INCLUDE [prod_short](includes/prod_short.md)] updates all **CO2e per Unit** values using the latest emission details from the work or machine centers.

## Working with production orders  

To learn more about how to work with production orders, go to [About production orders](production-about-production-orders.md) and [How to create production orders](production-how-to-create-production-orders.md). However, the connection of production orders with the sustainability value chain is:

- Tracking the emissions for items and work or machine centers consumed during the production process.
- Transferring the total emission values to the produced items or finished goods.  

To use a production order in the sustainability value chain process, add CO2e (carbon equivalent) emissions in all posted entries through the journals you use in the production process. You can start the process using a **Released Production Order**. To use the sustainability value chain in production orders, all items (raw materials) and work or machine centers you want to use must have a **Sustainability Account No.** and emissions.  

To do so, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released production orders**, and then select the related link.
2. Create a new production order. To learn more about production orders, go to [How to create a production order](production-how-to-create-production-orders.md).
3. Run the **Refresh Production Order** action to calculate values for the line.  
4. After you refresh the order, the value in the **Total CO2e** field updates based on emissions in the production BOM and routing for the production items.

When you refresh the production order, values from the production BOM and routing transfer to the **Prod. Order Components** and **Prod. Order Routing** pages for the production order you're using. If you change the initial production BOM and routing, it doesn't affect the production order you refreshed previously.  

To check the emission values, run the **Routing** or **Components** actions from the production order lines.  

> [!NOTE]
> Although the **Total CO2e** emission amount displays for each line on the **Prod. Order Components** and **Prod. Order Routing** pages, there's a field called **CO2e per Unit**. Its value comes from the **Item**, **Work Center** or **Machine Center** pages, and is used for calculations. However, if you change the value in the **Total CO2e** field on the line, the **CO2e per Unit** recalculates based on the total emission and quantity for that line.  

### Posting transactions related to production order  

To post all transactions related to the production order and record the emissions, choose one of the following journals:  

- Production journals
- Consumption journals
- Output journals

#### Production journals  

Production journals combine the functions of the separate consumption journal and output journals into one journal. The combined journal is accessed directly from a released production order. To learn more, go to [How to register consumption and output for a released production order line](production-how-to-register-consumption-and-output.md). Related to emissions, be sure that all lines have a value in the **CO2e per Unit** field.

Every time you post the journal, [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability value entries. You can access these entries from the **Release Production Order** page by running the **Sustainability Value Entries** action.  

#### Consumption journals

To learn more about consumption journals, go to [Batch post production consumption](production-how-to-post-consumption.md). It's important to know that all emissions are updated by posting these journals for all consumption transactions. When you post a journal, [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability value entries with the **Consumption** option as the **Item Ledger Entry Type**.  

#### Output journals

To learn more about output journals, go to [Batch post output and run times](production-how-to-post-output-quantity.md). It's important to know that all emissions are updated by posting these journals for all output transactions based on the routings. When you post the journal, [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability value entries with the **Output** option as the **Item Ledger Entry Type** for the finished good production. It also creates transactions for the work or machine centers you used related to the capacity ledger entry.  

### Finish a production order

When you finish a production order, [!INCLUDE [prod_short](includes/prod_short.md)] updates the value of your produced item and the **CO2e per Unit** field on the **Item Card** page for it.

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] calculates the value in the **CO2e per Unit** field for the produced item by summing the total emissions from all consumed items and operations (work and machine centers), and then divide that by the total output quantity.  

## Related information

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
