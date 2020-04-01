---
title: Synchronization and Data Integration | Microsoft Docs
description: The synchronization copies data between Common Data Service entities and Business Central records, and keeps the data in both systems up-to-date.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.date: 04/01/2020
ms.author: bholtorf

---

# Synchronizing Data in Business Central with Common Data Service
When you integrate [!INCLUDE[d365fin](includes/cds_long_md.md)] with [!INCLUDE[d365fin](includes/d365fin_md.md)], you can decide whether to synchronize data in selected fields of [!INCLUDE[d365fin](includes/d365fin_md.md)] records (such as customers, contacts, and sales people) with equivalent records in [!INCLUDE[d365fin](includes/cds_long_md.md)] (such as accounts, contacts, and users). Depending on the type of record, you can synchronize data from [!INCLUDE[d365fin](includes/cds_long_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)], or vice versa. For more information, see [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).  

Synchronization uses the following elements:

* Integration table mappings
* Integration field mappings
* Synchronization rules
* Coupled records

When synchronization is set up you can couple [!INCLUDE[d365fin](includes/d365fin_md.md)] records to [!INCLUDE[d365fin](includes/cds_long_md.md)] records to synchronize their data. You can start a synchronization manually, or based on a schedule. The following table provides on overview of the ways you can synchronize records.  

|  Type  |  Method  |  See  |  
|--------|----------|-------|  
|Manual synchronization|Synchronize on a record-by-record basis.<br /><br /> You can synchronize individual records in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as a customer, with a corresponding [!INCLUDE[d365fin](includes/cds_long_md.md)] record, such as an account. This is typically how users will work with [!INCLUDE[d365fin](includes/cds_long_md.md)] data in [!INCLUDE[d365fin](includes/d365fin_md.md)].|[Couple and Synchronize Records Manually](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
|  |Synchronize on a table mapping basis.<br /><br /> You can synchronize all records in a [!INCLUDE[d365fin](includes/d365fin_md.md)] table with an entity [!INCLUDE[d365fin](includes/cds_long_md.md)] entity.|[Synchronize Individual Table Mappings](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
||Synchronize all modified records for all table mappings.<br /><br /> You can synchronize all of the records that have been modified in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables since the last synchronization.|[Synchronizing All Modified Records](admin-manual-synchronization-of-table-mappings.md#synchronizing-all-modified-records)|
||Full synchronization of all data for all table mappings.<br /><br /> You can synchronize all of the data in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables and [!INCLUDE[d365fin](includes/cds_long_md.md)] entities that are mapped, and create new records in the destination solution for uncoupled records in the source solution.<br /><br /> Full synchronization synchronizes all data and ignores coupling. Typically, you do a full synchronization when you set up the integration and only one of solutions contains data. A full synchronization can also be useful in a demonstration environment.|[Run a Full Synchronization](admin-manual-synchronization-of-table-mappings.md#run-a-full-synchronization)|  
|Scheduled synchronization|Synchronize all changes to data for all table mappings.<br /><br /> You can synchronize [!INCLUDE[d365fin](includes/d365fin_md.md)] with [!INCLUDE[d365fin](includes/cds_long_md.md)] on scheduled intervals by setting up jobs in the job queue.|[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)|  

## Standard Entity Mapping for Synchronization
Entities in [!INCLUDE[d365fin](includes/cds_long_md.md)], such as accounts, are integrated with equivalent types of entities in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as customers. To work with [!INCLUDE[d365fin](includes/cds_long_md.md)] data you set up links, called couplings, between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)].

The following table lists the standard mapping between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)] that [!INCLUDE[d365fin](includes/d365fin_md.md)] provides.

|[!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[d365fin](includes/cds_long_md.md)]|Synchronization Direction|Default Filter|
|-------------------------------------------|-----|-------------------------|--------------|
|Salesperson/Purchaser|User|[!INCLUDE[d365fin](includes/cds_long_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Status** is **No**, **User Licensed** is **Yes**, Integration user mode is **No**|
|Customer|Account|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales account filter: **Relationship Type** is **Customer** and **Status** is **Active**.|
|Vendor|Account|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales account filter: **Relationship Type** is **Vendor** and **Status** is **Active**.|
|Contact|Contact|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] contact filter: **Type** is **Person** and the contact is assigned to a company. Sales contact filter: The contact is assigned to a company and the parent customer type is **Account**|
|Currency|Transaction Currency|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |


### Tip for Admins: Viewing Entity Mappings
You can view the mapping between the entities in [!INCLUDE[d365fin](includes/cds_long_md.md)] and the tables in [!INCLUDE[d365fin](includes/d365fin_md.md)] on the **Integration Table Mappings** page, where you can also apply filters. You define the mapping between the fields in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables and the fields in [!INCLUDE[d365fin](includes/cds_long_md.md)] entities on the **Integration Field Mapping** page, where you can add additional mapping logic. For example, this can be useful if you need to troubleshoot synchronization.

## See Also  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)   
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)   
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)
