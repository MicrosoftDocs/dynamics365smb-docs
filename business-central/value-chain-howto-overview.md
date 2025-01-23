---
title: Sustainability Value Chain overview
description: Learn about the sustainability value chain features by using the provided information and resources.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, value chain
ms.search.form: 
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Sustainability Value Chain Overview   

> [!IMPORTANT]
> This set of features is available as a _public preview_ in Business Central starting from **2025 release wave 1**. Please, read careful which features are supported in this moment.  

The Sustainability Value Chain functionallity is a comprehensive tool designed to streamline the collection and utilization of data from your value chain partners. This feature empowers organizations to accurately calculate their Scope 3 emissions, enabling better sustainability reporting and compliance with environmental standards.  

## Introduction to Value Chain for Scope 3 Emissions Calculation 

The sustainability value chain functionallity enables you to use data you got from your value chain partners and use that data to calculate your scope 3 emissions. A value chain in general is your vendor with whom you do business from whom you collect inbound emission data. After you collect emissions or product carbon footprint data from your vendors (value chain partners), you can use the data to calculate your scope 3 emissions in your internal business processes and calculate additional emission for handling with your items (transfers, production...), so you will have accurate information about embedded emissions for items you plan to sell. 

By leveraging the Sustainability Value Chain functionallity, businesses can achieve a higher level of accuracy in sustainability reporting, provide better communication with customers related to emissions in their products, better align with regulatory demands, and actively contribute to reducing their environmental footprint.  

##  How does the system keep data related to value chain  

To track sustainability value chain in Business Central, users will record and use transactions from the **Sustainability Value Entries** page.  

> [!NOTE]
> Sustainability Value Chain process works only with the CO2e (carbon equivalent)   

The **Sustainability Value Entry** table in Business Central is a crucial component for managing and tracking the value of embedded carbon footprint in items. It records all changes in the CO2e emissions of inventory items, including purchases, localtion transfers, production, sales, etc. This table helps ensure accurate CO2e (carbon equivalent) valuation and provides detailed insights into the emissions impact of inventory transactions.  

> [!IMPORTANT]
> Sustainability value chain functionality uses only average method of CO2e emission calculation per Item. An item's **CO2e per Unit** is calculated as the average **CO2e per Unit** at each point in time after a purchase.   

## Available fetures   

To get started with sustainability value chain functionallity, use the following articles.  

| Article | Description |
|---------|-------------|
| [Value Chain Setup](value-chain-howto-setup.md) | This article provides information how to enable value chain in Business Central and all aditional setup you need to make. |
| [Default emission values](sustainability-howto-default.md) | This article provides information how to set up default values on you master data you will use across the system. |
| [Value Chain in Purchase](value-chain-howto-purchase.md) | This article provides information to help you understanding how value chain process starts with the purchase process. |
| [Value Chain in Transfers](value-chain-howto-transfer.md) | This article provides information how to work with transfer order related to their impact to the sustainability value chain process. |
| [Value Chain in Assembly process](value-chain-howto-assembly.md) | This article provides information how to work with assembly orders related to the sustainability value chain process. |
| [Value Chain in Production process](value-chain-howto-mfg.md) | This article provides information how to work with production orders related to the sustainability value chain process, but also with other elements related to manufacturing. |
| [Value Chain in Sales](value-chain-howto-sales.md) | This article provides information to help you working with items and their embedded carbon footprints during the sales process. |


## See also  

[Sustainability Management overview](finance-manage-sustainability.md) 
[Sustainability setup](finance-sustainability-setup.md)    
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)    
[Record sustainability entries](finance-sustainability-journal.md)    
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
[Sustainability reports and analytics in Business Central](sustainability-reports.md)   
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
