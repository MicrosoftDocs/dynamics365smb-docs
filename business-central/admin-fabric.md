---
title: Introduction to Business Central and Microsoft Fabric
description: Get an overview of using Microsoft Fabric to get insight, business intelligence, and KPIs from your Business Central data.
author: kennienp
ms.topic: overview
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.search.form: 6316, 6317
ms.reviewer: jswymer
ms.date: 10/10/2023
ms.author: kepontop
ms.custom: bap-template
---
# Introduction to [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)]

[!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] is an end-to-end analytics solution with full-service capabilities including data movement, data lakes, data engineering, data integration, data science, real-time analytics, and business intelligence—all backed by a shared platform providing robust data security, governance, and compliance. Your organization no longer needs to stitch together individual analytics services from multiple vendors. Instead, use a streamlined solution that’s easy to connect, onboard, and operate.

> [!NOTE]
> [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] is currently in preview. For more information about the Fabric roadmap, see [aka.ms/FabricRoadmap](https://aka.ms/FabricRoadmap)
> 
> The regular publishing of this roadmap will help ensure you have line-of-sight into how [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] is going to address your needs.

## OneLake
A key part of [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] is OneLake. You can think of OneLake as the OneDrive for data. It provides you with data lake as a service without having to build it yourself. Every [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] tenant will have one OneLake. There is no infrastructure to set up or manage. All the data, which lands in OneLake will automatically take part in out of the box data governance such as data lineage, data protection, certification, and catalog integration. It breaks down data silos by enabling different parts of the organization to work independently while still contributing to the same data lake.

[!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] items store your data in OneLake in an open file format. For structured tabular data, this format is delta parquet. This format allows every analytics engine in [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] to access the data from other analytics engines. This way it allows flexibility for data practitioners to use the tools of your choice.

> [!NOTE]
> In a future release, [!INCLUDE[prod_short](includes/prod_short.md)] data is planned to also be available in OneLake for customers who both use [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] and [!INCLUDE[prod_short](includes/prod_short.md)]. When we know more about availability of [!INCLUDE[prod_short](includes/prod_short.md)] data in OneLake, we will update this article with a timeline.

## See also
[Using Power BI with Business Central](admin-powerbi.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
