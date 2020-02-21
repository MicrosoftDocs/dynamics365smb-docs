---
title: "Using Common Data Service"
description: Introduction to Common Data Service and its components.
author: bholtorf

ms.author: bholtorf
ms.custom: na
ms.reviewer: na
ms.service: dynamics365-business-central
ms.topic: article
ms.date: 10/01/2019
---

# Integrating with Common Data Service
Business apps often use data from more than one source. [!INCLUDE[d365fin](includes/cds_long_md.md)] combines data into a single set of logic that makes it easier to connect other Dynamics 365 applications, such as [!INCLUDE[crm_md](includes/crm_md.md)] or your own application built on top of [!INCLUDE[d365fin](includes/cds_long_md.md)], to [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. For more information about [!INCLUDE[d365fin](includes/cds_long_md.md)], see [What is Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

## Getting Started with [!INCLUDE[d365fin](includes/cds_long_md.md)]
To get started with [!INCLUDE[d365fin](includes/cds_long_md.md)] you will need a Microsoft Power Apps account. If you do not already have a Poser Apps account, you can get one for free by visiting [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) and choosing the **Get started free**link.

## Bi-Directional or Uni-directional Data Synchronization
Depending on your business needs, you can set up the integration to synchronize data either to or from one Dynamics 365 business app to another, or in both directions in near-real time through [!INCLUDE[d365fin](includes/cds_long_md.md)]. For example, if you integrate [!INCLUDE[d365fin](includes/d365fin_md.md)] with [!INCLUDE[crm_md](includes/crm_md.md)] through [!INCLUDE[d365fin](includes/cds_long_md.md)], a salesperson can create a sales order in [!INCLUDE[crm_md](includes/crm_md.md)] and the order will be synchronized to [!INCLUDE[d365fin](includes/d365fin_md.md)]. Conversely, from [!INCLUDE[crm_md](includes/crm_md.md)], the salesperson can view information from [!INCLUDE[d365fin](includes/d365fin_md.md)] about the availability of the item on the order. 

## Standard and Custom Entities
[!INCLUDE[d365fin](includes/cds_long_md.md)] securely stores data in a set of entities, which are sets of records similar to how a table stores data within a database. [!INCLUDE[d365fin](includes/cds_long_md.md)] includes a base set of standard entities that cover typical scenarios, but you can also create custom entities specific to your organization. In [!INCLUDE[crm_md](includes/crm_md.md)], you can view standard and custom entities on the Table Integration Mappings page.

## See Also
[Data Ownership Models](admin-cds-company-concept.md)  
[Walkthrough: Customizing an Integration with Common Data Service](admin-walkthrough-customizing-cds-integration.md)



