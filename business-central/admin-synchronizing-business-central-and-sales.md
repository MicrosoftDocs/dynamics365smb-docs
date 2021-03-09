---
title: Synchronization and Data Integration | Microsoft Docs
description: The synchronization copies data between Microsoft Dataverse tables and Business Central records, and keeps the data in both systems up-to-date.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.date: 10/01/2020
ms.author: bholtorf

---

# Synchronizing Data in Business Central with Microsoft Dataverse
[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

When you integrate [!INCLUDE[prod_short](includes/cds_long_md.md)] with [!INCLUDE[prod_short](includes/prod_short.md)], you can decide whether to synchronize data in selected fields of [!INCLUDE[prod_short](includes/prod_short.md)] (such as customers, contacts, and sales people) with equivalent rows in [!INCLUDE[prod_short](includes/cds_long_md.md)] (such as accounts, contacts, and users). Depending on the type of row, you can synchronize data from [!INCLUDE[prod_short](includes/cds_long_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)], or vice versa. For more information, see [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).  

Synchronization uses the following elements:

* Integration table mappings
* Integration field mappings
* Synchronization rules
* Coupled records

When synchronization is set up you can couple [!INCLUDE[prod_short](includes/prod_short.md)] records to [!INCLUDE[prod_short](includes/cds_long_md.md)] rows to synchronize their data. You can start a synchronization manually, or based on a schedule. The following table provides on overview of the ways you can synchronize.  

|  Type  |  Method  |  See  |  
|--------|----------|-------|  
|Manual synchronization|Synchronize on a row-by-row basis.<br /><br /> You can synchronize individual records in [!INCLUDE[prod_short](includes/prod_short.md)], such as a customer, with a corresponding [!INCLUDE[prod_short](includes/cds_long_md.md)] row, such as an account. This is typically how users will work with [!INCLUDE[prod_short](includes/cds_long_md.md)] data in [!INCLUDE[prod_short](includes/prod_short.md)].|[Couple and Synchronize Records Manually](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
|  |Synchronize on a table mapping basis.<br /><br /> You can synchronize all records in a [!INCLUDE[prod_short](includes/prod_short.md)] table with an table [!INCLUDE[prod_short](includes/cds_long_md.md)] table.|[Synchronize Individual Table Mappings](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
||Synchronize all modified records for all table mappings.<br /><br /> You can synchronize all of the records that have been modified in [!INCLUDE[prod_short](includes/prod_short.md)] tables since the last synchronization.|[Synchronizing All Modified Records](admin-manual-synchronization-of-table-mappings.md#synchronizing-all-modified-records)|
||Full synchronization of all data for all table mappings.<br /><br /> You can synchronize all of the data in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] tables that are mapped, and create new records or rows in the destination solution for uncoupled records in the source solution.<br /><br /> Full synchronization synchronizes all data and ignores coupling. Typically, you do a full synchronization when you set up the integration and only one of solutions contains data. A full synchronization can also be useful in a demonstration environment.|[Run a Full Synchronization](admin-manual-synchronization-of-table-mappings.md#run-a-full-synchronization)|  
|Scheduled synchronization|Synchronize all changes to data for all table mappings.<br /><br /> You can synchronize [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)] on scheduled intervals by setting up jobs in the job queue.|[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)|  

## Standard Table Mapping for Synchronization
Tables in [!INCLUDE[prod_short](includes/cds_long_md.md)], such as accounts, are integrated with equivalent types of tables in [!INCLUDE[prod_short](includes/prod_short.md)], such as customers. To work with [!INCLUDE[prod_short](includes/cds_long_md.md)] data you set up links, called couplings, between tables in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)].

The following table lists the standard mapping between tables in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)].

> [!TIP]
> You can reset configuration changes made to integration table and field mappings to their default settings by selecting the mappings, and then choosing **Use Default Synchronization Setup**.

| [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] | Synchronization Direction | Default Filter |
|---------------------------------------------|----------------------------------------------|---------------------------|----------------|
| Salesperson/Purchaser | User | [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] contact filter: **Status** is **No**, **User Licensed** is **Yes**, Integration user mode is **No** |
| Customer | Account | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] account filter: **Relationship Type** is **Customer** and **Status** is **Active**. [!INCLUDE[prod_short](includes/prod_short.md)] filter: **Blocked** is blank (Customer is not blocked). |
| Vendor | Account | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/cds_long_md.md)] account filter: **Relationship Type** is **Vendor** and **Status** is **Active**. [!INCLUDE[prod_short](includes/prod_short.md)] filter: **Blocked** is blank (Vendor is not blocked). |
| Contact | Contact | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/prod_short.md)] contact filter: **Type** is **Person** and the contact is assigned to a company. [!INCLUDE[prod_short](includes/cds_long_md.md)] contact filter: The contact is assigned to a company and the parent customer type is **Account** |
| Currency | Transaction Currency | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] |  |


### Tip for Admins: Viewing Table Mappings
You can view the mapping between the tables in [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] on the **Integration Table Mappings** page, where you can also apply filters. You define the mapping between the fields in [!INCLUDE[prod_short](includes/prod_short.md)] tables and the columns in [!INCLUDE[prod_short](includes/cds_long_md.md)] tables on the **Integration Field Mapping** page, where you can add additional mapping logic. For example, this can be useful if you need to troubleshoot synchronization.

## See Also  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)   
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)   
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]