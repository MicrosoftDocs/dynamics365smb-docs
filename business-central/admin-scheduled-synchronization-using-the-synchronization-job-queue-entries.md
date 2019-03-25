---
title: Synchronizing Business Central and Dynamics 365 for Sales | Microsoft Docs
description: Learn about synchronizing data between Business Central and Dynamics 365 for Sales.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.date: 03/20/2019
ms.author: bholtorf

---

# Scheduling a Synchronization between Business Central and Dynamics 365 for Sales
You can synchronize [!INCLUDE[d365fin](includes/d365fin_md.md)] with [!INCLUDE[crm_md](includes/crm_md.md)] on scheduled intervals by setting up jobs in the job queue. The synchronization jobs synchronize data in [!INCLUDE[d365fin](includes/d365fin_md.md)] records and [!INCLUDE[crm_md](includes/crm_md.md)] records that have been previously coupled together. Or for records that are not already coupled, depending on the synchronization direction and rules, the synchronization jobs can create and couple new records in the destination system. There are several synchronization jobs that are available out-of-the-box. You can view them on the **Job Queue Entries** page. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).
<!--
> [!Note]
> For the on-premeses version of [!INCLUDE[d365fin](includes/d365fin_md.md)], the synchronization jobs are run by codeunit **5339 Integration synch Job Runner**.--> 

## Synchronization Process  
Each synchronization job queue entry uses a specific integration table mapping that specifies which [!INCLUDE[d365fin](includes/d365fin_md.md)] table and [!INCLUDE[crm_md](includes/crm_md.md)] entity to synchronize. The table mappings also include some settings that control which records in the [!INCLUDE[d365fin](includes/d365fin_md.md)] table and [!INCLUDE[crm_md](includes/crm_md.md)] entity to synchronize.  

To synchronize data, [!INCLUDE[crm_md](includes/crm_md.md)] entity records must be coupled to [!INCLUDE[d365fin](includes/d365fin_md.md)] records. For example, a [!INCLUDE[d365fin](includes/d365fin_md.md)] customer must be coupled to a [!INCLUDE[crm_md](includes/crm_md.md)] account. You can set up couplings manually, before running the synchronization jobs, or let the synchronization jobs set up couplings automatically. The following list describes how data is synchronized between [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)] when you are using the synchronization job queue entries. For more information, see [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md). 

-   By default, only records in [!INCLUDE[d365fin](includes/d365fin_md.md)] that are coupled to records in [!INCLUDE[crm_md](includes/crm_md.md)] are synchronized. You can change the table mapping between a [!INCLUDE[crm_md](includes/crm_md.md)] entity and a [!INCLUDE[d365fin](includes/d365fin_md.md)] table so that the integration synchronization jobs will create new records in the destination database for each record in the source database that is not coupled. The new records are also coupled to the corresponding records in the source. For example, when you synchronize customers with [!INCLUDE[crm_md](includes/crm_md.md)] accounts, a new account record is created for each customer in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The new accounts are automatically coupled to customers in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Because the synchronization in this case is bidirectional, a new customer is created and coupled for each [!INCLUDE[crm_md](includes/crm_md.md)] account that is not already coupled.  

    > [!NOTE]  
    >  There are rules and filters that determine what data is synchronized. For more information, see [Synchronization Rules](admin-synchronizing-business-central-and-sales.md#synchronization-rules).

-   When new records are created in [!INCLUDE[d365fin](includes/d365fin_md.md)], the records use the either the template that is defined for the integration table mapping or the default template that is available for the record type. Fields are populated with data from [!INCLUDE[d365fin](includes/d365fin_md.md)] or [!INCLUDE[crm_md](includes/crm_md.md)] depending on the synchronization direction. For more information, see [How to: Modify Table Mappings for Synchronization](admin-how-to-modify-table-mappings-for-synchronization.md).  

-   With subsequent synchronizations, only records that have been modified or added after the last successful synchronization job for the entity will be updated.  

     New records in [!INCLUDE[crm_md](includes/crm_md.md)] are added in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If data in fields in [!INCLUDE[crm_md](includes/crm_md.md)] records has changed, the data is copied to the corresponding field in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

-   With bidirectional synchronization, the job synchronizes from [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)], and then from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)].

## Default Synchronization Job Queue Entries  
The following table describes the default synchronization jobs.  

|Job Queue Entry|Description|Direction|Integration Table Mapping|  
|---------------------|---------------------------------------|---------------|-------------------------------|  
|CONTACT - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] contacts with [!INCLUDE[d365fin](includes/d365fin_md.md)] contacts.|Bidirectional|CONTACT|  
|CURRENCY - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] transaction currencies with [!INCLUDE[d365fin](includes/d365fin_md.md)] currencies.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|CURRENCY|  
|CUSTOMER - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] accounts with [!INCLUDE[d365fin](includes/d365fin_md.md)] customers.|Bidirectional|CUSTOMER|  
|CUSTPRCGRP-PRICE - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] sales price lists with [!INCLUDE[d365fin](includes/d365fin_md.md)] customer price groups.| |CUSTOMER PRICE GROUPS-SALES PRICE LISTS|
|ITEM - PRODUCT - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] products with [!INCLUDE[d365fin](includes/d365fin_md.md)] items.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|ITEM-PRODUCT|
|POSTEDSALESINV-INV - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] invoices with [!INCLUDE[d365fin](includes/d365fin_md.md)] posted sales invoices.|From [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)]|INVOICES-POSTED SALES INVOICES|
|RESOURCE-PRODUCT - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] products with [!INCLUDE[d365fin](includes/d365fin_md.md)] resources.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|RESOURCE-PRODUCT|  
|SALESPEOPLE - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[d365fin](includes/d365fin_md.md)] salespeople with [!INCLUDE[crm_md](includes/crm_md.md)] users.|From [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)]|SALESPEOPLE|
|SALESPRC-PRODUCTPRICE - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] product prices with [!INCLUDE[d365fin](includes/d365fin_md.md)] sales prices.||PRODUCT PRICE-SALES PRICE|
|UNITOFMEASURE - Dynamics 365 for Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] unit groups with [!INCLUDE[d365fin](includes/d365fin_md.md)] units of measure.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|UNIT OF MEASURE|  
|Customer Statistics - Dynamics 365 for Sales synchronization|Updates [!INCLUDE[crm_md](includes/crm_md.md)] accounts with the latest [!INCLUDE[d365fin](includes/d365fin_md.md)] customer data. In [!INCLUDE[crm_md](includes/crm_md.md)], this information appears in **Business Central Account Statistics** quick view form of accounts that are coupled to [!INCLUDE[d365fin](includes/d365fin_md.md)] customers.<br /><br /> This data can also be updated manually from each customer record. For more information, see [How to: Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md). </BR></BR>**Note:**  This job queue entry is relevant only if the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [About the Business Central Integration Solution](admin-prepare-dynamics-365-for-sales-for-integration.md#about-the-business-central-integration-solution).|Not applicable.|Not applicable.|   

## To view the synchronization job log  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Synchronization Log**, and then choose the related link.
2.  If one or more error occurred for a synchronization job, the number of errors appears in the **Failed** column. To view the errors for the job, choose the number.  

    > [!TIP]  
    >  You can view all synchronization job errors by opening the synchronization job error log directly.

## To view the synchronization job log from the table mappings  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.
2.  In the **Integration Table Mappings** page, select an entry, and then choose **Integration Synch. Job Log**.  

## To view the synchronization error log  
* Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Synchronization Errors**, and then choose the related link.

## See Also  
[Synchronizing Data in Business Central and Dynamics 365 for Sales](admin-synchronizing-business-central-and-sales.md)  
[Manually Synchronize Table Mappings](admin-manual-synchronization-of-table-mappings.md)  
[Scheduling a Synchronization between Business Central and Dynamics 365 for Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  
[About Integrating Dynamics 365 Business Central with Dynamics 365 for Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  



