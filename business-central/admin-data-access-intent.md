---
title: Manage Database Access Intent
description: Manage database access intent for reports, API pages, and queries in Business Central to use read-only replicas and reduce the load on the primary database.
author: jswymer

ms.topic: how-to
ms.devlang: al
ms.search.form: 9880
ms.date: 11/10/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# Manage database access intent

As a super user or administrator, you can change the database access intent on reports, pages of the type API, and queries to improve performance of the service.

## Understand database access intent

[!INCLUDE[prod_short](includes/prod_short.md)] can be set up to use read-only replicas of the primary (read-write) database. Using the database replica reduces the load on the primary database. In some cases, it will also improve the performance when viewing data in the client. Replicas are beneficial for objects, like reports, queries, and API pages, that are used for viewing data only, not modifying data.

When objects run, the database access intent determines whether to use a read-only replica, if one is available, or the primary database. Reports, API pages, and queries are developed with a predefined database access intent (see [DatabaseAccessIntent property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataaccessintent-property)).

The **Database Access Intent List** page lets you override the predefined database access intent for objects when they're run.

In database terms, this feature is commonly known as *read scale-out*. For more information about read-scale out and data access intent in [!INCLUDE[prod_short](includes/prod_short.md)], see [Utilizing Read Scale-Out for Better Performance](/dynamics365/business-central/dev-itpro/administration/database-read-scale-out-overview) in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and Administration help.

## Change the database access intent

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Database Access Intent List**, and then choose the related link.

    The page lists all reports, pages, and queries. The **Access Intent** column includes one of the following values:

    |**Setting**|**Description**|  
    |------------|-------------|  
    |**Default**|Indicates that the object uses the predefined database access intent.|
    |**Allow Write**|Sets the object to use the primary database, where it can read or write data according to its implementation and the user's permissions.|
    |**Read Only**|Allows the object to use a read-only database replica, if one is available. Use this setting for objects that only read data. If read scale-out isn't supported, the primary database is used instead.|

1. Choose the **Edit List** action.

1. On the **Edit - Database Access Intent List** page, change the **Access Intent** field for the objects.

    > [!NOTE]
    > The list also includes ordinary pages, such as **Customer Card**. Changing the access intent isn't a way to make pages read-only or change users' permissions.

## Related information
[Business Functionality](across-business-functionality.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)    

## Start a free trial

[!INCLUDE[prod_short](includes/free_trial_md.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
