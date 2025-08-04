---
title: Mapping the tables and fields to synchronize
description: Learn how to map tables and fields for synchronizing data between Business Central and Microsoft Dataverse.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 08/07/2024
ms.custom: bap-template
ms.search.keywords: sales, crm, integration, sync, synchronize, table mapping
ms.service: dynamics-365-business-central
---
# Mapping the tables and fields to synchronize

The basis of synchronizing data is mapping the tables and fields in [!INCLUDE[prod_short](includes/prod_short.md)] with tables and columns in [!INCLUDE[prod_short](includes/cds_long_md.md)], so they can exchange the data. Mapping happens through integration tables.

## Mapping integration tables

An integration table is a table in the [!INCLUDE[prod_short](includes/prod_short.md)] database that represents a table, such as an account, in [!INCLUDE[cds_long_md](includes/cds_long_md.md)]. Integration tables include fields that correspond to columns in the [!INCLUDE[cds_long_md](includes/cds_long_md.md)] table. For example, the Account integration table connects to the Accounts table in [!INCLUDE[cds_short_md](includes/cds_long_md.md)]. There must be an integration table mapping for each table in [!INCLUDE[cds_short_md](includes/cds_short_md.md)] that you want to synchronize with data in [!INCLUDE[prod_short](includes/prod_short.md)].

When you create the connection between the apps, [!INCLUDE[prod_short](includes/prod_short.md)] sets up some default mappings. You can change the table mappings if you want. For more information, see [Standard Table Mapping for Synchronization](admin-synchronizing-business-central-and-sales.md#standard-table-mapping-for-synchronization). If you changed the default mappings and want to revert your changes, on the **Integration Table Mappings** page, choose **Use Default Synchronization Setup**.

> [!Note]
> If you are using an on-premises version of [!INCLUDE[prod_short](includes/prod_short.md)], the integration table mappings are stored in table 5335 Integration Table Mappings, where you can view and edit the mappings. Complex mappings and synchronization rules are defined in codeunit 5341.

> [!TIP]
> When a coupled record changes, [!INCLUDE [prod_short](includes/prod_short.md)] automatically synchronizes the data with Dataverse. Automatic synchronization is great in most cases. However, frequent changes to large amounts of coupled records in a table can slow down data synchronization.
>
> To avoid slow performance, on the **Integration Table Mappings** page, you can enable or disable event-based data synchronization for any table. By default, event-based synchronization is turned on so that existing integrations aren’t affected. Your administrator can turn it on or off for specific tables.

### Add table and field mappings to existing integration tables

[!INCLUDE [preview](includes/preview.md)]

On the **Integration Table Mappings** page, you can use the New Table Mapping action to add new table mappings to integration tables. The action starts the **Create new integration mappings** assisted setup guide, which helps you set up new integration table and field mappings.

The guide lets you map the tables in [!INCLUDE [prod_short](includes/prod_short.md)] with existing integration tables in Dataverse. You can also specify the Dataverse table's unique identifier in **Integration Table Unique Identifier Field Name** and the **Integration Table Modified on Field Name**, which are needed for data synchronization to work.

> [!NOTE]
> The lookup on the Table column shows all [!INCLUDE [prod_short](includes/prod_short.md)] tables, including custom tables, that aren't yet mapped. It excludes those that already exist on your Integration Table Mappings page. The lookup on the Integration Table column shows only Dataverse tables (AL Proxy Tables) that are part of out-of-the-box integrations. To add additional or custom Dataverse tables, you'll need help from a developer to create and deploy them through an extension.

The Advanced action opens extra table mapping settings that you can set up. In the **Advanced** section, the **Table Filter** field lets you specify filters for [!INCLUDE [prod_short](includes/prod_short.md)]. Use the **Integration Table Filter** field for Dataverse data to consider in data synchronization together with the configuration template codes in **Table Config. Template Code** and **Int. Tbl. Config. Code** to prefill missing data when new data comes from either application.

The guide also helps you specify the fields you want the new mapping to contain. You can match a [!INCLUDE [prod_short](includes/prod_short.md)] field in the **Field Name** column with a Dataverse field name in the **Integration Field Name** column. You can also specify a **Direction**, whether the field always has the same value in the **Constant** column, and whether validations or transformations need to be applied during field mapping.

> [!NOTE]
> To reduce errors, the lookup for the **Integration Table Field** column filters to a list of available fields. To map fields that the filters don't include, you'll need help from a developer.
>
> * Fields must be enabled.
> * You can't use the guide to map FlowField and FlowFilter fields.
> * You can only map fields of the type BigInteger, Boolean, Code, Date, DateFormula, DateTime, Decimal, Duration, GUID, Integer, Option, and Text.

> [!TIP]
> You can also add new field mappings to existing integration table mappings through the **Integration Field Mappings** list page, which you can access by choosing **Fields** on the **Integration Table Mappings** page.
>
> Simply choose **New Field Mapping** to open the field mapping step of the **Create new integration mappings** assisted setup guide, and then proceed as described in this article.

New field mappings you add to an existing table mapping are in a Disabled state. You can choose **Edit List** to enable them later.

### Synchronization rules

An integration table mapping also includes rules that control how integration synchronization jobs synchronize records in a [!INCLUDE[prod_short](includes/prod_short.md)] table and a table in [!INCLUDE[prod_short](includes/cds_long_md.md)]. For examples of rules for an integration with Sales, go to [Synchronization Rules](#synchronization-rules).

### Strategies for autoresolving conflicts

Data conflicts can easily occur when business applications exchange data on an ongoing basis. For example, someone might delete or change a row in one of the applications, or both. To reduce the number of conflicts to manually resolve, you can specify resolution strategies. [!INCLUDE[prod_short](includes/prod_short.md)] automatically resolves conflicts according to the rules in the strategies.

Integration table mappings include rules that control how synchronization jobs synchronize records. On the **Integration Table Mapping** page, in the **Resolve Deletion Conflicts** and **Resolve Update Conflicts** columns, you can specify how [!INCLUDE[prod_short](includes/prod_short.md)] resolves conflicts that occur because records were deleted in tables in one or the other business application, or updated in both. 

In the **Resolve Deletion Conflicts** column, you can choose to have [!INCLUDE[prod_short](includes/prod_short.md)] automatically restore deleted records, remove the coupling between the records, or do nothing. If you do nothing, you must manually resolve conflicts. 

In the **Resolve Update Conflicts** column, you can choose to have [!INCLUDE[prod_short](includes/prod_short.md)] automatically send a data update to the integration table when sending data to [!INCLUDE[prod_short](includes/cds_long_md.md)], or to get a data update from the integration table when getting data from [!INCLUDE[prod_short](includes/cds_long_md.md)], or do nothing. If you do nothing, you must manually resolve conflicts.

After you specify the strategy, on the **Coupled Data Synchronization Errors** page, you can choose the **Retry All** action to automatically resolve conflicts.

## Mapping integration fields

Mapping tables is only the first step. You must also map the fields on the tables. Integration field mappings link fields in [!INCLUDE[prod_short](includes/prod_short.md)] tables with corresponding columns in [!INCLUDE[prod_short](includes/cds_long_md.md)], and determine whether to synchronize data in each table. The standard table mapping that [!INCLUDE[prod_short](includes/prod_short.md)] provides includes field mappings, but you can change the mappings. For more information, see [Viewing Table Mappings](admin-synchronizing-business-central-and-sales.md#tip-for-admins-viewing-table-mappings).

> [!Note]
> If you are using an on-premises version of [!INCLUDE[prod_short](includes/prod_short.md)], integration field mappings are defined in table 5336 Integration Field Mapping.

You can manually map the fields, or you can automate the process by mapping multiple fields at the same time based on criteria for matching their values. For more information, see [To couple multiple records based on field value matching](admin-how-to-couple-and-synchronize-records-manually.md).

### Handle differences in field values

Sometimes the values in the fields that you want to map are different. For example, in [!INCLUDE[crm_md](includes/crm_md.md)] the language code for the United States is "U.S.," but in [!INCLUDE[prod_short](includes/prod_short.md)] it's "US." That means you must transform the value when you synchronize data. You can specify transformation rules for the fields on the **Integration Table Mappings** page by choosing **Mapping**, and then **Fields**. Predefined rules are provided, but you can also create your own. For more information, see [Transformation Rules](across-how-to-set-up-data-exchange-definitions.md#transformation-rules).

### Handle missing option values

[!INCLUDE[prod_short](includes/cds_long_md.md)] contains option set columns that provide values that you can map to [!INCLUDE[prod_short](includes/prod_short.md)] fields of the type **Option** for automatic synchronization. During synchronization, nonmapped options are ignored and the missing options are appended to the related [!INCLUDE[prod_short](includes/prod_short.md)] table and added to the **CDS Option Mapping** system table to be handled manually later. For example, by adding the missing options in either product and then updating the mapping. For more information, see [Handling Missing Option Values](admin-cds-missing-option-values.md).

## Couple records

Coupling links rows in [!INCLUDE[prod_short](includes/cds_long_md.md)] to records in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, accounts in [!INCLUDE[prod_short](includes/cds_long_md.md)] are typically coupled with customers in [!INCLUDE[prod_short](includes/prod_short.md)]. Coupling records offers the following benefits:

* It makes synchronization possible.
* Users can open records or rows in one business app from the other.

Coupling requires that the apps are already integrated.

Couplings can be set up automatically by using the synchronization jobs, or manually by editing the record in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Synchronizing Data in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-synchronizing-business-central-and-sales.md) and [Couple and Synchronize Records Manually](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings).

## Filter records and rows  

If you don't want to synchronize all rows for a specific table in [!INCLUDE[prod_short](includes/cds_long_md.md)] or table in [!INCLUDE[prod_short](includes/prod_short.md)], you can set up filters to limit the data that is synchronized. You set up filters on the **Integration Table Mappings** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.
2. To filter the [!INCLUDE[prod_short](includes/prod_short.md)] records, set the **Table Filter** field.  
3. To filter the [!INCLUDE[prod_short](includes/cds_long_md.md)] rows, set the **Integration Table Filter** field.  

## Create new records  

By default, only coupled records in [!INCLUDE[prod_short](includes/prod_short.md)] and rows in [!INCLUDE[prod_short](includes/cds_long_md.md)] are synchronized by the integration synchronization jobs. You can set up table mappings to create new records or rows in the destination app for each row in the source app that isn't already coupled.  

For example, the SALESPEOPLE - Dynamics 365 Sales synchronization job uses the table mapping SALESPEOPLE. The synchronization job copies data from users in [!INCLUDE[prod_short](includes/cds_long_md.md)] to salespersons in [!INCLUDE[prod_short](includes/prod_short.md)]. If you set up the table mapping to create new records, for every user in [!INCLUDE[prod_short](includes/cds_long_md.md)] that isn't already coupled to a salesperson in [!INCLUDE[prod_short](includes/prod_short.md)], a new salesperson row is created in [!INCLUDE[prod_short](includes/prod_short.md)].  

### To create new records during synchronization  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.
2. In the table mapping entry in the list, clear the **Synch. Only Coupled Records** field.  

## Use configuration templates on table mappings

You can specify one or more configuration templates to use for new [!INCLUDE[prod_short](includes/prod_short.md)] records, and another template to use new [!INCLUDE[prod_short](includes/cds_long_md.md)] rows.  

If you install the default synchronization setup, most of the time, two configuration templates are automatically created and used on the table mapping for [!INCLUDE[prod_short](includes/prod_short.md)] customers and [!INCLUDE[crm_md](includes/crm_md.md)] accounts: **CDSCUST** and **CDSACCOUNT**.  

* **CDSCUST** creates and synchronizes new customers in [!INCLUDE[prod_short](includes/prod_short.md)] based on accounts in [!INCLUDE[crm_md](includes/crm_md.md)].  

     To create this template, copy an existing configuration template for customers. The **CDSCUST** is created only if there's an existing configuration template and the **Currency Code** field in the template is blank. If a field in the configuration template contains a value, the value replaces the value in the mapped column for the [!INCLUDE[prod_short](includes/cds_long_md.md)] account. For example, if the **Country/Region** column in an account in [!INCLUDE[prod_short](includes/cds_long_md.md)] contains *U.S.* and the **Country/Region** field in the configuration template is **GB**, then **GB** is used as the **Country/Region** for the customer in [!INCLUDE[prod_short](includes/prod_short.md)].  

* **CDSACCOUNT** creates and synchronizes new accounts in [!INCLUDE[prod_short](includes/cds_long_md.md)] based on an account in [!INCLUDE[prod_short](includes/prod_short.md)].  

You can add more templates, and use filters to define conditions under which [!INCLUDE [prod_short](includes/prod_short.md)] applies them. The templates apply to data moving in either direction. For example, you might use a template for domestic customers in the United States, and another for foreign customers in the European Union, or vice versa. In that case, when the data synchronizes, [!INCLUDE [prod_short](includes/prod_short.md)] uses the country/region code for the customer to apply the appropriate template.

### To specify configuration templates on a table mapping  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Integration Table Mappings**, and then choose the related link.
2. In the table mapping entry in the list, in the **Table Config Templates** field, choose to the configuration template to use for new records in [!INCLUDE[prod_short](includes/prod_short.md)].  
3. If you have multiple templates, to define the conditions that determine when to use the template, enter criteria in the **Integration Table Filter** field, and then enter a number in the **Priority** field. The priority determines the order in which [!INCLUDE [prod_short](includes/prod_short.md)] evaluates whether to use the templates.

   > [!NOTE]
   > The **Table Config Template Code** and **Int. Tbl. Config Template Code** fields show different values depending on the number of templates that you configure for a specific integration table mapping:
   >
   > * If you configure a single configuration template, the name of the configuration template shows in order to stay compatible with current capabilities.
   > * If you configure multiple configuration templates, the number of configured configuration templates shows.

4. Set the **Int. Tbl. Config Template Code** field to the configuration template to use for new records in [!INCLUDE[prod_short](includes/cds_long_md.md)].

## Related information  

[About Integrating Dynamics 365 Business Central with [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Synchronizing Business Central and [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-synchronizing-business-central-and-sales.md)  
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
