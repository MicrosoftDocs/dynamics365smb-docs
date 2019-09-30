---
title: Manual Synchronization of Table Mappings | Microsoft Docs
description: The synchronization copies data between Dynamics 365 Sales entries and Business Central to keep both systems up-to-date.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.date: 10/01/2019
ms.author: bholtorf

---

# Manually Synchronize Table Mappings
An integration table mapping associates a [!INCLUDE[d365fin](includes/d365fin_md.md)] table (record type), such as customer, with a [!INCLUDE[crm_md](includes/crm_md.md)] entity, such as an account. Synchronizing an integration table mapping enables you to synchronize data in all records of the [!INCLUDE[d365fin](includes/d365fin_md.md)] table and [!INCLUDE[crm_md](includes/crm_md.md)] entity that are coupled. Additionally, depending on the configuration of the table mapping, synchronization can create and couple new records in the destination solution for uncoupled records in the source.  

Manually synchronizing integration table mappings can be useful during the initial set up of an integration, and when diagnosing synchronization errors.  

This article describes three methods for manually synchronizing integration table mappings. Each method provides a different level of synchronization.

## Run a Full Synchronization
A full synchronization runs all the default integration synchronization jobs for synchronizing [!INCLUDE[d365fin](includes/d365fin_md.md)] records and [!INCLUDE[crm_md](includes/crm_md.md)] entities, as defined on the **Integration Table Mappings** page. 

A full synchronization performs the following operations For [!INCLUDE[d365fin](includes/d365fin_md.md)] or [!INCLUDE[crm_md](includes/crm_md.md)] records that are:

* Not coupled, a new matching record will be created and coupled in the opposing solution.
Whether and where a record gets created depends on the synchronization direction. For example, when synchronizing data from [!INCLUDE[d365fin](includes/d365fin_md.md)] customers to [!INCLUDE[crm_md](includes/crm_md.md)] accounts, if there is a customer that is not coupled to an account, then a new account will be automatically added in [!INCLUDE[crm_md](includes/crm_md.md)] and coupled to the customer in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The opposite holds true when the synchronization direction is from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)]. For each account that is not already coupled to a customer, a new matching customer will be created in [!INCLUDE[d365fin](includes/d365fin_md.md)] and coupled to the account in [!INCLUDE[crm_md](includes/crm_md.md)].  

     > [!NOTE]  
     >  To achieve this, the full synchronization operation temporarily clears the **Synch. Only Coupled Records** option on the integration table mapping that is used by the synchronization job. At the end of the full synchronization process, you will be prompted whether you want to keep this option cleared for all jobs.  

* Coupled, the synchronization direction (for example, from [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)] or from [!INCLUDE[crm_md](includes/crm_md.md)]to [!INCLUDE[d365fin](includes/d365fin_md.md)]) is predetermined by the integration table mappings. For more information, see [Standard Sales Entity Mapping for Synchronization](admin-synchronizing-business-central-and-sales.md#standard-sales-entity-mapping-for-synchronization).  

The jobs are run in the following order to avoid coupling dependencies between entities.  

1.  CURRENCY - Dynamics 365 Sales synchronization job  
2.  SALEPEOPLE - Dynamics 365 Sales synchronization job  
3.  UNITOFMEASURE - Dynamics 365 Sales synchronization job  
4.  CUSTOMER - Dynamics 365 Sales synchronization job  
5.  CONTACTS - Dynamics 365 Sales synchronization job  
6.  RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job  
7.  ITEM-PRODUCT - Dynamics 365 Sales synchronization job  

> [!IMPORTANT]  
>  You typically only use the full synchronization when you initially set up integration between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] and only one of solutions contains data, which you want to copy to the other solution. A full synchronization can be useful in a demonstration environment. Because the full synchronization automatically creates and couples records between the solutions, it makes it faster to start working with synchronizing data between records. On the other hand, you should only run a full synchronization if you want a record in [!INCLUDE[d365fin](includes/d365fin_md.md)] for each record in [!INCLUDE[crm_md](includes/crm_md.md)] for the given table mappings. Otherwise, you can have unwanted or duplicate records in either [!INCLUDE[d365fin](includes/d365fin_md.md)] or [!INCLUDE[crm_md](includes/crm_md.md)].  

### See the process for a full synchronization
> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2085502]

### To run a full synchronization  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft Dynamics 365 Sales Connection Setup**, and then choose the related link.
2.  Choose the **Run Full Synchronization** action, and then choose the **Yes** button.  
3.  When the full synchronization is completed, you can specify whether to allow scheduled synchronization jobs to create new records.  

    If you want all synchronization jobs to create new records in the destination for uncoupled records in the source, choose **Yes**. This sets the **Synch. Only Coupled Records** field on the table mappings that are used by the synchronization jobs.  

    If you want synchronization jobs to run as they did before the full synchronization with regard to creating new records, choose **No**. This sets the **Synch. Only Coupled Records** field to the setting it had before the full synchronization.  

You can view the results of the full synchronization on the **Integration Synchronization Jobs** page. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).  

## Synchronizing All Modified Records
You can use the **Microsoft Dynamics 365 Sales Connection Setup** page to synchronize changes to data in all integration table mappings. This is similar to a full synchronization. It will synchronize data in all coupled records in the [!INCLUDE[d365fin](includes/d365fin_md.md)] tables and [!INCLUDE[crm_md](includes/crm_md.md)] entities that are defined in the table mappings. By default, only records that have been modified since the last time they were synchronized will be synchronized. The table mappings are synchronized in the following order to avoid coupling dependencies between the entities:  

1.  CURRENCY - Dynamics 365 Sales synchronization job  
2.  SALEPEOPLE - Dynamics 365 Sales synchronization job  
3.  UNITOFMEASURE - Dynamics 365 Sales synchronization job  
4.  CUSTOMER - Dynamics 365 Sales synchronization job  
5.  CONTACTS - Dynamics 365 Sales synchronization job  
6.  RESOURCE-PRODUCT \- Dynamics 365 Sales synchronization job  
7.  ITEM-PRODUCT - Dynamics 365 Sales synchronization job  

You can view the results of the synchronization on the **Integration Synchronization Jobs** page. For more information, see [View the Status of a Synchronization](admin-how-to-view-synchronization-status.md).  

> [!TIP]  
>  By modifying the integration table mapping in advance, you can configure the synchronization with filters to control which records are synchronized, or configure it to create new records in the destination solution for uncoupled records in the source. For more information, see [Modify Table Mappings for Synchronization](admin-how-to-modify-table-mappings-for-synchronization.md).

### To synchronize records for all tables  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft Dynamics 365 Sales Connection Setup**, and then choose the related link.
2.  Choose the **Synchronize Modified Records** action, and then choose **Yes**.  

## Synchronize Individual Table Mappings
You can use the **Integration Table Mappings** page to run a synchronization job specific table mappings. This will synchronize data in all coupled records in the [!INCLUDE[d365fin](includes/d365fin_md.md)] table and [!INCLUDE[crm_md](includes/crm_md.md)] entity that are defined by the table mapping. By default, only records that have been modified since the last time they were synchronized will be synchronized.  

By modifying the integration table mapping in advance, you can configure the synchronization job to create new records in the destination solution for uncoupled records in the source.

### To synchronize records of an integration table mapping  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.
2.  Choose the **Synchronize Modified Records** action, and then choose **Yes**.  

## See Also  
[Synchronizing Business Central and Dynamics 365 Sales](admin-synchronizing-business-central-and-sales.md)   
[Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md)   
