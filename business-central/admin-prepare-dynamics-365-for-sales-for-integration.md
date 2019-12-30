---
title: Integrating with Dynamics 365 Sales| Microsoft Docs
description: Learn how to get Dynamics 365 Business Central ready to integrate with Dynamics 365 Sales.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, integrating
ms.date: 10/01/2019
ms.author: bholtorf

---
# Integrating with Dynamics 365 Sales
The sales person role is often considered as one the most outward-facing jobs in a business. However, it can be helpful for sales people to be able to look inward in the business and see what is happening on the back end. By integrating [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)], you can give your sales people that insight by enabling them to view information in [!INCLUDE[d365fin](includes/d365fin_md.md)] while they are working in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, when preparing a sales quote it could be useful to know whether you have enough inventory to fulfill the order. For more information, see [Using Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md).

> [!NOTE]
> These steps describe the process of integrating the online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)]. For information about on-premises configuration, see [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

<!--## Software Requirements
You must have an Office 365 subscription, and both [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)] must be part of the same organization.  -->

## Overview of the Integration Process
The following steps provide an overview of the steps to integrate [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!Note]  
> These tasks require the **System Administrator** security role in [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)].  

1. In the Microsoft 365 admin center, set up a user account for connecting to and synchronizing data with [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

2. Assign licenses for [!INCLUDE[crm_md](includes/crm_md.md)] to the [!INCLUDE[d365fin](includes/d365fin_md.md)] users who will use the integrated apps.

3. Set up a connection to [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Set Up a Connection to Dynamics 365 Sales](admin-how-to-set-up-a-dynamics-crm-connection.md).  

4. Optional: Couple [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] records. For more information, see [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md).

5. Synchronize data between the apps. For more information, see [Synchronizing Business Central and Dynamics 365 Sales](admin-synchronizing-business-central-and-sales.md).  

## About the Business Central Integration Solution
The solution lets people view information in [!INCLUDE[d365fin](includes/d365fin_md.md)] while they are working in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, it can provide insights into customer statistics, allows users to couple and view records in [!INCLUDE[d365fin](includes/d365fin_md.md)] from [!INCLUDE[crm_md](includes/crm_md.md)], and allows people to see whether products are available in [!INCLUDE[d365fin](includes/d365fin_md.md)].

By default, the **Set Up Dynamics 365 Sales Connection** assisted setup guide will import the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution. To do that, the setup guide uses an administrator user account. This account must also be a valid user in [!INCLUDE[crm_md](includes/crm_md.md)] with the following security roles:

* System Administrator  
* Solution Customizer  

For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md), [Create users in Microsoft Dynamics 365 (online) and assign security roles](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles), and [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

This account is used only one time during the setup. After the solution is imported into [!INCLUDE[d365fin](includes/d365fin_md.md)] the account is no longer needed. Integration will continue to use the user account that was created specifically for the integration.

In addition to customizing [!INCLUDE[crm_md](includes/crm_md.md)], the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution also creates the following roles in [!INCLUDE[crm_md](includes/crm_md.md)] for the integration:

* **Integration Administrator** - Allows users to manage the connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)]. Typically assigned only to the user account for synchronization.  
* **Integration User** - Allows users to access synchronized data. Typically assigned to the user account for synchronization and any other user who needs to view or access the synchronized data.
* **Product Availability User** - Allows users to query product availability in [!INCLUDE[d365fin](includes/d365fin_md.md)] from [!INCLUDE[crm_md](includes/crm_md.md)].

For details about each role, such as the permissions and access levels, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

At the end of the setup guide, [!INCLUDE[d365fin](includes/d365fin_md.md)] prompts you to couple sales people to users in [!INCLUDE[crm_md](includes/crm_md.md)]. Records in [!INCLUDE[crm_md](includes/crm_md.md)] usually have an owner (user) assigned to them, and if coupling between the user in [!INCLUDE[crm_md](includes/crm_md.md)] and the sales person in [!INCLUDE[d365fin](includes/d365fin_md.md)] does not exist, synchronization will fail. You can also do this later by using the **Couple Salespersons** action on the **Microsoft Dynamics 365 Connection Setup** page.

## See Also  
[Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Dynamics 365 Sales](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronizing Business Central and Dynamics 365 Sales](admin-synchronizing-business-central-and-sales.md)  
[Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration)
