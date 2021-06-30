---
title: "Using Microsoft Dataverse"
description: Introduction to how to integrate and use Microsoft Dataverse and its components to connect to other Dynamics 365 applications.
author: bholtorf

ms.author: bholtorf
ms.custom: na
ms.reviewer: na
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 06/14/2021
---

# Integrating with Microsoft Dataverse
[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

Business apps often use data from more than one source. [!INCLUDE[prod_short](includes/cds_long_md.md)] combines data into a single set of logic that makes it easier to connect other Dynamics 365 applications, such as [!INCLUDE[crm_md](includes/crm_md.md)] or your own application built on top of [!INCLUDE[prod_short](includes/cds_long_md.md)], to [!INCLUDE[prod_short_md](includes/prod_short.md)]. For more information about [!INCLUDE[prod_short](includes/cds_long_md.md)], see [What is Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)

The following steps provide an overview of the steps to integrate [!INCLUDE[prod_short](includes/cds_long_md.md)] with [!INCLUDE[prod_short](includes/prod_short.md)].

> [!Note]  
> These tasks require the **System Administrator** security role in [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)].  

1. Assign licenses for [!INCLUDE[prod_short](includes/cds_long_md.md)] to the [!INCLUDE[prod_short](includes/prod_short.md)] users who will use the integrated apps.

2. Set up a connection to [!INCLUDE[prod_short](includes/cds_long_md.md)]. For more information, see [Connect to Dataverse](admin-how-to-set-up-a-dynamics-crm-connection.md).  

3. Synchronize data between the apps. For more information, see [Synchronizing Business Central and Dataverse](admin-synchronizing-business-central-and-sales.md). 

## Getting Started with [!INCLUDE[prod_short](includes/cds_long_md.md)]
To get started with [!INCLUDE[prod_short](includes/cds_long_md.md)] you will need a Microsoft Power Apps account. If you do not already have a Power Apps account, you can get one for free by visiting [powerapps.com](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) and choosing the **Get started free** link. To learn more about how to get started with [!INCLUDE[prod_short](includes/cds_long_md.md)], see the [Get started with Dataverse](/learn/modules/get-started-with-powerapps-common-data-service/) module from Microsoft Learn.

## Bi-Directional or Uni-directional Data Synchronization
Depending on your business needs, you can set up the integration to synchronize data either to or from one Dynamics 365 business app to another, or in both directions in near-real time through [!INCLUDE[prod_short](includes/cds_long_md.md)]. For example, if you integrate [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[crm_md](includes/crm_md.md)] through [!INCLUDE[prod_short](includes/cds_long_md.md)], a salesperson can create a sales order in [!INCLUDE[crm_md](includes/crm_md.md)] and the order will be synchronized to [!INCLUDE[prod_short](includes/prod_short.md)]. Conversely, from [!INCLUDE[crm_md](includes/crm_md.md)], the salesperson can view information from [!INCLUDE[prod_short](includes/prod_short.md)] about the availability of the item on the order. 

## Standard and Custom Entities
[!INCLUDE[prod_short](includes/cds_long_md.md)] securely stores data in a set of tables, which are sets of records similar to how a table stores data within a database. [!INCLUDE[prod_short](includes/cds_long_md.md)] includes a base set of standard tables that cover typical scenarios, but you can also create custom tables specific to your organization. In [!INCLUDE[prod_short](includes/prod_short.md)], you can view standard and custom tables being synchronized on the Integration Table Mappings page.

## About the Business Central Base Integration Solution

The Base Integration Solution is a key component of the integration. The solution adds the required roles and access levels to the user accounts for the integration, and it creates tables needed to map [!INCLUDE[prod_short](includes/prod_short.md)] company to business unit in [!INCLUDE[prod_short](includes/cds_long_md.md)]. 

By default, the **Set up [!INCLUDE[prod_short](includes/cds_long_md.md)] connection** assisted setup guide will import the solution. To do that, the setup guide uses an administrator user account that you specify. This account must be a valid user in [!INCLUDE[prod_short](includes/cds_long_md.md)] with the following security role:

* System Administrator  

For more information, see [Setting Up User Accounts for Integrating with [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-setting-up-integration-with-dynamics-sales.md) and [Create users in Microsoft Dynamics 365 (online) and assign security roles](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles). 

The administrator account is used only one time during the setup for the configuration changes that the Base Integration Solution makes in [!INCLUDE[prod_short](includes/cds_long_md.md)]. After the solution is imported the account is no longer needed. Integration will continue to use the user account that is automatically created specifically for the integration.

In addition to customizing [!INCLUDE[prod_short](includes/cds_long_md.md)], the solution also creates the following roles in [!INCLUDE[prod_short](includes/cds_long_md.md)] for the integration:

* **Integration Administrator** - Allows users to manage the connection between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)]. Typically, this is assigned only to the automatically created user account for synchronization.  
* **Integration User** - Allows users to access synchronized data. Typically, this is assigned to the automatically created user account for synchronization and other users who need to view or access the synchronized data.

For details about each role, such as the permissions and access levels, see [Setting Up User Accounts for Integrating with [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-setting-up-integration-with-dynamics-sales.md).

During connection setup, integration table mappings that are needed to synchronize data, are created. Entities in [!INCLUDE[prod_short](includes/cds_long_md.md)] are mapped to tables and table fields in Business Central through integration tables. For more information, see [Standard Entity Mapping for Synchronization](admin-synchronizing-business-central-and-sales.md#standard-table-mapping-for-synchronization).

## See Also
[Data Ownership Models](admin-cds-company-concept.md)  
<!--needs to be removed as this is moved to dev-itpro docs[Walkthrough: Customizing an Integration with Dataverse](\dynamics365\business-central\dev-itpro\administration\administration-custom-cds-integration) -->





[!INCLUDE[footer-include](includes/footer-banner.md)]