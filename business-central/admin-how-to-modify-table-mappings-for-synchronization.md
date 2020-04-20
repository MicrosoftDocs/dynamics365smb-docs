---
title: Mapping the Tables and Fields to Synchronize | Microsoft Docs
description: Learn how to map tables and fields for synchronizing data between Business Central and Common Data Service.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize, table mapping
ms.date: 04/20/2020
ms.author: bholtorf

---
# Mapping the Tables and Fields to Synchronize
The basis of synchronizing data in [!INCLUDE[d365fin](includes/d365fin_md.md)] with data in [!INCLUDE[d365fin](includes/cds_long_md.md)] is mapping the tables and fields that contain the data to each other. Mapping happens through integration tables. 

## Mapping Integration Tables
An integration table is a table in the [!INCLUDE[d365fin](includes/d365fin_md.md)] database that represents an entity, such as an account, in [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. Integration tables include fields that correspond to the fields in the table for the [!INCLUDE[cds_long_md](includes/cds_long_md.md)] entity. For example, the Account integration table connects to the Accounts entity in [!INCLUDE[cds_short_md](includes/cds_long_md.md)]. There must be a integration table mapping for each entity in [!INCLUDE [cds_short_md](includes/cds_short_md.md)] that you want to synchronize with data in [!INCLUDE[prodshort](includes/prodshort.md)].

When you create the connection between the apps, [!INCLUDE[d365fin](includes/d365fin_md.md)] sets up some default table and field mappings. You can change the table mappings if you want. For more information, see [Standard Entity Mapping for Synchronization](admin-synchronizing-business-central-and-sales.md#standard-entity-mapping-for-synchronization). If you have changed the default mappings and want to revert your changes, on the **[!INCLUDE[d365fin](includes/cds_long_md.md)] Connection Setup** page, choose **Use Default Synchronization Setup**.

> [!Note]
> If you are using an on-premises version of [!INCLUDE[d365fin](includes/d365fin_md.md)], the integration table mappings are stored in table 5335 Integration Table Mappings, and can be viewed and modified from page 5335 Integration Table Mappings. Complex mappings and synchronization rules are defined in codeunit 5341. 

### Synchronization Rules
An integration table mapping also includes rules that control how integration synchronization jobs synchronize records in a [!INCLUDE[d365fin](includes/d365fin_md.md)] table and an entity in [!INCLUDE[d365fin](includes/cds_long_md.md)]. <!--For examples of rules for an integration with Sales, see [Synchronization Rules](admin-synchronizing-business-central-and-sales.md#synchronization-rules). need to verify link -->

## Mapping Integration Fields
Mapping tables is only the first step. You must also map the fields on the tables. Integration field mappings link fields in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables with corresponding fields in [!INCLUDE[d365fin](includes/cds_long_md.md)], and determine whether to synchronize data in each table. The standard table mapping that [!INCLUDE[d365fin](includes/d365fin_md.md)] provides includes field mappings, but you can change those if you want. For more information, see [Viewing Entity Mappings](admin-synchronizing-business-central-and-sales.md#tip-for-admins-viewing-entity-mappings).

> [!Note]
> If you are using an on-premises version of [!INCLUDE[d365fin](includes/d365fin_md.md)], Integration field mappings are defined in table 5336 Integration Field Mapping.

### Handling Differences in Field Values
Sometimes the values in the fields that you want to map are different. For example, in [!INCLUDE[crm_md](includes/crm_md.md)] the language code for the United States is "U.S.," but in [!INCLUDE[d365fin](includes/d365fin_md.md)] it's "US." That means you must transform the value when you synchronize data. This happens through transformation rules that you define for the fields. You define transformation rules on the **Integration Table Mappings** page by choosing **Mapping**, and then **Fields**. Predefined rules are provided, but you can also create your own. For more information, see [Transformation Rules](across-how-to-set-up-data-exchange-definitions.md#transformation-rules).

### Handling Missing Option Values in Mapping
[!INCLUDE[d365fin](includes/cds_long_md.md)] contains option set fields that provide values that you can map to [!INCLUDE[d365fin](includes/d365fin_md.md)] fields of the type **Option** for automatic synchronization. During synchronization, non-mapped options are ignored and the missing options are appended to the related [!INCLUDE[d365fin](includes/d365fin_md.md)] table and added to the **CDS Option Mapping** system table to be handled manually later. For example, by adding the missing options in either product and then updating the mapping. For more information, see [Handling Missing Option Values](admin-cds-missing-option-values.md).

## Coupling Records
Coupling links records in [!INCLUDE[d365fin](includes/cds_long_md.md)] to records in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, accounts in [!INCLUDE[d365fin](includes/cds_long_md.md)] are typically coupled with customers in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Coupling records offers the following benefits:

* It makes synchronization possible.
* Users can open records in one business app from the other. This requires that the apps are already integrated.

Couplings can be set up automatically by using the synchronization jobs, or manually by editing the record in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Synchronizing Data in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-synchronizing-business-central-and-sales.md) and [Couple and Synchronize Records Manually](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings).

## Filtering Records  
If you do not want to synchronize all records for a specific entity in [!INCLUDE[d365fin](includes/cds_long_md.md)] or table in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can set up filters to limit the records that are synchronized. You set up filters on the **Integration Table Mappings** page.  

#### To filter records for synchronization  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.

2.  To filter the [!INCLUDE[d365fin](includes/d365fin_md.md)] records, set the **Table Filter** field.  

3.  To filter the [!INCLUDE[d365fin](includes/cds_long_md.md)] records, set the **Integration Table Filter** field.  

## Creating New Records  
By default, only records in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)] that are coupled will be synchronized by the integration synchronization jobs. You can set up table mappings so that new records will be created in the destination (for example, [!INCLUDE[d365fin](includes/d365fin_md.md)]) for each record in the source (for example, [!INCLUDE[d365fin](includes/cds_long_md.md)]) that is not already coupled.  

For example, the SALESPEOPLE - Dynamics 365 Sales synchronization job uses the table mapping SALESPEOPLE. The synchronization job copies data from user records in [!INCLUDE[d365fin](includes/cds_long_md.md)] to salesperson records in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you set up the table mapping to create new records, for every user in [!INCLUDE[d365fin](includes/cds_long_md.md)] that is not already coupled to a salesperson in [!INCLUDE[d365fin](includes/d365fin_md.md)], a new salesperson record is created in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

#### To create new records during synchronization  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.

2.  In the table mapping entry in the list, clear the **Synch. Only Coupled Records** field.  

## Using Configuration Templates on Table Mappings
You can assign configuration templates to table mappings to use for new records that are created in [!INCLUDE[d365fin](includes/d365fin_md.md)] or [!INCLUDE[d365fin](includes/cds_long_md.md)]. For each table mapping, you can specify a configuration template to use for new [!INCLUDE[d365fin](includes/d365fin_md.md)] records and another template to use new [!INCLUDE[d365fin](includes/cds_long_md.md)] records.  

If you install the default synchronization setup, most of the time, two configuration templates will be automatically created and used on the table mapping for [!INCLUDE[d365fin](includes/d365fin_md.md)] customers and [!INCLUDE[crm_md](includes/crm_md.md)] accounts: **CDSCUST** and **CDSACCOUNT**.  

-   **CDSCUST** is used to create and synchronize new customers in [!INCLUDE[d365fin](includes/d365fin_md.md)] based on an account in [!INCLUDE[crm_md](includes/crm_md.md)].  

     This template is created by copying an existing configuration template for customers in the application. The **CDSCUST** is created only if there is an existing configuration template and the **Currency Code** field in the template is blank. If a field in the configuration template contains a value, the value will be used instead of the value in the mapped field for the [!INCLUDE[d365fin](includes/cds_long_md.md)] account. For example, if the **Country/Region** field in an account in [!INCLUDE[d365fin](includes/cds_long_md.md)] contains *U.S.* and the **Country/Region** field in the configuration template is *GB*, then *GB* is used as the **Country/Region** for the customer in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

-   **CDSACCOUNT** creates and synchronizes new accounts in [!INCLUDE[d365fin](includes/cds_long_md.md)] based on an account in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

#### To specify configuration templates on a table mapping  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.

2.  In the table mapping entry in the list, in the **Table Config Template Code** field, choose to the configuration template to use for new records in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

3.  Set the **Int. Tbl. Config Template Code** field to the configuration template to use for new records in [!INCLUDE[d365fin](includes/cds_long_md.md)].

## See Also  
[About Integrating Dynamics 365 Business Central with [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-prepare-dynamics-365-for-sales-for-integration.md )   
[Synchronizing Business Central and [!INCLUDE[d365fin](includes/cds_long_md.md)]](admin-synchronizing-business-central-and-sales.md)   
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  
