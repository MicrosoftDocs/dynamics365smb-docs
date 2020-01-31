---
title: Company and Business Unit Mapping | Microsoft Docs
description: Companies are both a legal and business constructs, and they are used to secure and visualize business data.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: CDS, Common Data Service, integration, sync
ms.date: 01/17/2020
ms.author: bholtorf

---

# Company and Business Unit Relationships
In [!INCLUDE[d365fin](includes/d365fin_md.md)], a company is a legal and business entity that offers ways to secure and visualize business data. Users always work in the context of a company. The closest that [!INCLUDE[d365fin](includes/cds_long_md.md)] comes to this concept is the business unit entity, which does not have legal or business implications.

Because business units lack legal and business implications, you cannot force a one-to-one (1:1) mapping to synchronize data between a company and a business unit, either one-way or bi-directional. To enable synchronization, Microsoft has introduced an entity in [!INCLUDE[d365fin](includes/cds_long_md.md)] that is named cdm_Company <!--what do we call this?-->. This entity is equivalent to the Company entity in [!INCLUDE[d365fin](includes/d365fin_md.md)]. To help ensure that records are synchronized in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)] we recommend the following setup for data in [!INCLUDE[d365fin](includes/cds_long_md.md)]:

* For each [!INCLUDE[d365fin](includes/d365fin_md.md)] Company record that is enabled for synchronization, an associated cdm_Company <!--Name?--> record is created.
* When a cdm_Company <!--Name?--> record is created and synchronization is enabled, a default business unit is created that has the same name. Although a default team is automatically created for that business unit, the business unit isn't used. <!--Is the company used instead?-->
* A separate owner team is created that has the same name <!--as what, but BU of Co?-->. It's also associated with the business unit.<!--to do what?-->
* By default, the owner of any record that is created and synchronized <!--I have replaced instances of "dual-write" (and derivations) with "synchronized." Hope that was correct...--> to [!INCLUDE[d365fin](includes/cds_long_md.md)] is set to the "DW Owner" <!--Name?--> team that is linked to the associated business unit.
* The following image shows an example of this data setup in [!INCLUDE[d365fin](includes/cds_long_md.md)].

<!--Image placeholder for Data setup in [!INCLUDE[d365fin](includes/cds_long_md.md)]-->

In this configuration, records that are related to the USMF <!--Name of the company in the diagram. Replace with ours.--> company will be owned by a team that is linked to the USMF <!--Name?--> business unit in [!INCLUDE[d365fin](includes/cds_long_md.md)]. Users who can access that business unit through a security role that is set to business unit–level visibility <!--where is this set? on the BU or the security role?--> can now see those records. The following example shows how to use teams to provide access to those records.

* The "Sales Manager" role is assigned to members of the "USMF Sales" <!--Name?--> team.
* Users who have the "Sales Manager" role can access any account records that are members of the same business unit that they are members of <!--should this be "as the users."-->.
* The "USMF Sales" team is linked to the USMF <!--Name?--> business unit that was mentioned earlier <!--USMF?-->. Members of the "USMF Sales" <!--Name?--> team can see any account that is owned by the "USMF DW" <!--Name?--> user, which would have come from the USMF <!--Name?--> Company entity in [!INCLUDE[d365fin](includes/d365fin_md.md)].

However, the 1:1 mapping between business unit, company, and team is just a starting point, as shown in the following image.

<!--Image placeholder for How teams can be used-->

In this example, a new "Europe" <!--Name?--> business unit is manually created in [!INCLUDE[d365fin](includes/cds_long_md.md)] as the parent for both DEMF <!--Name?--> and ESMF <!--Name?-->. This new root business unit is not related to synchronization. However, it can give members of the "EUR Sales" <!--Name?--> team access to account data in both DEMF <!--Name?--> and ESMF <!--Name?--> by setting the data visibility to **Parent/Child BU** on the associated security role.

Synchronization determines which team should own records. This is controlled by the **Default owning team** field on the cdm_Company <!--Name?--> record. When a cdm_Company <!--Name?--> record is enabled for synchronization, a plug-in automatically creates the associated business unit and owner team (if it doesn't already exist), and sets the **Default owning team** field. When synchronization is enabled for an entity, admins can change the owning team but cannot clear the field.

<!--Image placeholder for Default owning team field-->

## Company striping and bootstrapping
[!INCLUDE[d365fin](includes/cds_long_md.md)] integration brings company parity by using a company identifier to stripe data. In the following image, all company-specific entities are extended to have a many-to-one (N:1) relationship with the cdm_Company <!--Name?--> entity.

<!-- Image placeholder for N:1 relationship between a company-specific entity and the cdm_Company entity-->

Record values become read-only after a company is added and saved, so make sure that the correct company is chosen.
Only records that have company data are eligible for synchronization between the application and [!INCLUDE[d365fin](includes/cds_long_md.md)]. <!--Not sure what this means-->

## See Also
[About [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-common-data-service.md)