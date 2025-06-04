---
title: Manual Synchronization of Table Mappings | Microsoft Docs
description: The synchronization copies data between Microsoft Dataverse tables and Business Central to keep both systems up-to-date.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Manually Synchronize Table Mappings


An integration table mapping associates a [!INCLUDE[prod_short](includes/prod_short.md)] table, such as customer, with a [!INCLUDE[prod_short](includes/cds_long_md.md)] table, such as account. Synchronizing an integration table mapping enables you to synchronize data in all records of the [!INCLUDE[prod_short](includes/prod_short.md)] table and [!INCLUDE[prod_short](includes/cds_long_md.md)] table that are coupled. Additionally, depending on the configuration of the table mapping, synchronization can create and couple new records in the destination solution for uncoupled records in the source.  

Manually synchronizing integration table mappings can be useful during the initial set up of an integration, and when diagnosing synchronization errors.  

This article describes three methods for manually synchronizing integration table mappings. Each method provides a different level of synchronization.

## Run a Full Synchronization
A full synchronization runs all the default integration synchronization jobs for synchronizing [!INCLUDE[prod_short](includes/prod_short.md)] records and [!INCLUDE[prod_short](includes/cds_long_md.md)] tables, as defined on the **Integration Table Mappings** page. 

A full synchronization performs the following operations For [!INCLUDE[prod_short](includes/prod_short.md)] or [!INCLUDE[prod_short](includes/cds_long_md.md)] records that are:

* Not coupled, a new matching row will be created and coupled in the opposing solution.
Whether and where a row gets created depends on the synchronization direction. For example, when synchronizing data from [!INCLUDE[prod_short](includes/prod_short.md)] customers to [!INCLUDE[prod_short](includes/cds_long_md.md)] accounts, if there is a customer that is not coupled to an account, then a new account will be automatically added in [!INCLUDE[prod_short](includes/cds_long_md.md)] and coupled to the customer in [!INCLUDE[prod_short](includes/prod_short.md)]. The opposite holds true when the synchronization direction is from [!INCLUDE[prod_short](includes/cds_long_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)]. For each account that is not already coupled to a customer, a new matching customer will be created in [!INCLUDE[prod_short](includes/prod_short.md)] and coupled to the account in [!INCLUDE[prod_short](includes/cds_long_md.md)].  

     > [!NOTE]  
     >  To achieve this, the full synchronization operation temporarily clears the **Synch. Only Coupled Records** option on the integration table mapping that is used by the synchronization job. At the end of the full synchronization process, you will be prompted whether you want to keep this option cleared for all jobs.  

* Coupled, the synchronization direction (for example, from [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[prod_short](includes/cds_long_md.md)] or from [!INCLUDE[prod_short](includes/cds_long_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)]) is predetermined by the integration table mappings. For more information, see [Standard Table Mapping for Synchronization](admin-synchronizing-business-central-and-sales.md#standard-table-mapping-for-synchronization).  

> [!IMPORTANT]  
>  You typically only use the full synchronization when you initially set up integration between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] and only one of solutions contains data, which you want to copy to the other solution. A full synchronization can be useful in a demonstration environment. Because the full synchronization automatically creates and couples records between the solutions, it makes it faster to start working with synchronizing data between records. On the other hand, you should only run a full synchronization if you want a row in [!INCLUDE[prod_short](includes/prod_short.md)] for each row in [!INCLUDE[prod_short](includes/cds_long_md.md)] for the given table mappings. Otherwise, you can have unwanted or duplicate records in either [!INCLUDE[prod_short](includes/prod_short.md)] or [!INCLUDE[prod_short](includes/cds_long_md.md)].  

### To run a full synchronization  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dataverse Connection Setup**, and then choose the related link.

    > [!NOTE]
    > If you want to run a full synchronization for tables through Dynamics 365 Sales, use the **Microsoft Dynamics 365 Sales Connection Setup** page instead.

2.  Choose the **Run Full Synchronization** action, and then choose the **Yes** button.  
3.  When the full synchronization is completed, you can specify whether to allow scheduled synchronization jobs to create new records.  

    If you want all synchronization jobs to create new records in the destination for uncoupled records in the source, choose **Yes**. This sets the **Synch. Only Coupled Records** field on the table mappings that are used by the synchronization jobs.  

    If you want synchronization jobs to run as they did before the full synchronization with regard to creating new records, choose **No**. This sets the **Synch. Only Coupled Records** field to the setting it had before the full synchronization.  

You can view the results of the full synchronization on the **Integration Synchronization Jobs** page. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).  

## Synchronizing All Modified Records
You can use the **Common Data Service Connection Setup** page to synchronize changes to data in all integration table mappings. This is similar to a full synchronization. It will synchronize data in all coupled records in the [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] tables that are defined in the table mappings. By default, only data that has been modified since the last synchronization will be synchronized. Synchronization jobs synchronize table mappings in the following order to avoid coupling dependencies between the tables:  

1.  CURRENCY  
2.  SALESPEOPLE  
3.  VENDOR  
4.  CUSTOMER  
5.  CONTACTS  

You can view the results of the synchronization on the **Integration Synchronization Jobs** page. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).  

> [!TIP]  
>  By modifying the integration table mapping in advance, you can create filters to control the data to synchronize, or configure mappings to create new data in the destination solution for uncoupled records or rows in the source. For more information, see [Modify Table Mappings for Synchronization](admin-how-to-modify-table-mappings-for-synchronization.md).

### To synchronize data for all tables  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft Dynamics 365 Sales Connection Setup**, and then choose the related link.
2.  Choose the **Synchronize Modified Records** action, and then choose **Yes**.  

## Synchronize Individual Table Mappings
You can use the **Integration Table Mappings** page to run a synchronization job for table mappings. This will synchronize data for all coupled records and rows in the [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] tables that are defined by the table mapping. By default, only data that has been modified since the last synchronization will be synchronized.  

### To synchronize records of an integration table mapping  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.
2.  Choose the **Synchronize Modified Records** action, and then choose **Yes**.  

## Related information  
[Synchronizing Business Central and Dynamics 365 Sales](admin-synchronizing-business-central-and-sales.md)   
[Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md)   


[!INCLUDE[footer-include](includes/footer-banner.md)]
