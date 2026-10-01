---
title: Track Fixed Asset Emissions in the Value Chain
description: Learn how to track CO2e emissions when you acquire, reclassify, sell, or dispose of fixed assets in Business Central.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, CO2e, value chain, fixed asset, acquisition, reclassification, disposal
ms.search.form: Primary_5600, 5604, 5628, 5629, 5636
ms.date: 08/27/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Track fixed asset emissions in the sustainability value chain

You can track the carbon dioxide equivalent (CO2e) emissions that are embedded in a fixed asset. [!INCLUDE [prod_short](includes/prod_short.md)] records the emissions when you acquire the asset. The emissions follow the asset when you reclassify, sell, or dispose of it.

## Set up fixed asset emissions

Before you start, complete the [sustainability value chain setup](value-chain-howto-setup.md). When you turn on **Enable Value Chain Tracking**, [!INCLUDE [prod_short](includes/prod_short.md)] also turns on **Use Emissions In Purchase Documents** and **Fixed Asset Emissions**.

Set up the carbon equivalent factors for the gases that you track. Learn more in [Set up emission fees](value-chain-howto-setup.md#emission-fees).

To specify default emissions for a fixed asset, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then select the related link.
2. Open the fixed asset.
3. On the **Sustainability** FastTab, select a **Default Sust. Account**.
4. Enter values in the **Default CO2 Emission**, **Default CH4 Emission**, and **Default N2O Emission** fields.

The default account and emissions are copied to purchase lines for the fixed asset. You can change the values on the document before you post it.

## Track emissions when you acquire a fixed asset

You can record fixed asset emissions from a purchase document or a fixed asset journal.

### Acquire a fixed asset from a purchase document

When you select a fixed asset on a purchase line, [!INCLUDE [prod_short](includes/prod_short.md)] copies the default sustainability account and emissions from the **Fixed Asset Card** page. It calculates **Total CO2e** from the CO2, CH4, and N2O emissions and their carbon equivalent factors. The calculation includes the quantity on the line.

When you post a purchase invoice, [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability ledger entries. It also creates a sustainability value entry with **Fixed Asset** as the type. If you post a corrective purchase credit memo, [!INCLUDE [prod_short](includes/prod_short.md)] creates negative entries.

Learn more about acquiring assets from purchase documents in [Acquire fixed assets](fa-how-acquire.md#add-a-fixed-asset-from-a-purchase-order-or-invoice).

### Acquire a fixed asset from a journal

The **Fixed Asset Journal** and **Fixed Asset G/L Journal** pages include the **Sust. Account No.** and **Total CO2e** fields.

You can enter sustainability data only when **FA Posting Type** is **Acquisition Cost**. Enter a nonzero value in **Total CO2e** when the selected sustainability account requires emissions. You can't add sustainability data to other fixed asset posting types.

## Reclassify fixed asset emissions

<!--When you reclassify an acquisition cost, its CO2e emissions follow the same percentage. For example, if you enter **25** in **Reclassify Acq. Cost %**, 25 percent of the acquisition CO2e transfers to the new fixed asset.-->

Specify **Sust. Account No.** for the original fixed asset and **New Sust. Account No.** for the new fixed asset. If you transfer to one fixed asset, the new account can be the same as the original account. If you split the asset across multiple fixed assets, enter the new account on each reclassification line.

Learn more about the reclassification process in [Transfer, split, or combine fixed assets](fa-how-trans-split-combine.md).

## Depreciate a fixed asset with emissions

Depreciation doesn't create or transfer sustainability emissions. You can't enter a sustainability account or CO2e amount on a depreciation journal line. The emissions remain associated with the fixed asset acquisition entries.

Learn more in [Depreciate or amortize fixed assets](fa-how-depreciate-amortize.md).

## Sell or dispose of a fixed asset with emissions

When you select a fixed asset on a sales line, [!INCLUDE [prod_short](includes/prod_short.md)] copies its default sustainability account. The **Total CO2e** value comes from the asset's nonreversed acquisition entries for the selected depreciation book.

When you post the sale, the disposal entries carry the asset's CO2e. You can review the CO2e values for **Proceeds on Disposal**, **Gain/Loss**, and the disposal acquisition-cost entry.

Learn more about disposal posting in [Dispose of or retire fixed assets](fa-how-dispose-retire.md).

## Review fixed asset emissions

The **FA Ledger Entries** page and the fixed asset ledger preview show the **Sust. Account No.** and **Total CO2e** for each applicable entry. Use these fields to trace the emissions through acquisition, reclassification, and disposal.

You can also review the corresponding entries on the **Sustainability Ledger Entries** and **Sustainability Value Entries** pages.

## Related information

- [Sustainability value chain overview](value-chain-howto-overview.md)
- [Sustainability value chain setup](value-chain-howto-setup.md)
- [Sustainability value chain in purchasing](value-chain-howto-purchase.md)
- [Sustainability value chain in sales](value-chain-howto-sales.md)
- [Fixed assets](fa-manage.md)
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
