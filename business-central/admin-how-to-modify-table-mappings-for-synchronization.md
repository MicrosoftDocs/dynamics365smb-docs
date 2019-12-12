---
title: Modify Table Mappings for Synchronization | Microsoft Docs
description: Learn how to change the table mappings that are used when synchronizing data between Business Central and Dynamics 365 Sales.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize, table mapping
ms.date: 10/01/2019
ms.author: bholtorf

---
# Modify Table Mappings for Synchronization
An integration table mapping links a table in [!INCLUDE[d365fin](includes/d365fin_md.md)] to an integration table for the [!INCLUDE[crm_md](includes/crm_md.md)] entity, such as an account. For each entity in [!INCLUDE[crm_md](includes/crm_md.md)] that you want to synchronize with corresponding data in [!INCLUDE[d365fin](includes/d365fin_md.md)]], there must be a integration table mapping. An integration table mapping includes settings that control how integration synchronization jobs synchronize records in a [!INCLUDE[d365fin](includes/d365fin_md.md)] table and an entity in [!INCLUDE[crm_md](includes/crm_md.md)].  

<!--

## Coupling Records
Coupling links records in [!INCLUDE[crm_md](includes/crm_md.md)] to records in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, accounts in [!INCLUDE[crm_md](includes/crm_md.md)] are typically coupled with customers in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Coupling records offers the following benefits:

* It makes synchronization possible.
* Users can open records in one business app from the other. This requires that the [d365fin](includes/d365fin_md.md)] integration solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)].

Couplings can be set up automatically by using the synchronization jobs, or manually by editing the record in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Synchronizing Data in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)]](business-central/admin-synchronizing-business-central-and-sales.md) and [Couple and Synchronize Records Manually](business-central/admin-how-to-couple-and-synchronize-records-manually.md).

## Integration Tables and Table Mappings
An integration table is a table in the [!INCLUDE[d365fin](includes/d365fin_md.md)] database that represents an entity, such as an account, in [!INCLUDE[crm_md](includes/crm_md.md)]. Integration tables include fields that correspond to the fields that the entity has in [!INCLUDE[crm_md](includes/crm_md.md)], and connects the [!INCLUDE[d365fin](includes/d365fin_md.md)] table to the [!INCLUDE[crm_md](includes/crm_md.md)] entity. For example, the Account integration table connects to the Accounts entity in [!INCLUDE[crm_md](includes/crm_md.md)].

> [!Note]
> If you are using an on-premises version of [!INCLUDE[d365fin](includes/d365fin_md.md)], the integration table mappings are stored in table 5335 Integration Table Mappings, and can be viewed and modified from page 5335 Integration Table Mappings. Complex mappings and synchronization rules are defined in codeunit 5341. 

## Integration Field Mappings
A field mapping associates a field in a [!INCLUDE[crm_md](includes/crm_md.md)] entity record with a field in a [!INCLUDE[d365fin](includes/d365fin_md.md)] record. The mapping is used to determine which data to synchronize between [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)] records. The field mappings define which field in [!INCLUDE[d365fin](includes/d365fin_md.md)] corresponds to which field in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, a [!INCLUDE[d365fin](includes/d365fin_md.md)] customer includes some fields that are either not supported in [!INCLUDE[crm_md](includes/crm_md.md)] accounts, or you just do not want the data to be synchronized. Integration field mappings are defined in table 5336 Integration Field Mapping.

-->

## Filtering Records  
 If you do not want to synchronize all records for a specific entity in [!INCLUDE[crm_md](includes/crm_md.md)] or table in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can set up filters to limit the records that are synchronized. You set up filters on the **Integration Table Mappings** page.  

#### To filter records for synchronization  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.

2.  To filter the [!INCLUDE[d365fin](includes/d365fin_md.md)] records, set the **Table Filter** field.  

3.  To filter the [!INCLUDE[crm_md](includes/crm_md.md)] records, set the **Integration Table Filter** field.  

## Creating New Records  
 By default, only records in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] that are coupled will be synchronized by the integration synchronization jobs. You can set up table mappings so that new records will be created in the destination (for example, [!INCLUDE[d365fin](includes/d365fin_md.md)]) for each record in the source (for example, [!INCLUDE[crm_md](includes/crm_md.md)]) that is not already coupled.  

 For example, the SALESPEOPLE - Dynamics 365 Sales synchronization job uses the table mapping SALESPEOPLE. The synchronization job copies data from user records in [!INCLUDE[crm_md](includes/crm_md.md)] to salesperson records in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you set up the table mapping to create new records, for every user in [!INCLUDE[crm_md](includes/crm_md.md)] that is not already coupled to a salesperson in [!INCLUDE[d365fin](includes/d365fin_md.md)], a new salesperson record is created in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

#### To create new records during synchronization  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.

2.  In the table mapping entry in the list, clear the **Synch. Only Coupled Records** field.  

## Using Configuration Templates on Table Mappings
You can assign configuration templates to table mappings to use for new records that are created in [!INCLUDE[d365fin](includes/d365fin_md.md)] or [!INCLUDE[crm_md](includes/crm_md.md)]. For each table mapping, you can specify a configuration template to use for new [!INCLUDE[d365fin](includes/d365fin_md.md)] records and another template to use new [!INCLUDE[crm_md](includes/crm_md.md)] records.  

If you install the default synchronization setup, most of the time, two configuration templates will be automatically created and used on the table mapping for [!INCLUDE[d365fin](includes/d365fin_md.md)] customers and [!INCLUDE[crm_md](includes/crm_md.md)] accounts: **CRMCUST** and **CRMACCOUNT**.  

-   **CRMCUST** is used to create and synchronize new customers in [!INCLUDE[d365fin](includes/d365fin_md.md)] based on an account in [!INCLUDE[crm_md](includes/crm_md.md)].  

     This template is created by copying an existing configuration template for customers in the application. The **CRMCUST** is created only if there is an existing configuration template and the **Currency Code** field in the template is blank. If a field in the configuration template contains a value, the value will be used instead of the value in the mapped field for the [!INCLUDE[crm_md](includes/crm_md.md)] account. For example, if the **Country/Region** field in an account in [!INCLUDE[crm_md](includes/crm_md.md)] contains *U.S.* and the **Country/Region** field in the configuration template is *GB*, then *GB* is used as the **Country/Region** for the customer in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

-   **CRMACCOUNT** creates and synchronizes new accounts in [!INCLUDE[crm_md](includes/crm_md.md)] based on an account in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

#### To specify configuration templates on a table mapping  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.

2.  In the table mapping entry in the list, in the **Table Config Template Code** field, choose to the configuration template to use for new records in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

3.  Set the **Int. Tbl. Config Template Code** field to the configuration template to use for new records in [!INCLUDE[crm_md](includes/crm_md.md)].

## See Also  
[About Integrating Dynamics 365 Business Central with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md )   
[Synchronizing Business Central and Dynamics 365 Sales](admin-synchronizing-business-central-and-sales.md)   
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  
