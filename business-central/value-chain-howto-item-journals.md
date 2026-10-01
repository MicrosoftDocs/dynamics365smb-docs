---
title: Sustainability value chain in item journals
description: Learn how item journals and item reclassification journals affect sustainability value chain entries and item emissions.
author: altotovi
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, carbon, CO2, CO2e, value chain, item journal, item reclassification journal, adjust emissions
ms.search.forms: Primary_40, 393, 6221
ms.date: 08/21/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Sustainability value chain in item journals

You can record changes to an item's carbon equivalent (CO2e) emissions in item journals and item reclassification journals. When you post the journal, [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability value entries for the item.

## Before you start

On the **Sustainability Setup** page, select **Enable Value Chain Tracking**. You can also assign a default sustainability account to each item that you want to use. Learn more in [Set up the sustainability value chain](value-chain-howto-setup.md) and [Set up default emission values](sustainability-howto-default.md).

The sustainability account must be a posting account that allows direct posting. You can't use an account category for water, waste, or discharged water. Unless the account subcategory is for renewable energy, the **Total CO2e** value must be different from zero when you post.

## Record emissions in an item journal

You can create sustainability value entries for the **Purchase**, **Positive Adjmt.**, **Sale**, and **Negative Adjmt.** entry types.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Journals**, and then select the related link.
2. Choose an item journal batch.
3. In the **Entry Type** field, choose the type of inventory change.
4. Enter the item number and quantity.
5. Review the **Sust. Account No.** and **Total CO2e** values. Change the total emission if the transaction has a different value.
6. Post the journal.

[!INCLUDE [prod_short](includes/prod_short.md)] copies the item's **Default Sust. Account** and **CO2e per Unit** values to the journal line. It calculates **Total CO2e** based on the quantity and the quantity per unit of measure.

Posting creates a sustainability value entry for each journal line that has a sustainability account. For regular items, purchase and positive adjustment entries add emissions. Sale and negative adjustment entries subtract emissions. For items marked as GHG credits, the signs are reversed.

## Record emissions in an item reclassification journal

Use an item reclassification journal when you want to transfer emissions without adding new values and keep a record of your changes.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Reclassification Journals**, and then select the related link.
2. Choose an item journal batch.
3. Enter the item number, quantity, current location, and new location.
4. Review the **Sust. Account No.** value that [!INCLUDE [prod_short](includes/prod_short.md)] copies from the item.
5. In **Total CO2e**, enter the emissions added by the movement.
6. Post the journal.

Posting creates a sustainability value entry with **Transfer** as the item ledger entry type.

## Recalculate CO2e per unit

Run the **Adjust Emissions** batch job to recalculate the average **CO2e per Unit** value on item cards from posted sustainability value entries. This task is useful after you post item journal or item reclassification journal transactions.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Adjust Emissions**, and then select the related link.
2. To limit the items that the batch job updates, set either **Item No. Filter** or **Item Category Filter**. You can't use both filters at the same time. Leave both fields blank to process all items.
3. Choose **OK**.

The batch job updates only items that have sustainability value entries. It also updates the date in the **CO2e Last Date Modified** field.

## Related information

[Sustainability value chain overview](value-chain-howto-overview.md)  
[Sustainability value chain in transfers](value-chain-howto-transfer.md)  
[Sustainability reports and analytics](sustainability-reports.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Count, adjust, and reclassify inventory](inventory-how-count-adjust-reclassify.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
