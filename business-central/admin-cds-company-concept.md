---
title: Dataverse data ownership models for synchronization
description: Choose a data ownership model for Business Central and Dataverse synchronization, and learn how companies, business units, and teams control access.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: CDS, Dataverse, integration, sync
ms.date: 10/14/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
ai.usage: ai-assisted
---

# Choose a data ownership model for synchronization

When you set up synchronization between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[cds_long](includes/cds_long_md.md)], choose who owns new records in [!INCLUDE[cds_long](includes/cds_long_md.md)]. The ownership model works with security roles to control who can access synchronized data.

On the **Dataverse Connection Setup** page, the **Ownership Model** field offers two options:

* **Team**: Assign new records to the company's default owning team.
* **Person**: Assign new records to the [!INCLUDE[cds_long](includes/cds_long_md.md)] user coupled to the salesperson or purchaser on the source record.

These options apply to synchronized records in tables with **User or team** ownership, such as accounts and contacts. They don't change the ownership of organization-owned tables, such as the Product table. Learn more about table ownership in [Types of tables](/power-apps/maker/data-platform/types-of-entities).

## Companies, business units, and owner teams

In [!INCLUDE[prod_short](includes/prod_short.md)], users work in the context of a company. In [!INCLUDE[cds_long](includes/cds_long_md.md)], a *business unit* groups related business activities and helps define access to data. A business unit isn't a legal entity and doesn't have to represent a company.

When you enable synchronization for a company, the integration creates or reuses the following records in [!INCLUDE[cds_long](includes/cds_long_md.md)]:

* A company record in the integration's company table. Its name matches the [!INCLUDE[prod_short](includes/prod_short.md)] company name. Its **External ID** stores the [!INCLUDE[prod_short](includes/prod_short.md)] company ID separately.
* A business unit directly below the root business unit. Its generated name combines the company name and company ID, in the format `<CompanyName> (<CompanyID>)`.
* A separate owner team associated with that business unit. Its generated name uses the format `BCI - <BusinessUnitName>`.

The integration stores the default owning team on the company record. Both ownership models use this setup. If you select an existing business unit, the integration creates or reuses an owner team in that business unit and sets it as the company's default owning team.

The integration's owner team is separate from the default team that [!INCLUDE[cds_long](includes/cds_long_md.md)] automatically creates for each business unit.

> [!NOTE]
> If you rename a company in [!INCLUDE[prod_short](includes/prod_short.md)], the integration doesn't automatically rename its existing company, business unit, or owner team records in [!INCLUDE[cds_long](includes/cds_long_md.md)]. Synchronization identifies the company by its ID, so the name difference doesn't affect synchronization.

## Team ownership

With **Team** ownership, the company's default owning team owns new synchronized records in user and team-owned tables. Access to those records depends on the security roles assigned to users and teams.

For example, synchronized accounts for Cronus US are owned by its integration owner team in the Cronus US business unit. To give a separate Cronus US Sales team access to those accounts:

1. Create or select a Cronus US Sales owner team associated with the Cronus US business unit.
2. Assign the sales team a security role that grants **Read** access to the Account table at the **Business Unit** level.
3. Add the salespeople who need access to the sales team.

Members can then read the accounts owned by the integration team in that business unit. A role's name alone, such as Sales Manager, doesn't establish its access level.

### Access across a business-unit hierarchy

[!INCLUDE[cds_long](includes/cds_long_md.md)] has one root business unit. You can create a Europe business unit below the root and place Germany and Spain below Europe. A sales team associated with Europe can use a security role with **Read** access to accounts at the **Parent: Child Business Unit** level to read accounts in Europe, Germany, and Spain.

Synchronization determines which team should own records. This is controlled by the **Default owning team** field on the BCI row. When a BCI record is enabled for synchronization, [!INCLUDE[prod_short](includes/prod_short.md)] automatically creates the associated business unit and owner team if they don't already exist, and sets the **Default owning team** field. When synchronization is enabled for a table, administrators can change the owning team, but a team must always be assigned.

Learn more about access levels in [Security roles and privileges](/power-platform/admin/security-roles-privileges).

## Choose a different business unit

Before you enable synchronization, you can select an existing business unit in the **Coupled Business Unit** field on the **Dataverse Connection Setup** page. Selection is available for both **Team** and **Person** ownership. The field's selection action isn't available while data synchronization or virtual tables and events are enabled.

You can select only active business units directly below the root business unit. An existing business unit keeps its name without a company ID suffix. The integration creates or reuses an owner team named `BCI - <BusinessUnitName>` in the selected business unit.

Learn more about connection settings in [Connect to Dataverse](admin-how-to-set-up-a-dynamics-crm-connection.md).

## Person ownership

When you use **Person** ownership, new synchronized accounts and contacts go to the [!INCLUDE[cds_long](includes/cds_long_md.md)] user who works with the salesperson or purchaser on the source record. If you assign a salesperson or purchaser, link that person to a [!INCLUDE[cds_long](includes/cds_long_md.md)] user before synchronizing. An assigned salesperson or purchaser without a link causes a synchronization error.

If the source record doesn't have a salesperson or purchaser, the integration assigns the new record to the company's default owning team. Organization-owned tables, such as Product, stay organization-owned.

The assisted setup guide adds coupled users to the default owning team. During synchronization, the integration automatically adds coupled users to the default owning team only when the connection uses Microsoft 365 authentication and administrator authentication succeeds.

To check membership, use the **Default Team Member** column on the **Users - Dataverse** page. If a coupled user isn't a member, use **Add Coupled Users to Team** on the **Dataverse Connection Setup** page. Sign in with an administrator account when prompted.

Learn more about synchronization in [Synchronize data in Business Central with Microsoft Dataverse](admin-synchronizing-business-central-and-sales.md).

## Related information

[Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md)  
[Create or edit business units](/power-platform/admin/create-edit-business-units)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
