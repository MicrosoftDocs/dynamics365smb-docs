---
title: Sustainability value chain overview
description: Learn about the sustainability value chain features by using the provided information and resources.
author: altotovi
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain
ms.search.form: 
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Sustainability value chain overview

> [!IMPORTANT]
> This set of features is available as a _public preview_ in [!INCLUDE [prod_short](includes/prod_short.md)], starting from **2025 release wave 1**. Read carefully, and be sure to understand which features we currently support.  

The sustainability value chain features are a comprehensive tool designed to streamline the collection and use of data from your value chain partners. This feature empowers organizations to accurately calculate Scope 3 emissions, enabling better sustainability reporting and compliance with environmental standards.  

## Introduction to value chain for Scope 3 emissions calculation

The sustainability value chain enables you to use data you from your value chain partners to calculate your scope 3 emissions. A value chain in general is a vendor you do business with and from whom you collect inbound emission data. After you collect emissions or carbon data from your vendors, you can use the data to calculate your Scope 3 emissions in your business processes. You can also calculate other emissions for other types of item handling, such as transfers, production, and so on. These calculations help give you accurate information about embedded emissions for items you plan to sell.

The sustainability value chain helps businesses:

- Achieve a higher level of accuracy in sustainability reporting.
- Provide better communication with customers related to emissions in their products.
- Better align with regulatory demands.
- Actively contribute to reducing their environmental footprint.  

## How the system keeps sustainability value chain data

To track the sustainability value chain, record and use transactions from the **Sustainability Value Entries** page.  

> [!NOTE]
> The sustainability value chain process works only with the CO2e (carbon equivalent).

The **Sustainability Value Entry** page is an important component for managing and tracking the value of the embedded carbon footprint in items. It records all changes in the CO2e emissions of inventory items, including purchases, location transfers, production, sales, and so on. This page helps ensure accurate CO2e (carbon equivalent) valuation and provides detailed insights into the emissions effect of inventory transactions.  

> [!IMPORTANT]
> The sustainability value chain uses only the average method of CO2e emission calculation per item. An item's **CO2e per Unit** is calculated as the average **CO2e per Unit** at each point in time after a purchase.

## Available features

The following table contains articles that can help you get started with the sustainability value chain.  

| Article | Description |
|---------|-------------|
| [Value Chain Setup](value-chain-howto-setup.md) | Learn how to enable the value chain in [!INCLUDE [prod_short](includes/prod_short.md)], and the setups you must create. |
| [Default emission values](sustainability-howto-default.md) | Learn how to set up the default values for your master data. |
| [Value Chain in Purchase](value-chain-howto-purchase.md) | Learn how the value chain process starts with purchase processes. |
| [Value Chain in Transfers](value-chain-howto-transfer.md) | Learn how to work with transfer orders and their effect on the sustainability value chain process. |
| [Value Chain in Assembly process](value-chain-howto-assembly.md) | Learn how to work with assembly orders related to the sustainability value chain process. |
| [Value Chain in Production process](value-chain-howto-mfg.md) | Learn how to work with production orders related to the sustainability value chain process. The article also covers other elements related to manufacturing. |
| [Value Chain in Sales](value-chain-howto-sales.md) | Learn how to work with items and their embedded carbon footprints during the sales process. |

## Related information

[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Ad hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)  
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
