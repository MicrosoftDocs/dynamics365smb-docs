---
title: Manage database access intent in Business Central
description: Change the database access intent for reports, API pages, and queries.
author: jswymer

ms.topic: how-to
ms.devlang: al
ms.search.form: 9880
ms.date: 04/01/2021
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Managing Database Access Intent

As a super user or administrator, you can change the database access intent on reports, pages of the type API, and queries to improve performance of the service.

## Overview

[!INCLUDE[prod_short](includes/prod_short.md)] can be set up to use read-only replicas of the primary (read-write) database. Using the database replica reduces the load on the primary database. In some cases, it will also improve the performance when viewing data in the client. Replicas are beneficial for objects, like reports, queries, and API pages, that are used for viewing data only, not modifying data.

When objects run, the database access intent determines whether to use a read-only replica, if one is available, or the primary database. Reports, API pages, and queries are developed with a predefined database access intent (see [DatabaseAccessIntent property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataaccessintent-property)).

The **Database Access Intent List** page lets you override the predefined database access intent for objects when they're run.

In database terms, this feature is commonly known as *read scale-out*. For more information about read-scale out and data access intent in [!INCLUDE[prod_short](includes/prod_short.md)], see [Utilizing Read Scale-Out for Better Performance](/dynamics365/business-central/dev-itpro/administration/database-read-scale-out-overview) in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and Administration help.

## To change the database access intent

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Database Access Intent List**, and then choose the related link.

    The page lists all reports, pages, and queries. The **Access Intent** column includes one of the following values:

    |**Setting**|**Description**|  
    |------------|-------------|  
    |**Default**|Indicates that the object uses the predefined database access intent.|
    |**Allow Write**|Sets the object to use the primary database, allowing the user to modify data.|
    |**Read Only**|Sets the object to use the database replica, which means that the user can only view data, not change data.|

2. Choose the **Edit List** action.

3. On the **Edit - Database Access Intent List** page, change the **Access Intent** field for the objects.

    > [!NOTE]
    > If an object that is editable, like the Customer Card, is set to **Read Only**, the primary database will still be used, regardless of the access intent, allowing users to make changes as normal.

## Related information
[Business Functionality](across-business-functionality.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)    

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
