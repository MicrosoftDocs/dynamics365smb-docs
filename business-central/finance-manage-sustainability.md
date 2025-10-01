---
title: Sustainability management overview
description: Learn about the sustainability management feature by using the provided information and resources.
author: altotovi
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, carbon, CO2
ms.search.form: 
ms.date: 02/03/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Sustainability management overview

Business Central offers sustainability management features that help you monitor and manage your organization's effect on the environment. The features are designed to oversee and regulate an organization's environmental footprint by tracking various greenhouse gas (GHG) emissions, and water and waste intensity to gather insights. You gather sustainability data using sustainability journals, general journals, or purchase documents, and the recalculation of emissions to the CO2 equivalent (CO2e). You can manually enter known data, or use built-in methods to calculate emissions. However, calculation using formulas is available only when you use sustainability journals.

Based on GHG protocol, there are three emission scopes:  

- **Scope 1 emissions** include emissions from stationary and mobile combustion, and from inadvertent fugitive emissions.  
- **Scope 2 emissions** include indirect emissions from the generation of energy that is purchased from utility providers.  
- **Scope 3 emissions** include a wide spectrum of emissions, from purchased goods and services and capital goods, to fuel and energy–related activities, to upstream and downstream transportation, to generated waste, to business travel and employee commuting, and so on.

But, [!INCLUDE [prod_short](includes/prod_short.md)] offers other emission scopes:  

- **Out of scope** emissions include emissions that fall outside these defined categories but are still relevant for a complete understanding of how an organization affects the environment. For example, emissions from activities or sources that an organization doesn't directly control but still contribute to the overall carbon footprint. Another example is carbon credits, which don't have a specific scope.
- **Water/Waste** refers to the measurement and estimation of water withdrawn or discharged and waste disposed or diverted. The measurement is based on intensity factors and is intended to provide a comprehensive understanding of an organization's environmental effects.

With this set of features, you can:

- Set up emission factors for different sources and categories of GHG emissions, water, and waste.
- Record emission, or water and waste intensity data in sustainability journals, either manually or by using predefined calculation methods.
- Record emission data directly with purchase documents or general journals.  
- Record purchase of carbon credit using purchase documents or sustainability journals.
- Calculate internal carbon fees.
- Recalculate emission of all gasses to the CO2 equivalent using formulas.  
- Post emission entries (and carbon credits) to the sustainability ledger, where you can view and analyze the emission data by various dimensions.
- Set scorecards and goals and compare them with baseline and targeted values.  
- Generate sustainability reports that show your organization's GHG emissions or water and waste intensity performance.  
- Use financial reports for cross-functional reporting.
- Operate with the value chain for Scope 3 across various operations (Public Preview).
- Integrate sustainability features with non-Microsoft systems using APIs.  

To following table links to articles that can help you get started with sustainability management.

| Article | Description |
|---------|-------------|
| **Feature** |             |
| [Sustainability setup](finance-sustainability-setup.md) | Learn how to configure sustainability features. |
| [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md) | Learn how to set up charts of sustainability accounts (CoSA), account categories, and subcategories. It also describes how to analyze information in sustainability ledger entries. |
| [Record sustainability entries](finance-sustainability-journal.md) | Learn how to work with all types of sustainability journals. |
| [Work with carbon credits](sustainability-carbon-credit.md) | Learn how to set up and purchase carbon credit. |
| [Work with sustainability certificates](sustainability-certificates.md) |  Learn about sustainability certificates, and how to set up and use them.  |
| **Planning** |             |
| [Sustainability scorecards and goals overview](sustainability-scorecards-goals.md) | Learn how to set up and use sustainability scorecards and goals. |
| **Reporting** |             |
| [Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md) | Learn how to use ad-hoc analysis to analyze sustainability data directly from list pages and queries. |
| [Sustainability reports and analytics in Business Central](sustainability-reports.md) | Learn how to use integrated reports and analytics related to sustainability. |
| [Analyzing sustainability entries with financial reports](sustainability-fin-reporting.md) | Learn how to use financial reports to create ways to analyze sustainability performance data. |
| **Integrations** |             |
| [Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json) | Learn how to create connected apps that establish a point-to-point connection between [!INCLUDE [prod_short](includes/prod_short.md)] and non-Microsoft sustainability solutions or services using APIs. |

## Related information

[Sustainability setup](finance-sustainability-setup.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Ad hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)  
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
