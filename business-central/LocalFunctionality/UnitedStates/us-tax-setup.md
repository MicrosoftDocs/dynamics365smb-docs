---
title: Basic Tax Setup in the US Version
description: Learn how to set basic tax data and apply default accounts for posting calculated tax information.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: install-set-up-deploy
ms.search.keywords: tax, setup
ms.search.form: 485
ms.date: 10/19/2026
ms.author: bholtorf
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Basic tax setup in the US version

Use the **Tax Setup** page to define basic tax information in [!INCLUDE [prod_short](../../includes/prod_short.md)]. Specify the tax group for nontaxable transactions and the default accounts for posting calculated tax. Then configure tax jurisdictions, tax areas, and tax details to match your company's requirements. Learn more in [Sales tax in the US version](us-sales-tax.md).

> [!TIP]
> [!INCLUDE [prod_short](../../includes/prod_short.md)] is available in countries/regions that use value-added tax (VAT). For information about how to set up and report VAT in your country/region, see the articles in the [Local Functionality](../../about-localization.md) section.

## Set up taxes

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Setup**, then choose the related link.
1. On the **Tax Setup** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]
   * Specify the **Non-Taxable Tax Group Code** to identify the tax group for nontaxable transactions.
   * On the **Default Accounts** FastTab, specify **Tax Account (Sales)**, **Tax Account (Purchases)**, and **Reverse Charge (Purchases)** as appropriate for your transactions. These settings provide default general ledger (G/L) accounts. Tax jurisdictions also have their own tax account settings. Learn more about how to set up or edit G/L accounts in [Set Up or Change the Chart of Accounts](../../finance-setup-chart-accounts.md).

> [!TIP]
> If you are in the US, we recommend running the **Tax Setup** together with the **Set Up Sales Tax** assisted guide. Learn more about the guide and other important pages and fields to set up in [Sales Tax in the US](us-sales-tax.md).

## Related information

- [United States Local Functionality](united-states-local-functionality.md)  
- [Finance](../../finance.md)  
- [Setting Up Finance](../../finance.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
