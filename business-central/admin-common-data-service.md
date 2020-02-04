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

# About Common Data Service
Business apps often use data from more than one source. [!INCLUDE[d365fin](includes/cds_long_md.md)] combines data into a single set of logic, which makes it easier to connect other Dynamics 365 applications, such as Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Talent, or even your own application, to [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. 

## Bi-Directional or Uni-directional Data Synchronization
Depending on your business needs, you can set up the integration to synchronize data either to or from [!INCLUDE[d365fin](includes/cds_long_md.md)], or in both directions in near-real time. For example, if you are using [!INCLUDE[d365fin](includes/cds_long_md.md)] to exchange data with Dynamics 365 Sales, when a person updates information about an account the corresponding customer is updated in [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. for 

## Standard and Custom Entities
[!INCLUDE[d365fin](includes/cds_long_md.md)] securely stores data in a set of entities, which are sets of records similar to how a table stores data within a database. [!INCLUDE[d365fin](includes/cds_long_md.md)] includes a base set of standard entities that cover typical scenarios, but you can also create custom entities specific to your organization. 

You can view standard, and custom entities if you have them on the Table Integration Mappings page.

## See Also
[Company and Business Unit Relationships](admin-cds-company-concept.md)  
[Walkthrough: Customizing an Integration with Common Data Service](admin-walkthrough-customizing-cds-integration.md)



