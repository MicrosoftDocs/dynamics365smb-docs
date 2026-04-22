---
title: Cloud Migration Extensions for Migrating to Business Central Online
description: Use the cloud migration extensions to migrate your on-premises data to Business Central online. These extensions move your on-premises data to the cloud.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: app, add-in, manifest, customize, import, implement
ms.search.form: 4021, 4026, 4031, 4090, 4091, 4092, 4093, 4094, 4095, 4096, 4097, 40027, 
ms.reviewer: bholtorf
ms.date: 04/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Cloud migration extensions for migrating to Business Central Online

Depending on your on-premises solution, you must use different extensions to connect your data with [!INCLUDE[prod_short](includes/prod_short.md)] online for purposes of migrating your solution to the cloud.  

If you are using one of the supported on-premises products, you can configure your cloud environment based on a product-specific extension. Once your cloud environment is configured, you can migrate data from your on-premises solution to [!INCLUDE[prod_short](includes/prod_short.md)]. This enables you to take full advantage of what the cloud has to offer your business such as enhanced insights into your business, artificial intelligence, multiple device access, and anytime, anywhere access.

For more information, see [Migrating On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content for [!INCLUDE[prod_short](includes/prod_short.md)].  

## Business Central on-premises

If you are using an on-premises deployment of [!INCLUDE[prod_short](includes/prod_short.md)], get the **Intelligent Cloud Base** extension and the **Business Central Intelligent Cloud** extension, and then run the **Cloud Migration Setup** assisted setup guide.  

## Dynamics GP

If you are using Dynamics GP, get the **Dynamics GP Historical Data**, **Dynamics GP Intelligent Cloud**, and **Dynamics GP Intelligent Cloud - US** extensions, and then run the **Cloud Migration Setup** assisted setup guide.  

> [!IMPORTANT]
> Migrating from Dynamics GP using the **Cloud Migration Setup** assisted setup guide is currently only supported for the following markets: United States, Canada, United Kingdom.

## Related information

[Cloud Migration Base Extension](ui-extensions-intelligent-cloud.md)  
[Migrating On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
