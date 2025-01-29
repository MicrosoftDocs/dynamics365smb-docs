---
title: Sustainability management overview
description: Learn about the sustainability management feature by using the provided information and resources.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, carbon, CO2
ms.search.form: 
ms.date: 09/06/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Sustainability management overview

Business Central offers a sustainability management feature that helps you monitor and manage your organization's and its effect on the environment. This feature is designed to oversee and regulate an organization's environmental footprint by tracking various greenhouse gas (GHG) emissions, water and waste intensity. In this way, it facilitates proper insights. The feature supports the basic process of collecting gas emission, water and waste intensity data via sustainability and general journals or purchase documents, and recalculation of emissions to the CO2 equivalent (CO2e). You can either manually enter known data or use built-in methods for calculating emissions footprints; calculation using formulas are available for use only when using sustainability journals.   

> [!NOTE]
> New set of features is expected to be added with every release.  

Base on the Greenhouse Gas (GHG) Protocol we use three emission scopes:  

- **Scope 1 emissions** include emissions from stationary and mobile combustion, and from inadvertent fugitive emissions.  
- **Scope 2 emissions** include indirect emissions from the generation of energy that is purchased from utility providers.  
- **Scope 3 emissions** include a wide spectrum of emissions, from purchased goods and services and capital goods, to fuel and energy–related activities, to upstream and downstream transportation, to generated waste, to business travel and employee commuting, and so on. 

But in Business Central we have these additional options:  

- **Out of scope emissions** include emissions that fall outside these defined categories but are still relevant for a complete understanding of an organization's environmental impact; this can include emissions from activities or sources that are not directly controlled by the organization but still contribute to the overall carbon footprint, or i.e. Carbon Credit as it does not have specific scope. 
- **Water/Waste** option refers to the measurement and estimation of water withdrawn or discharged and waste disposed or diverted, based on intensity factors, to provide a comprehensive understanding of an organization's environmental impact.   

With this se of features, you can:

- Set up emission factors for different sources and categories of GHG emissions, water and waste. 
- Record emission, or water and waste intensity data in sustainability journals, either manually or by using predefined calculation methods.
- Record emission data directly working with purchase documents or general journals.  
- Record purchase of carbon credit using purchase documents or sustainability journal. 
- Calculate internal carbon fee.   
- Recalculate emission of all gasses to the CO2 equivalent using formulas.  
- Post emission entries (and carbon credits) to the sustainability ledger, where you can view and analyze the emission data by various dimensions. 
- Set scorecards and goals and compare them with baseline and targeted values.  
- Generate sustainability reports that show your organization's GHG emissions or water and waste intensity performance.  
- Use financial reports for cross functional reporting.   
- Operate with the value chain for Scope 3 across various operations (Public Preview). 
- Inegrate sustainability solution with the 3rd party systems using APIs.  

To get started with sustainability management, use the following articles.   

| Article | Description |
|---------|-------------|
| **Feature** |             |
| [Sustainability setup](finance-sustainability-setup.md) | This article provides information to help you correctly configure the whole Sustainability module. |
| [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md) | This article provides information on how to set up charts of sustainability accounts (CoSA), account categories, and subcategories. And also, how to analyze information in sustainability ledger entries. |
| [Record sustainability entries](finance-sustainability-journal.md) | Use this article to learn how to work with all types of sustainability journals. |
| [Work with carbon credits](sustainability-carbon-credit.md) | Learn how to set up and purchase carbon credit. |
| [Work with sustainability certificates](sustainability-certificates.md) |  Learn what the sustainability certificates are and how to set up and use them.  |
| **Planning** |             |
| [Sustainability scorecards and goals overview](sustainability-scorecards-goals.md) | Learn how to set up and use sustainability scorecards and goals. |
| **Reporting** |             |
| [Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md) | This article provides information about how to use ad-hoc analysis to analyze sustainability data directly from list pages and queries. |
| [Sustainability reports and analytics in Business Central](sustainability-reports.md) | This article provides information about how to use integrated reports and analytics related to Sustainability in Business Central. |
| [Analyzing sustainability entries with financial reports](sustainability-fin-reporting.md) | Describes how to use financial reports to create various views and reports for analyzing sustainability performance data. |
| **Integrations** |             |
| [Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json) | Use this article to learn how to create connected apps that establish a point-to-point connection between Business Central and non-Microsoft sustainability solutions or services using APIs. |

## See also

[Sustainability setup](finance-sustainability-setup.md)    
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)    
[Record sustainability entries](finance-sustainability-journal.md)    
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
[Sustainability reports and analytics in Business Central](sustainability-reports.md)   
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Finance](finance.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
