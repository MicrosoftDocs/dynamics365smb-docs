---
title: Introduction to Microsoft Fabric and Business Central
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
# Introduction to Microsoft Fabric and Business Central

[!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] is an end-to-end analytics solution with full-service capabilities including data movement, data lakes, data engineering, data integration, data science, real-time analytics, and business intelligence&mdash;all backed by a shared platform providing robust data security, governance, and compliance. Your organization no longer needs to stitch together individual analytics services from multiple vendors. Instead, use a streamlined solution that’s easy to connect, onboard, and operate.

> [!NOTE]
> [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] is currently in preview. For more information about the Microsoft Fabric release plan, see [aka.ms/FabricRoadmap](https://aka.ms/FabricRoadmap)
> 
> The regular publishing of this roadmap will help you stay informed about how [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] will address your needs.

## Where does [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] fit into [!INCLUDE[prod_short](includes/prod_short.md)] analytics

[!INCLUDE[prod_short](includes/prod_short.md)] comes with many out-of-the-box reports and data analysis capabilities such as financial reporting, open in Excel, and analysis mode on lists and queries. On top of this, it's easy to define Power BI reports that read data from standard and custom APIs, define Power BI metrics scorecards, and embed all of these directly in the [!INCLUDE[prod_short](includes/prod_short.md)] client. But for customers with more advanced data science or business intelligence scenarios that require richer data engineering or data integration, [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] might be a good option. 

## OneLake

A key part of [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] offering is OneLake. OneLake is a single, unified, logical data lake for the whole organization. You can think of OneLake as the OneDrive for data. It provides you with data lake as a service without having to build it yourself. OneLake comes automatically with every [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] tenant with no infrastructure to manage. All the data, which lands in OneLake, automatically takes part in out-of-the-box data governance such as data lineage, data protection, certification, and catalog integration. It breaks down data silos by enabling different parts of the organization to work independently while still contributing to the same data lake.

[!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] items store your data in OneLake in an open file format. For structured tabular data, this format is *delta parquet*. Delta parquet format allows every analytics engine in [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] to access the data from other analytics engines. This way, it allows flexibility for data practitioners to use the tools of your choice.

> [!NOTE]
> We expect that with one of our future releases, [!INCLUDE[prod_short](includes/prod_short.md)] data will also be made available in OneLake for the customers who use both [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] and have unique requirements in the areas that [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] supports. The timeline will depend on the timeline of the general availability of [!INCLUDE[microsoft_fabric](includes/microsoft_fabric.md)] and its components required to enable this experience. We're going to update this article with a more precise timeline, once we know more.

## See also
[Using Power BI with Business Central](admin-powerbi.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
