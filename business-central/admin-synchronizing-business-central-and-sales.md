---
title: Synchronization and data integration
description: Synchronization copies data between Microsoft Dataverse tables and Business Central records to align data in both systems.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.date: 06/10/2025
ms.custom: bap-template
ms.search.keywords: Dataverse, integration, sync, synchronize, mapping
ms.saerch.form: 5372_Primary
ms.service: dynamics-365-business-central
---

# Synchronizing data in Business Central with Microsoft Dataverse

When you integrate [!INCLUDE[prod_short](includes/cds_long_md.md)] with [!INCLUDE[prod_short](includes/prod_short.md)], you can decide whether to synchronize data in selected fields of [!INCLUDE[prod_short](includes/prod_short.md)] (such as customers, contacts, and sales people) with equivalent rows in [!INCLUDE[prod_short](includes/cds_long_md.md)] (such as accounts, contacts, and users). Depending on the type of row, you can synchronize data from [!INCLUDE[prod_short](includes/cds_long_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)], or vice versa. Learn more at [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).  

Synchronization uses the following elements:

* Integration table mappings
* Integration field mappings
* Synchronization rules
* Records that are coupled

When synchronization is set up, you can couple [!INCLUDE[prod_short](includes/prod_short.md)] records to [!INCLUDE[prod_short](includes/cds_long_md.md)] rows to synchronize their data. You can start a synchronization manually, or based on a schedule. The following table provides an overview of the ways you can synchronize.  

|  Type  |  Method  |  Learn more  |  
|--------|----------|-------|  
|Manual synchronization|Synchronize on a row-by-row basis.<br /><br /> You can synchronize individual records in [!INCLUDE[prod_short](includes/prod_short.md)], such as a customer, with a corresponding [!INCLUDE[prod_short](includes/cds_long_md.md)] row, such as an account. |[Couple and Synchronize Records Manually](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
|  |Synchronize on a table mapping basis.<br /><br /> You can synchronize all records in a [!INCLUDE[prod_short](includes/prod_short.md)] table with a table [!INCLUDE[prod_short](includes/cds_long_md.md)] table.|[Synchronize Individual Table Mappings](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
||Synchronize all modified records for all table mappings.<br /><br /> You can synchronize all of the records that were modified in [!INCLUDE[prod_short](includes/prod_short.md)] tables since the last synchronization.|[Synchronizing All Modified Records](admin-manual-synchronization-of-table-mappings.md#synchronizing-all-modified-records)|
||Full synchronization of all data for all table mappings.<br /><br /> You can synchronize all data in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] tables that are mapped. It also creates new records or rows in the destination solution for uncoupled records in the source solution.<br /><br /> Full synchronization synchronizes all data and ignores coupling. Typically, you do a full synchronization when you set up the integration and only one of solutions contains data. A full synchronization can also be useful in a demonstration environment.|[Run a Full Synchronization](admin-manual-synchronization-of-table-mappings.md#run-a-full-synchronization)|  
|Scheduled synchronization|Synchronize all changes to data for all table mappings.<br /><br /> You can synchronize [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)] on scheduled intervals by setting up jobs in the job queue.|[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)|  

> [!NOTE]
> The synchronization between [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] is based on the scheduled job queue entries and doesn't guarantee real time data consistency between two services. For real time data consistency, explore [Business Central Virtual Tables](/dynamics365/business-central/dev-itpro/powerplatform/powerplat-overview) or Business Central APIs.

## Standard table mapping for synchronization

Tables in [!INCLUDE[prod_short](includes/cds_long_md.md)], such as accounts, are integrated with equivalent types of tables in [!INCLUDE[prod_short](includes/prod_short.md)], such as customers. To work with [!INCLUDE[prod_short](includes/cds_long_md.md)] data you set up links, called couplings, between tables in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)].

The following table lists the standard mapping between tables in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)].

> [!TIP]
> You can reset configuration changes made to integration table and field mappings to their default settings by selecting the mappings, and then choosing **Use Default Synchronization Setup**.

| [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] | Synchronization Direction | Default Filter |
|---------------------------------------------|----------------------------------------------|---------------------------|----------------|
| Salesperson/Purchaser | User | [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] contact filter: **Status** is **No**, **User Licensed** is **Yes**, Integration user mode is **No** |
| Customer | Account | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] account filter: **Relationship Type** is **Customer** and **Status** is **Active**. [!INCLUDE[prod_short](includes/prod_short.md)] filter: **Blocked** is blank (Customer isn't blocked). |
| Vendor | Account | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] account filter: **Relationship Type** is **Vendor** and **Status** is **Active**. [!INCLUDE[prod_short](includes/prod_short.md)] filter: **Blocked** is blank (Vendor isn't blocked). |
| Contact | Contact | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/prod_short.md)] contact filter: **Type** is **Person** and the contact is assigned to a company. [!INCLUDE[prod_short](includes/cds_long_md.md)] contact filter: The contact is assigned to a company and the parent customer type is **Customer**. |
| Currency | Transaction Currency | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] |  |

> [!NOTE]
> The **Dataverse** actions aren't available on pages, for example, the Customer Card page, for records that don't respect the table filter on the integration table mapping.

### Tip for admins: viewing table mappings

You can view the mapping between the tables in [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] on the **Integration Table Mappings** page, where you can also apply filters. You define the mapping between the fields in [!INCLUDE[prod_short](includes/prod_short.md)] tables and the columns in [!INCLUDE[prod_short](includes/cds_long_md.md)] tables on the **Integration Field Mapping** page, where you can add more mapping logic. For example, you might add mapping logic if you need to troubleshoot synchronization.

## Use virtual tables to get more data

When you're setting up your integration, you can use virtual tables to make more data available in [!INCLUDE[prod_short](includes/cds_long_md.md)], without help from a developer.

A virtual table is a custom table that has columns and rows that contain data from an external data source, such as [!INCLUDE [prod_short](includes/prod_short.md)]. The columns and rows in a virtual table look like a regular table, however, the data isn't stored in a physical table in the [!INCLUDE[prod_short](includes/cds_long_md.md)] database. Instead, the data is retrieved at runtime.

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] contains objects that are also called virtual tables. Those table objects aren't related to the virtual tables that you use with [!INCLUDE[prod_short](includes/cds_long_md.md)].

To learn more about virtual tables, go to the following articles:

* [Create and edit virtual tables that contain data from an external data source](/power-apps/maker/data-platform/create-edit-virtual-entities) (Power Apps documentation)
* [Business Central Virtual Table for Microsoft Dataverse Admin Reference](/dynamics365/business-central/dev-itpro/powerplatform/powerplat-admin-reference) ([!INCLUDE [prod_short](includes/prod_short.md)] documentation)

To use virtual tables, you must install the **Business Central Virtual Entity** app from [Marketplace](https://marketplace.microsoft.com/en-US/product/dynamics-365/microsoftdynsmb.businesscentral_virtualentity).

After you install the app, you can enable virtual tables from one of the following pages in [!INCLUDE [prod_short](includes/prod_short.md)]:

* When you run the **Set up Dataverse connection** assisted setup guide, you can use the **Dataverse Available Virtual Tables** page to select multiple virtual tables. Afterward, the tables are available in [!INCLUDE[prod_short](includes/cds_long_md.md)] and the PowerApps Maker Portal.
* From the **Dataverse Connection Setup**, **Virtual Tables**, and **Available Virtual Tables** pages.  
* From the Power App Maker Portal.

## Synchronize data from multiple companies or environments

You can synchronize data from multiple [!INCLUDE [prod_short](includes/prod_short.md)] companies or environments with a [!INCLUDE[prod_short](includes/cds_long_md.md)] environment. In multi-company synchronization scenarios, there are several things to consider.

### Set company IDs

When you synchronize records, we set a company ID on the [!INCLUDE[prod_short](includes/cds_long_md.md)] entity to clarify the [!INCLUDE [prod_short](includes/prod_short.md)] company the records came from. Integration table mappings have integration table filter fields that take the company ID into account. To include a table mapping in a multi-company setup, on the **Integration Table Mapping** page, choose the **Multi-Company Synchronization Enabled** checkbox. The setting optimizes how integration table filter fields filter company IDs in a multi-company setup.

For integration table mappings that synchronize documents, such as orders, quotes, and opportunities, if you choose the **Multi-Company Synchronization Enabled** checkbox the integration only considers entities that have the company ID of the current [!INCLUDE [prod_short](includes/prod_short.md)] company. To synchronize documents, for example, between Business Central and Sales, users in Sales must specify the company ID on the documents. Otherwise, the documents don't synchronize.  

For all other integration table mappings, choosing the **Multi-Company Synchronization Enabled** checkbox removes the filter on company ID. The synchronization considers related entities, regardless of their company ID.

### Specify the synchronization direction

If you enable multi-company support on an integration table mapping, we recommend that you set the direction of the mapping to **FromIntegration**. If you set the direction to **ToIntegration** or **Bidirectional**, it's a good idea to use **Table Filter** and **Integration Table Filter** to control which entities synchronize with which company. It's also a good idea to use match-based coupling to avoid creating duplicate records. Learn more at [Customize the match-based coupling](/dynamics365/business-central/admin-how-to-set-up-a-dynamics-crm-connection#customize-the-match-based-coupling).

### Use unique numbers

If your number series doesn't guarantee that primary key values are unique to each company, we recommend that you use prefixes. To start using prefixes, create a transformation rule on the integration field mapping. Learn more at [Handle differences in field values](admin-how-to-modify-table-mappings-for-synchronization.md#handle-differences-in-field-values).

## Related information  

[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)  
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)  
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
