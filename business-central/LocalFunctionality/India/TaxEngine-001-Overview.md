---
title: Tax Engine Overview
description: Provides an overview of the Tax Engine, its components, and configuration options for managing tax rules and calculations in Business Central for India.
author: v-debapd
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Tax engine overview

Tax rules can change frequently. Changes can affect tax rates, calculation methods, tax filing, and reporting. The tax engine helps you manage tax rules and calculations through configuration.

The tax engine includes a use case designer for modifying existing use cases or creating new ones. A use case describes a business scenario and the conditions for calculating tax. Application events trigger the calculation. You can enable or disable use cases to meet your business needs.

The tax engine consists of six modules. Together, these modules support tax configuration, calculation, posting, and configuration import and export.

|Particulars|Description|
|---------|---------|
|**Tax Engine Core Extension**|Contains shared UI elements, tables, and library functions for lookups, conditions, and value handling. Other extensions can use these functions.|
|**Tax Engine Tax Type Handler Extension**|Tax Type Handler extension contains UI elements and related tables, which enables definition of a new tax type, its attributes, and map business entities involved with this tax type.|
|**Tax Engine Tax Use Case Handler Extension**|Tax Use Case Handler extension contains UI elements and related tables, which are used for configuring a tax use case. Use case definition includes primary business entity like Sales Order or Purchase Order line table, conditions for execution of use case, rules, and formulae for calculation of tax and functionality to script business logic.|
|**Tax Engine Scripting Extension**|Script extension contains UI elements and related tables, which are used in scripting of Business logic within a use case.|
|**Tax Engine Tax Posting Handler Extension**|Posting Handler extension contains UI elements and related tables, which are used to configure posting of tax components to G/L Accounts and related tax ledgers.|
|**Tax Engine JSON Exchange Extension**|Imports and exports tax engine configuration data in JSON format.|

> [!NOTE]
> The Tax engine functionality is only available for legal entities with a primary address in India.

## Related information

[Tax Engine Import Export Configuration](TaxEngine-002-Import-Export-Configuration.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]