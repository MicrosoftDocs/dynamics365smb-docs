---
title: Intelligent Cloud | Microsoft Docs
description: Get a cloud copy of your data so you are connected to the intelligent cloud.
author: bmeier94

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms. search.keywords: cloud, edge
ms.date: 09/11/2018
ms.author: bmeier

---

# Your Access to the Intelligent Cloud with [!INCLUDE[prodlong](includes/prodlong.md)]

As a user of [!INCLUDE[prodshort](includes/prodshort.md)] online, you have full access to scenarios that are based on the Intelligent Cloud, such as editing data in Excel and pushing changes back to [!INCLUDE[prodshort](includes/prodshort.md)], or when you view your data in Power BI. However, while [!INCLUDE[prodshort](includes/prodshort.md)] is a cloud-first service, also those customers who need to run their workloads fully on-premises or on the intelligent edge connected to the cloud can do so.  

If you are interested in [!INCLUDE[prodshort](includes/prodshort.md)], you can sign up for a free trial of the default, cloud deployment solution, or you can choose to work with a partner to deploy [!INCLUDE[prodshort](includes/prodshort.md)] locally to your own choice of hardware. You can then decide to connect to the cloud through your tenant in the cloud. As a result, the data from your locally deployed [!INCLUDE[prodshort](includes/prodshort.md)] will be replicated to the cloud for intelligent cloud scenarios.  

For more information about connecting to the intelligent cloud from an on-premises solution, see [Connect to the Intelligent Cloud](/dynamics365/business-central/dev-itpro/administration/about-intelligent-edge) in the ITPro content for [!INCLUDE[prodshort](includes/prodshort.md)].  

## Making your purchase decision

When making a [!INCLUDE[prodshort](includes/prodshort.md)] purchase decision, you will have the option of making a purchase through CSP or through DPL. If you want to make a CSP purchase but your partner is not a CSP partner, it is recommended the partner work with a Master VAR that is a CSP partner.

You can also get started by signing up for a [free trial](https://dynamics.microsoft.com/en-gb/business-central/) and decide to purchase a license after the 30-day trial expires.  

### License purchased in CSP

Various service plans or offers are available in CSP to purchase [!INCLUDE[prodshort](includes/prodshort.md)]. For more information, see [Dynamics 365 Business Central Pricing](https://dynamics.microsoft.com/en-us/business-central/overview/#pricing).  

- [!INCLUDE[prodshort](includes/prodshort.md)]

      This is a ‘dual rights’ license, named user, subscription based offer that provides you with the flexibility to configure a cloud tenant, on-premise installation, or an Intelligent Cloud environment that enables you to use your [!INCLUDE[prodshort](includes/prodshort.md)] cloud tenant in conjunction with your [!INCLUDE[prodshort](includes/prodshort.md)] on-premises installation.  
      The cloud environment is set up through CSP, and the on-premises offer is set up using Order Central to obtain the FLF file. The initial purchase will be made in CSP, the order information will automatically sync with Order Central.  
      This is ideal for customers that want a full cloud solution to run their business or customers that want ownership of an on-premises installation but want to take advantage of the growing services and value available in the cloud.  
- Intelligent Cloud Add-in

      This is a premium license for a [!INCLUDE[prodshort](includes/prodshort.md)] cloud solution run and managed in Microsoft Service. This is a named user, subscription-based offer, that will be available for users that have purchased their on-premises software through DPL.  
      This is ideal for customers that want to maintain ownership of an on-premises installation but want to take advantage of the growing services and value available in the cloud as well as switch from a BREP model (CAPEX) to CSP model (COPEX).  

### License purchased through DPL

Various plans are available in DPL to purchase [!INCLUDE[prodshort](includes/prodshort.md)], Dynamics GP 2018 R2, Dynamics NAV 2018, or Dynamics SL 2018).  

All DPL purchases will be made through Order Central. At minimum, an Intelligent Cloud Add-In license must be purchased through CSP to create your Intelligent Cloud environment.

## Viewing intelligent cloud insights on-premises

Now that your connection to the Intelligent Cloud is up and running, you are also able to view the insights from the many cloud services within your on-premises application.  

To view Intelligent Cloud insights, navigate to the **Intelligent Cloud Insights** page.  

### Power BI

Enhancements to the current Power BI embed experience include automatic deployment of Power BI reports, default report selection, and the ability for users to manage their Power BI reports without ever requiring them to leave [!INCLUDE[prodshort](includes/prodshort.md)].  

Power BI reports will be automatically be deployed and selected upon user sign in. Once visible in Business Central, users can make edits to their Power BI reports from a new page in [!INCLUDE[prodshort](includes/prodshort.md)] that surfacing all the Power BI functionality to modify reports.  

[!INCLUDE[prodshort](includes/prodshort.md)] will also provide different default reports based upon where the data originated from. For example, if data originated from Dynamics GP, a set of default reports, specific to Dynamics GP related data, will be deployed.  

A new connector will also be available for the Oct. 1 release for [!INCLUDE[prodshort](includes/prodshort.md)] (on-premises) and will require basic authentication to connect.  

#### Microsoft Flow

The latest version of the Flow connector for [!INCLUDE[prodshort](includes/prodshort.md)] includes support for a delta service to monitor changes in data as well as expose CREATE, MODIFY and DELETE triggers when creating new Flows.  

Your [!INCLUDE[prodshort](includes/prodshort.md)] on-premises solution uses a different Flow connector that requires basic authentication to connect. This connector is not supported in the delta service, therefore CREATE, MODIFY and DELETE triggers will not be exposed when creating a Flow.  

## See Also

[Welcome to Business Central](index.md)  
[Business Central Intelligent Cloud extension](ui-extensions-intelligent-cloud.md)  
[Data Replication extension](ui-extensions-data-replication.md)  
[Connect to the Intelligent Cloud](/dynamics365/business-central/dev-itpro/administration/about-intelligent-edge)  
