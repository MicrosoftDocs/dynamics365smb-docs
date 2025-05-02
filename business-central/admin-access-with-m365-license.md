---
title: Business Central Access with Microsoft 365 licenses
description: Learn how users can get access to Business Central data, for example in Microsoft Teams chats and channels, with only a Microsoft 365 license, but no Business Central license.
author: mikebc
ms.author: mikebc 
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: overview
ms.date: 08/12/2024
ms.custom: bap-template
ms.search.keywords: License, access, Microsoft 365, collaborate, collaboration, Teams, Microsoft Teams
ms.search.form: 1978
---

# Business Central access with Microsoft 365 licenses

[!INCLUDE[prod_short](includes/prod_short.md)] users are assigned a Dynamics 365 Business Central license that allows them to view, modify and act on their business data from any user interface. For all other employees across the organization that only need to occasionally view data, Business Central offers access through Microsoft 365.  

When an organization has both a Dynamics 365 Business Central and Microsoft 365 subscription, administrators can configure environments to enable access with Microsoft 365 licenses, and choose exactly which tables and other objects this category of user will have access to. When configured, employees that have a Microsoft 365 license but no [!INCLUDE [prod_short](includes/prod_short.md)] license can view [!INCLUDE [prod_short](includes/prod_short.md)] records that are shared with them in Microsoft Teams chat and channels.

## Why enable access with Microsoft 365 licenses  

- Unlock master data that every employee across the organization should have access to.

- Empower departments that don’t run on [!INCLUDE [prod_short](includes/prod_short.md)] to self-serve, by accessing key data needed to successfully perform their tasks, eliminating the need for continually requesting data from others.

- Increase collaboration efficacy so that tasks and projects that span across departments complete on time, by eliminating the friction that is typically associated with access denied errors due to licensing.

- Increase team performance so that people can make data-driven decisions that are inclusive of everyone in the group, even if they don’t work in [!INCLUDE [prod_short](includes/prod_short.md)].

- Meet licensing budget targets by assigning licenses that progressively match employee needs, with Microsoft 365 licenses for read-only access, Dynamics 365 Business Central Team Member licenses for limited write access, and Dynamics 365 Business Central Essentials or Premium for full write access.

- Improve data security by reducing the need for pasting screen snippets of business data outside of data governance boundaries.

## Use rights

When a person accesses [!INCLUDE [prod_short](includes/prod_short.md)] with a Microsoft 365 license, the license entitles the user to read (but not write) [!INCLUDE [prod_short](includes/prod_short.md)] data through a simplified user interface in Microsoft Teams. This section explains these use rights and limitations that help you plan how to configure and make the most out of this capability. For more information on this license type compared to other [!INCLUDE [prod_short](includes/prod_short.md)] licenses, consult the [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).
 
### Client access

Users are entitled to access [!INCLUDE [prod_short](includes/prod_short.md)] data in Microsoft Teams. The following table summarizes which of the different methods of accessing the [!INCLUDE [prod_short](includes/prod_short.md)] service are allowed with this license.

|Client accessing the Business Central service |Access|
|-|-|
|Business Central app for Microsoft Teams|![Yes](media/check.png)|
|Business Central Web client |![No](media/x-icon.png ) |
|Business Central mobile apps|![No](media/x-icon.png )|
|Business Central APIs|![No](media/x-icon.png )|
|Business Central integrations with other Office applications|![No](media/x-icon.png )|
|Business Central embedded in any other applications |![No](media/x-icon.png )|

### Data access

Users are entitled to read table data but can't modify, create or delete records. The [!INCLUDE [prod_short](includes/prod_short.md)] platform automatically prevents writing to any data tables.  

### Use of objects

Access with Microsoft 365 licenses doesn't restrict which Business Central objects or object ranges can be accessed. Users are entitled to access the Microsoft base application and any extensions such as customizations and add-on apps.

## Simplified user interface

Users are entitled to a reduced set of features and functions provided by [!INCLUDE [prod_short](includes/prod_short.md)] in Microsoft Teams. The tables below indicate noteworthy features. This isn't an exhaustive list and is subject to change.

Features of the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams:

|Feature  |Available|
|-|-|
|View [!INCLUDE [prod_short](includes/prod_short.md)] cards|![Yes](media/check.png)|
|View card details |![Yes](media/check.png) |
|Pin card details as a tab |![Yes](media/check.png)|
|View [!INCLUDE [prod_short](includes/prod_short.md)] tabs|![Yes](media/check.png)|
|Add a [!INCLUDE [prod_short](includes/prod_short.md)] tab|![No_](media/x-icon.png )|
|Search for business contacts |![No](media/x-icon.png )|
|Paste and share a link preview as a card|![No](media/x-icon.png )|

Functions of the [!INCLUDE [prod_short](includes/prod_short.md)] client embedded in Teams:

|Function |Available|Example functions|
|-|-|-|
|Data manipulation system actions |![No](media/x-icon.png )|Edit, Create, Delete|
|Basic functions in lists|![Yes](media/check.png)|Search, sort, change layout|
|Advanced functions in lists|![No](media/x-icon.png )|Filter pane, views|
|Drill down from list to card |![Yes](media/check.png)||
|Access data from related tables|![No](media/x-icon.png )|FactBox pane, field drilldown, peek, look up |
|Actions|![No](media/x-icon.png )|Action bar, action menus, page notification actions|
|System-wide shortcuts|![No](media/x-icon.png )|My Settings, Role Explorer, Tell Me search  |
|Copy|![Yes](media/check.png)|Copy rows, copy field value, copy link to page|
|UI customization|![No](media/x-icon.png )|Personalize| 
|Inline customization|![Yes](media/check.png)|Resize column, Expand/Collapse, Show more |
|Data sharing |![No](media/x-icon.png )|Open or Edit in Excel, Share to Teams|
|Inline user assistance|![Yes](media/check.png) |Tooltips, links to documentation|
|Advanced user assistance |![No](media/x-icon.png )|Page and field teaching tips, Help pane|

## Minimum requirements

This section describes the minimum requirements that must be met for your organization to enable access with Microsoft 365 licenses, and for individual Microsoft Teams users to access [!INCLUDE [prod_short](includes/prod_short.md)] data without a [!INCLUDE [prod_short](includes/prod_short.md)] license.

### Requirements to enable access

- [!INCLUDE [prod_short](includes/prod_short.md)] online (SaaS).

### Requirements for individual users to access data in Teams

- Data must be accessed using the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams. Users must have the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams installed and must use one of the supported Teams clients. Get a list of Teams clients supported by [!INCLUDE [prod_short](includes/prod_short.md)] in [Minimum Requirements for Using Business Central](product-requirements.md#teams).

- Users must be internal to the organization, meaning that a user identity originates from the same home tenant where [!INCLUDE [prod_short](includes/prod_short.md)] is deployed and where access is enabled. External identities aren't supported. [!INCLUDE [prod_short](includes/prod_short.md)] automatically prevents access to guests.

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

- The organization must have at least one other user that is assigned a Dynamics 365 Business Central license.

## Next steps

- Get an understanding of the user access flow to help plan your approach and configuration of Business Central to match the business needs. Learn more in [User Access Flow](admin-access-with-m365-license-flow.md).
- Set up your environment and users for access with with Microsoft 365 licenses. Learn more in [Set Up Access with Microsoft 365 Licenses ](admin-access-with-m365-license-setup.md).
- For troubleshooting tips, visit [Business Central troubleshooting](/troubleshoot/dynamics-365/business-central/welcome-business-central).

## Related information

[Business Central and Microsoft Teams Integration](across-teams-overview.md)  
