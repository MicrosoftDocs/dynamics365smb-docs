---
title: Data ownership models for synchronization
description: Companies are both a legal and business constructs, and they are used to secure and visualize business data.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: CDS, Dataverse, integration, sync
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Data ownership models for synchronization

[!INCLUDE[prod_short](includes/cds_long_md.md)] requires that you specify an owner for the data you store. For more information, see [Types of tables](/powerapps/maker/data-platform/types-of-entities) in the Power Apps documentation. When you set up integration between [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] you must choose the **User or team** ownership for records that are synchronized. Actions that can be performed on these records can be controlled on a user level. <!--We recommend the Team ownership model because it makes it easier to manage ownership for multiple people.NO LONGER TRUE IN DATAVERSE-->

## Team Ownership
In [!INCLUDE[prod_short](includes/prod_short.md)], a company is a legal and business table that offers ways to secure and visualize business data. Users always work in the context of a company. The closest that [!INCLUDE[prod_short](includes/cds_long_md.md)] comes to this concept is the business unit table, which does not have legal or business implications.

Because business units lack legal and business implications, you cannot force a one-to-one (1:1) mapping to synchronize data between a company and a business unit, either one-way or bi-directional. To make synchronization possible, when you enable synchronization for a company in [!INCLUDE[prod_short](includes/prod_short.md)], the following happens in [!INCLUDE[prod_short](includes/cds_long_md.md)]:

* We create a company table that is equivalent to the company table in [!INCLUDE[prod_short](includes/prod_short.md)]. The name of the company is suffixed with "BC Company ID." For example, Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* We create a default business unit that has the same name as the company. For example, Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* We create separate owner team with the same name as the company and associate it with the business unit. The name of the team is prefixed with "BCI -." For example, BCI - Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Records that are created and synchronized to [!INCLUDE[prod_short](includes/cds_long_md.md)] are assigned to the "BCI Owner" team that is linked to the business unit.

> [!NOTE]
> If you rename a company in [!INCLUDE[prod_short](includes/prod_short.md)], the names of the company, business, and team that we create automatically in [!INCLUDE[prod_short](includes/cds_long_md.md)] are not updated. Because only the company ID is used for integration, this does not affect synchronization. If you want the names to match you must update the company, business unit, and team in [!INCLUDE[prod_short](includes/cds_long_md.md)].

The following image shows an example of this data setup in [!INCLUDE[prod_short](includes/cds_long_md.md)].

![The root business unit is on top, the teams are in the center, and then the companies are at the bottom.](media/cds_bu_team_company.png)

In this configuration, records that are related to the Cronus US company will be owned by a team that is linked to the Cronus US business unit in [!INCLUDE[prod_short](includes/cds_long_md.md)]. Users who can access that business unit through a security role that is set to business unit–level visibility in [!INCLUDE[prod_short](includes/cds_long_md.md)] can now see those records. The following example shows how to use teams to provide access to those records.

* The Sales Manager role is assigned to members of the Cronus US Sales team.
* Users who have the Sales Manager role can access account records for members of the same business unit.
* The Cronus US Sales team is linked to the Cronus US business unit that was mentioned earlier. Members of the Cronus US Sales team can see any account that is owned by the Cronus US user, which would have come from the Cronus US company table in [!INCLUDE[prod_short](includes/prod_short.md)].

However, the 1:1 mapping between business unit, company, and team is just a starting point, as shown in the following image.

![The security role controls data visibility.](media/cds_bu_team_company_2.png)

In this example, a new EUR (Europe) root business unit is created in [!INCLUDE[prod_short](includes/cds_long_md.md)] as the parent for both Cronus DE (Gernamy) and Cronus ES (Spain). The EUR business unit is not related to synchronization. However, it can give members of the EUR Sales team access to account data in both Cronus DE and Cronus ES by setting the data visibility to **Parent/Child BU** on the associated security role in [!INCLUDE[prod_short](includes/cds_long_md.md)].

Synchronization determines which team should own records. This is controlled by the **Default owning team** field on the BCI row. When a BCI record is enabled for synchronization we automatically create the associated business unit and owner team (if it doesn't already exist), and set the **Default owning team** field. When synchronization is enabled for an table, administrators can change the owning team, but a team must always be assigned.

> [!NOTE]
> Records become read-only after a company is added and saved, so be sure to choose the correct company.

## Choosing a different business unit
You can change the business unit selection if you are using the Teams ownership model. If you use the Person ownership model, the default business unit is always selected. 

If you choose another business unit, for example, one that you created earlier in [!INCLUDE[prod_short](includes/cds_long_md.md)], it will keep its original name. That is, it will not be suffixed with the company ID. We will create a team that does use the naming convention.

When changing a business unit, you can choose only the business units that are one level below the root business unit.

## Person Ownership
If you choose the Person ownership model you must specify each salesperson who will own new records. The business unit and team are created as described in the [Team Ownership](admin-cds-company-concept.md#team-ownership) section.

The default business unit is used when the Person ownership model is chosen, and you cannot choose another business unit. The team that is associated with the default business unit will own records for common tables, such as the Product table, that are not related to specific salespersons.

When you couple salespersons in [!INCLUDE[prod_short](includes/prod_short.md)] to users in [!INCLUDE[prod_short](includes/cds_long_md.md)], [!INCLUDE[prod_short](includes/prod_short.md)] will add the user to the default team in [!INCLUDE[prod_short](includes/cds_long_md.md)]. You can verify that users are added by looking at the **Default Team Member** column on the **Users - Common Data Service** page. If the user is not added, you can add them manually by using the **Add Coupled Users to Team** action. For more information, see [Synchronizing Data in Business Central with Dataverse](admin-synchronizing-business-central-and-sales.md).

## Related information
[About [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-common-data-service.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
