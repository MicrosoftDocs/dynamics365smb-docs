---
author: brentholtorf
ms.topic: include
ms.date: 04/01/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
[!INCLUDE[prod_short](prod_short.md)] users sometimes support more than one department or suborganization within a business unit. For example, a business might have sales offices in different cities and multiple countries/regions, so it has created a separate business unit for each office. The offices that are in the same country/region are set up as separate *companies* in a shared *environment*. Other offices are created as companies in separate environments because they are geographically based in other countries/regions.

- What's a company?

  Think of a *company* as a container that holds information about a legal entity. Using the example above, the business has a sales office in Seattle and another in New York, so it creates a company in [!INCLUDE[prod_short](prod_short.md)] for each office so that it can manage operations for each office separately.

- What's an environment?

  Companies in [!INCLUDE[prod_short](prod_short.md)] online exist in what are referred to as *environments*. There are two types of environments, **Production** and **Sandbox**. In short, production environments contain live business data, and sandbox environments are used as a safe place to test things like new business processes or features. For more information, see [Types of environments](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-environments#types-of-environments) (in English only). If you have access to a company, you have access to the environment it's in. If you have access to more than one company, and those companies are in different environments, when you sign in to [!INCLUDE[prod_short](prod_short.md)] you must specify the environment that you want to work in. Environments are particular to a given country/region, so if your organization works in multiple countries/regions, you need separate environments for each country/region. For more information, see [Environments and companies](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology#environments-and-companies) (in English only).
