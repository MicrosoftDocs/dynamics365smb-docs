---
title: Sustainability value chain in purchasing
description: Learn about understanding how value chain process starts with the purchase process.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain
ms.search.form: 50, 51
ms.date: 09/27/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Sustainability value chain in purchasing

The requirement for enabling the us of the sustainability value chain in the purchase process is to enable the following fields on the **Sustainability Setup** page:

- **Enable Value Chain tracking** to enable value chain capabilities in all processes.  
- **Use Emissions In Purchase Documents** to enable emission fields in the purchase document lines.

To do so, follow next steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sustainability Setup**, and then select the related link.
2. Check whether the basic setup already exists. If it doesn't, follow [these instructions](finance-sustainability-setup.md) to set it up.  
3. On the **Procurement** FastTab, fill in the fields that are related to the sustainability value chain features.  
   1. Select the **Use Emissions In Purchase Documents** field.
   2. Select the **Enable Value Chain tracking** field.
4. Close the page.

## Work with purchase documents

To learn how to work with purchase documents in sustainability, go to [How to record emissions with purchase documents](finance-sustainability-journal.md#purchase-documents).  

If you enabled the value chain on the **Sustainability Setup** page, and created a purchase document with the **Sustainability Accounts** and emissions (minimum one emission), [!INCLUDE [prod_short](includes/prod_short.md)] automatically starts the sustainability value chain and posts details to the **Sustainability Value Entries** page.  

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] creates sustainability value entries for items and fixed assets. It doesn't support emissions from item charges. Fixed asset lines use a separate calculation and posting flow. Learn more in [Track fixed asset emissions in the sustainability value chain](value-chain-howto-fixed-assets.md).

> [!IMPORTANT]
> Because the sustainability value chain works only with the carbon equivalent (CO2e), before you start, configure carbon equivalent factors on the Emission Fees page. To learn more, go to [Emission fees](value-chain-howto-setup.md#emission-fees).  

After you post the purchase documents, the results display on the **Posted Purchase Invoice** or **Posted Purchase Credit Memo** pages. To review the results, use the **Find entries** action. In the list of entries, find the sustainability value entry. To open a list of value chain transactions related to your purchase documents, select the entry.  

When you post the document, [!INCLUDE [prod_short](includes/prod_short.md)] also updates the item's carbon information. The result depends on the **Carbon Tracking Method** on the **Item Card** page:

- For **Average**, [!INCLUDE [prod_short](includes/prod_short.md)] updates the item's **CO2e per Unit**. The first purchase establishes the value. Later purchases update it by using the average method.
- For **Specific**, [!INCLUDE [prod_short](includes/prod_short.md)] records the calculated CO2e on the item ledger entries created by the purchase. Later transactions use the CO2e from the item entries that they apply to. If the item uses lot tracking, assign the lot when you post the purchase so that later transactions can use the value for that lot.

For more information about the methods, see [Choose how to track carbon for an item](value-chain-howto-setup.md#choose-how-to-track-carbon-for-an-item).

## Related information

[Sustainability Value Chain Overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
