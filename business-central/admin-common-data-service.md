---
title: Integrate with Microsoft Dataverse via data sync
description: Introduction to how to integrate and use Microsoft Dataverse and its components to connect to other Dynamics 365 applications.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 06/10/2025
ms.custom: bap-template
ms.search.form: 7214_Primary
ms.service: dynamics-365-business-central
---

# Integrate with Microsoft Dataverse via data sync

Business apps often use data from more than one source. [!INCLUDE[cds_long](includes/cds_long_md.md)] combines data into a single set of logic that makes it easier to connect [!INCLUDE[prod_short](includes/prod_short.md)] to other Dynamics 365 applications. For example, [!INCLUDE[crm_md](includes/crm_md.md)] or your own application built on [!INCLUDE[cds_long](includes/cds_long_md.md)]. To learn more about [!INCLUDE[cds_long](includes/cds_long_md.md)], go to [What is Dataverse?](/power-apps/maker/data-platform/data-platform-intro).

The following steps provide an overview of the steps to integrate [!INCLUDE[cds_long](includes/cds_long_md.md)] with [!INCLUDE[prod_short](includes/prod_short.md)].

> [!Note]  
> These tasks require the **System Administrator** security role in [!INCLUDE[cds_long](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)].  

1. Assign licenses for [!INCLUDE[cds_long](includes/cds_long_md.md)] to the [!INCLUDE[prod_short](includes/prod_short.md)] users who will use the integrated apps.

2. Set up a connection to [!INCLUDE[cds_long](includes/cds_long_md.md)]. To learn more, go to [Connect to Dataverse](admin-how-to-set-up-a-dynamics-crm-connection.md).  

3. Synchronize data between the apps. To learn more, go to [Synchronizing Business Central and Dataverse](admin-synchronizing-business-central-and-sales.md).

## Get started with [!INCLUDE[cds_long](includes/cds_long_md.md)]

To get started with [!INCLUDE[cds_long](includes/cds_long_md.md)], you'll need a Microsoft Power Apps account. If you don't already have a Power Apps account, you can get one for free by visiting [powerapps.com](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) and choosing the **Get started free** link. To learn more about how to get started with [!INCLUDE[cds_long](includes/cds_long_md.md)], go to the [Get started with Dataverse](/training/modules/get-started-with-powerapps-common-data-service/) module from Microsoft training.

## Bi-directional or uni-directional data synchronization

You can synchronize data either to or from one Dynamics 365 business app to another, or in both directions in near-real time, through [!INCLUDE[cds_long](includes/cds_long_md.md)]. For example, if you integrate [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[crm_md](includes/crm_md.md)], a salesperson can create a sales order in [!INCLUDE[crm_md](includes/crm_md.md)] and the order synchronizes to [!INCLUDE[prod_short](includes/prod_short.md)]. Conversely, from [!INCLUDE[crm_md](includes/crm_md.md)], the salesperson can check the availability of the item on the order in [!INCLUDE[prod_short](includes/prod_short.md)]. 

## Standard and custom entities

[!INCLUDE[cds_long](includes/cds_long_md.md)] securely stores data in a set of tables, which are sets of records similar to how a table stores data within a database. [!INCLUDE[cds_long](includes/cds_long_md.md)] includes a base set of standard tables that cover typical scenarios, but you can also create custom tables specific to your organization. In [!INCLUDE[prod_short](includes/prod_short.md)], you can view standard and custom tables being synchronized on the Integration Table Mappings page.

## About the Business Central Base Integration Solution

The Base Integration Solution is a key component of the integration. The solution adds the required roles and access levels to the user accounts for the integration, and it creates tables needed to map [!INCLUDE[prod_short](includes/prod_short.md)] company to business unit in [!INCLUDE[cds_long](includes/cds_long_md.md)].

By default, the **Set up [!INCLUDE[cds_long](includes/cds_long_md.md)] connection** assisted setup guide imports the solution. To do that, the setup guide uses an administrator user account that you specify. This account must be a valid user in [!INCLUDE[cds_long](includes/cds_long_md.md)] with the **System Administrator** security role.  

To learn more about user accounts, go to the following articles:

* [Setting Up User Accounts for Integrating with [!INCLUDE[cds_long](includes/cds_long_md.md)]](admin-setting-up-integration-with-dynamics-sales.md)
* [Create users in Microsoft Dynamics 365 (online) and assign security roles](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles)

The administrator account is used only one time during the setup for the configuration changes that the Base Integration Solution makes in [!INCLUDE[cds_long](includes/cds_long_md.md)]. After the solution imports, the account is no longer needed. Integration will continue to use the user account that is automatically created specifically for the integration.

In addition to customizing [!INCLUDE [cds_long_md](includes/cds_long_md.md)], the solution also creates a security role in [!INCLUDE [cds_long_md](includes/cds_long_md.md)] for the integration:

* **Business Central Dataverse Integration** - Allows you to manage the connection between [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [cds_long_md](includes/cds_long_md.md)]. Typically, this role is assigned only to the user account that's automatically created for synchronization. To learn more about this role, go to [Setting Up User Accounts for Integrating with [!INCLUDE[cds_long](includes/cds_long_md.md)]](admin-setting-up-integration-with-dynamics-sales.md).

When you set up the connection, you create the integration table mappings that you need to synchronize data. Entities in [!INCLUDE[cds_long](includes/cds_long_md.md)] are mapped to tables and table fields in [!INCLUDE [prod_short](includes/prod_short.md)] through integration tables. To learn more about mappings, go to [Standard Entity Mapping for Synchronization](admin-synchronizing-business-central-and-sales.md#standard-table-mapping-for-synchronization).

> [!Note]  
> The Base Integration Solution doesn't define auditing settings (IsAuditEnabled) for the tables it extends. When you import the solution, it might disable auditing on tables where another solution previously enabled it. This behavior occurs because [!INCLUDE[cds_long](includes/cds_long_md.md)] applies the settings from the imported solution, and if auditing isn't explicitly enabled in the solution file, it defaults to disabled. After you enable the integration, check your auditing settings in [!INCLUDE[cds_long](includes/cds_long_md.md)] and re-enable auditing for the affected tables if needed. Alternatively, redeploy any solutions that previously enabled auditing on those tables.

## Handle differences in local and base transaction currencies

You can connect to a [!INCLUDE[cds_long](includes/cds_long_md.md)] environment that has a different base currency than the local currency in [!INCLUDE[prod_short](includes/prod_short.md)]. You make the connection in [!INCLUDE[prod_short](includes/prod_short.md)] on the **Dataverse Connection Setup** page or by using the **Set up connection to Dataverse** assisted setup guide.

To be able to connect, ensure that the base transaction currency setting in [!INCLUDE[cds_long](includes/cds_long_md.md)] has the currency that is set on the **Currencies** page in [!INCLUDE [prod_short](includes/prod_short.md)], and at least one exchange rate is specified for the currency on the **Currency Exchange Rates** page.

Here's an example. You're connecting [!INCLUDE[prod_short](includes/prod_short.md)] with Euro (EUR) set as the local currency on the **General Ledger Setup** page to a [!INCLUDE[cds_long](includes/cds_long_md.md)] environment that has a base transaction currency set to US dollar (USD). You'll need to have USD on the **Currencies** page in [!INCLUDE [prod_short](includes/prod_short.md)] and the appropriate exchange rate.

When you enable the connection to [!INCLUDE[cds_long](includes/cds_long_md.md)], [!INCLUDE [prod_short](includes/prod_short.md)] adds its local currency to the **Currency** entity in [!INCLUDE[cds_long](includes/cds_long_md.md)] with the exchange rate from the **Currency Factor** field on the **Currency Exchange Rates** page.

Currency synchronization is unidirectional, from [!INCLUDE [prod_short](includes/prod_short.md)] to [!INCLUDE [!INCLUDE[cds_long](includes/cds_long_md.md)], monetary amounts convert and synchronize as follows:

* Amounts in the [!INCLUDE[cds_long](includes/cds_long_md.md)] base currency convert to the [!INCLUDE [prod_short](includes/prod_short.md)] local currency based on the latest exchange rate synchronized from [!INCLUDE [prod_short](includes/prod_short.md)].
* Amounts in the [!INCLUDE [prod_short](includes/prod_short.md)] local currency synchronize with the [!INCLUDE [prod_short](includes/prod_short.md)] local currency in one of the other (non-base) currencies in [!INCLUDE[cds_long](includes/cds_long_md.md)].

## What happens when you copy a company

You can safely copy companies that integrate with [!INCLUDE[cds_long](includes/cds_long_md.md)] or [!INCLUDE[crm_md](includes/crm_md.md)]. Copying companies helps reduce the risk of data inconsistencies and can save you valuable time. To learn more about copying companies, go to [Copy a company](about-new-company.md#copy-a-company).

[!INCLUDE [dataverse-copy-company](includes/dataverse-copy-company.md)]

## Related information

[Data Ownership Models](admin-cds-company-concept.md)  
<!--needs to be removed as this is moved to dev-itpro docs[Walkthrough: Customizing an Integration with Dataverse](\dynamics365\business-central\dev-itpro\administration\administration-custom-cds-integration) -->

[!INCLUDE[footer-include](includes/footer-banner.md)]
