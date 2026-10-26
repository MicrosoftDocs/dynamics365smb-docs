---
title: Sales tax in the US Version
description: Understand the setup of sales tax, including how tax groups, tax areas (such as states, counties, cities, and localities), tax jurisdictions, and tax details work.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: local, sales tax, tax group
ms.search.form: 315, 466, 467, 468, 469, 10015, 10016, 10101
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Sales tax in the US version

[!INCLUDE [sales-tax](../includes/CAMXUS/sales-tax-setup.md)]

If you set up new tax areas and tax jurisdictions, you must make sure that you fill in the fields correctly. In the United States, states, counties, cities, and localities can charge sales tax. Companies collect and remit sales tax to these government authorities for products sold to end users. Sales tax can also be charged to existing sales tax. For example, tax can be calculated on a sales invoice amount that already includes the tax from other jurisdictions.  

## Tax details

The **Tax Details** page defines tax rates for combinations of tax jurisdictions, tax groups, tax types, and effective dates. For each tax jurisdiction, set up one tax group for normal sales tax. Also, set up another tax group for items or services that aren't taxed. Additionally, create a tax group for every type of item or service that is handled with a different sales tax rate in that jurisdiction. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

For each tax detail, specify the **Tax Type** and **Effective Date**, and enter the applicable rate in **Tax Below Maximum**. Use **Tax Above Maximum** when a different rate applies above the maximum amount. For a nontaxable tax group, set the applicable rates to zero.

Work with your tax advisor to determine where you must collect sales tax and which rates and effective dates apply. Don't assume that a sale is exempt because you don't have a physical location in the customer's state.

> [!TIP]
> If you have more than one company in the same database, you can use the **Copy Tax Setup** task to copy tax settings between them. The feature ensures that the tax information is identical throughout the companies.
>
> 1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Copy Tax Setup**, then choose the related link.
> 1. Select the company from which you want to copy the tax data, which setup information to copy, and choose **OK**.

## Related information

- [Set Up Basic Tax Information](us-tax-setup.md)  
- [Set Up Sales Tax - Watch a Video](https://youtu.be/AfD-D9uf6po)  
- [United States Local Functionality](united-states-local-functionality.md)  
- [Finance](../../finance.md)  
- [Setting Up Finance](../../finance.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
