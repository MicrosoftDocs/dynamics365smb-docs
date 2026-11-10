---
title: Business Central Access with Microsoft 365 Licenses
description: Discover how users can view Business Central data in Microsoft Teams with only a Microsoft 365 license. Learn setup steps and requirements.
author: mikebc
ms.author: mikebc 
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: overview
ai-usage: ai-assisted
ms.date: 11/09/2026
ms.custom: bap-template
ms.search.keywords: License, access, Microsoft 365, collaborate, collaboration, Teams, Microsoft Teams
ms.search.form: 1978
---

# Business Central access with Microsoft 365 licenses

Users with a [!INCLUDE [prod_short](includes/prod_short.md)] license can view, modify, and act on their business data from any user interface. For other employees across your organization that only need to occasionally view data, [!INCLUDE [prod_short](includes/prod_short.md)] offers access through Microsoft 365.  

If your organization has both a [!INCLUDE [prod_short](includes/prod_short.md)] and a Microsoft 365 subscription, admins set up environments so users sign in with Microsoft 365 licenses but can access only specific tables and other objects. When configured, employees that have a Microsoft 365 license but no [!INCLUDE [prod_short](includes/prod_short.md)] license can view [!INCLUDE [prod_short](includes/prod_short.md)] records that are shared with them in Microsoft Teams chat and channels.

## Why enable access with Microsoft 365 licenses  

- Unlock master data that every employee across the organization should have access to.

- Empower departments that don’t run on [!INCLUDE [prod_short](includes/prod_short.md)] to self-serve, by accessing key data needed to successfully perform their tasks, eliminating the need for continually requesting data from others.

- Increase collaboration efficacy so that tasks and projects that span across departments complete on time, by eliminating the friction that is typically associated with access denied errors due to licensing.

- Increase team performance so that people can make data-driven decisions that are inclusive of everyone in the group, even if they don’t work in [!INCLUDE [prod_short](includes/prod_short.md)].

- Meet licensing budget targets by assigning licenses that match employee needs:

  - Microsoft 365 licenses for read-only access
  - Dynamics 365 Business Central Team Member licenses for limited write access
  - Dynamics 365 Business Central Essentials or Premium licenses for full write access.

- Improve data security by reducing the need for pasting screen snippets of business data outside of data governance boundaries.

## Use rights

When a person accesses [!INCLUDE [prod_short](includes/prod_short.md)] with a Microsoft 365 license, the license entitles the user to read (but not write) [!INCLUDE [prod_short](includes/prod_short.md)] data through a simplified user interface in Microsoft Teams. This section explains these use rights and limitations that help you plan how to configure and make the most out of this capability. Learn more about this license type compared to other [!INCLUDE [prod_short](includes/prod_short.md)] licenses in the [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).

### Client access

Users are entitled to access [!INCLUDE [prod_short](includes/prod_short.md)] data in Microsoft Teams. The following table summarizes which of the different methods of accessing the [!INCLUDE [prod_short](includes/prod_short.md)] service are allowed with this license.

|Client accessing the [!INCLUDE [prod_short](includes/prod_short.md)] service |Access|
|-|-|
|[!INCLUDE [prod_short](includes/prod_short.md)] app for Microsoft Teams|:::image type="icon" source="media/check.png"::: Yes|
|Business Central Web client |:::image type="icon" source="media/x-icon.png"::: No |
|[!INCLUDE [prod_short](includes/prod_short.md)] mobile apps|:::image type="icon" source="media/x-icon.png"::: No|
|[!INCLUDE [prod_short](includes/prod_short.md)] APIs|:::image type="icon" source="media/x-icon.png"::: No|
|[!INCLUDE [prod_short](includes/prod_short.md)] integrations with other Office applications|:::image type="icon" source="media/x-icon.png"::: No|
|[!INCLUDE [prod_short](includes/prod_short.md)] embedded in any other applications |:::image type="icon" source="media/x-icon.png"::: No|

### Data access

Users are entitled to read table data but can't modify, create, or delete records. The [!INCLUDE [prod_short](includes/prod_short.md)] platform automatically prevents writing to any data tables.  

### Use of objects

Access with Microsoft 365 licenses doesn't restrict which [!INCLUDE [prod_short](includes/prod_short.md)] objects or object ranges can be accessed. Users are entitled to access the Microsoft base application and any extensions such as customizations and add-on apps.

This entitlement doesn't grant access to every object or record. Assigned permission sets and security filters determine which data a user can read. They don't override the read-only restriction of Microsoft 365 access.

These use rights don't grant permission to every object or record. Administrators must assign permission sets that allow access to the relevant pages and table data. Security filters also apply. Assigning a permission set with write access doesn't override the read-only restriction of the Microsoft 365 license.

## Simplified user interface

Users are entitled to a reduced set of features and functions provided by [!INCLUDE [prod_short](includes/prod_short.md)] in Microsoft Teams. The following tables indicate noteworthy features. This list isn't exhaustive and is subject to change.

Features of the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams:

|Feature  |Available|
|-|-|
|View [!INCLUDE [prod_short](includes/prod_short.md)] cards|:::image type="icon" source="media/check.png"::: Yes|
|View card details |:::image type="icon" source="media/check.png"::: Yes |
|Pin card details as a tab |:::image type="icon" source="media/check.png"::: Yes|
|View [!INCLUDE [prod_short](includes/prod_short.md)] tabs|:::image type="icon" source="media/check.png"::: Yes|
|Add a [!INCLUDE [prod_short](includes/prod_short.md)] tab|:::image type="icon" source="media/x-icon.png"::: No|
|Search for business contacts |:::image type="icon" source="media/x-icon.png"::: No|
|Paste and share a link preview as a card|:::image type="icon" source="media/x-icon.png"::: No|

Functions of the [!INCLUDE [prod_short](includes/prod_short.md)] client embedded in Teams:

|Function |Available|Example functions|
|-|-|-|
|Data manipulation system actions |:::image type="icon" source="media/x-icon.png"::: No|Edit, Create, Delete|
|Basic functions in lists|:::image type="icon" source="media/check.png"::: Yes|Search, sort, change layout|
|Advanced functions in lists|:::image type="icon" source="media/x-icon.png"::: No|Filter pane, views|
|Drill down from list to card |:::image type="icon" source="media/check.png"::: Yes||
|Access data from related tables|:::image type="icon" source="media/x-icon.png"::: No|FactBox pane, field drilldown, peek, look up |
|Actions|:::image type="icon" source="media/x-icon.png"::: No|Action bar, action menus, page notification actions|
|System-wide shortcuts|:::image type="icon" source="media/x-icon.png"::: No|My Settings, Role Explorer, Tell Me search  |
|Copy|:::image type="icon" source="media/check.png"::: Yes|Copy rows, copy field value, copy link to page|
|UI customization|:::image type="icon" source="media/x-icon.png"::: No|Personalize| 
|Inline customization|:::image type="icon" source="media/check.png"::: Yes|Resize column, Expand/Collapse, Show more |
|Data sharing |:::image type="icon" source="media/x-icon.png"::: No|Open or Edit in Excel, Share to Teams|
|Inline user assistance|:::image type="icon" source="media/check.png"::: Yes |Tooltips, links to documentation|
|Advanced user assistance |:::image type="icon" source="media/x-icon.png"::: No|Page and field teaching tips, Help pane|

## Minimum requirements

This section explains the minimum requirements for your organization to use Microsoft 365 licenses, and for individual Microsoft Teams users to use [!INCLUDE [prod_short](includes/prod_short.md)] data without a [!INCLUDE [prod_short](includes/prod_short.md)] license.

### Requirements to enable access

- [!INCLUDE [prod_short](includes/prod_short.md)] online (SaaS).

### Requirements for individual users to access data in Teams

- Data must be accessed using the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams. Users must have the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams installed and must use one of the supported Teams clients. Get a list of Teams clients supported by [!INCLUDE [prod_short](includes/prod_short.md)] in [Minimum Requirements for Using Business Central](product-requirements.md#teams).

- Users must be internal to the organization. A user identity originates from the same home tenant where [!INCLUDE [prod_short](includes/prod_short.md)] is deployed and access is enabled. External identities aren't supported. [!INCLUDE [prod_short](includes/prod_short.md)] automatically prevents access to guests.

- Users must be assigned a Microsoft 365 license from one of the following plans.
  
  |Supported plan|Product ID |
  |-|-|
  |Microsoft 365 Business Basic|3b555118-da6a-4418-894f-7df1e2096870|
  |Microsoft 365 Business Standard|f245ecc8-75af-4f8e-b61f-27d8114de5f3|
  |Microsoft 365 Business Premium |cbdc14ab-d96c-4c30-b9f4-6ada7cdc1d46|
  |Microsoft 365 E3 |05e9a617-0261-4cee-bb44-138d3ef5d965 |
  |Microsoft 365 E5|06ebc4ee-1bb5-47dd-8120-11324bc54e06|
  |Microsoft 365 F1|50f60901-3181-4b75-8a2c-4c8e4c1d5a72|
  |Microsoft 365 F3|66b55226-6b4f-492c-910c-a3b7a3c9d993|
  |Office 365 E1|18181a46-0d4e-45cd-891e-60aabd171b4e|
  |Office 365 E2 |6634e0ce-1a9f-428c-a498-f84ec7b8aa2e|
  |Office 365 E3|6fd2c87f-b296-42f0-b197-1e91e994b900|
  |Office 365 E5|c7df2760-2c81-4ef7-b578-5b5392b571df|
  |Office 365 F2|131fd665-5752-4995-a628-bcba5c889745|
  |Office 365 F3|4b585984-651b-448a-9e53-3b10f069cf7f|
  |Microsoft Teams Essentials (Microsoft Entra Identity) |3ab6abff-666f-4424-bfb7-f0bc274ec7bc|
  |Microsoft Teams EEA|7e74bd05-2c47-404e-829a-ba95c66fe8e5|
  
  Most offers based on these plans are also supported. For example, if you subscribe to Microsoft 365 Business Premium (Nonprofit Staff Pricing), it's a specific offer for not-for-profit organizations based on the Microsoft 365 Business Premium plan, and is therefore supported.

  > [!NOTE]
  > Can't find your plan in the list? Microsoft is continually looking for feedback on how we can improve our service and expand our offering so that more customers can take advantage of this capability. Share your idea for which plans we should support next at  [https://aka.ms/bcIdeas](https://aka.ms/bcIdeas).

- Users must be assigned a Microsoft 365 license that has the Microsoft Teams app enabled in the list of apps for that license.

  |Supported apps|Service Plan ID|
  |-|-|
  |Microsoft Teams|57ff2da0-773e-42df-b2af-ffb7a2317929 |

- The organization must have at least one other user with a Dynamics 365 Business Central license.

## Next steps

- Get an understanding of the user access flow to help plan your approach and configuration of [!INCLUDE [prod_short](includes/prod_short.md)] to match the business needs. Learn more in [User Access Flow](admin-access-with-m365-license-flow.md).
- Set up your environment and users for access with Microsoft 365 licenses. Learn more in [Set Up Access with Microsoft 365 Licenses ](admin-access-with-m365-license-setup.md).
- Get troubleshooting tips if you run into problems. Learn more in [Business Central troubleshooting](/troubleshoot/dynamics-365/business-central/welcome-business-central).

## Related information

[Business Central and Microsoft Teams Integration](across-teams-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
