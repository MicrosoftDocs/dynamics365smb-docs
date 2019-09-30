---
title: Synchronization and Data Integration | Microsoft Docs
description: The synchronization copies data between Dynamics 365 Sales entries and Business Central records, and keeps the data in both systems up-to-date.
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

# Synchronizing Data in Business Central and Dynamics 365 Sales
When you integrate [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[d365fin](includes/d365fin_md.md)], you can decide whether to synchronize data in selected fields of [!INCLUDE[d365fin](includes/d365fin_md.md)] records (such as customers, contacts, and sales people) with equivalent records in [!INCLUDE[d365fin](includes/d365fin_md.md)] (such as accounts, contacts, and users). Depending on the type of record, you can synchronize data from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)], or vice versa. For more information, see [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).  

Synchronization uses the following elements:

* Integration table mappings
* Integration field mappings
* Synchronization rules
* Coupled records

When synchronization is set up you can couple [!INCLUDE[d365fin](includes/d365fin_md.md)] records to [!INCLUDE[crm_md](includes/crm_md.md)] records to synchronize their data. You can start a synchronization manually, or based on a schedule. The following table provides on overview of the ways you can synchronize records.  

|  Type  |  Method  |  See  |  
|--------|----------|-------|  
|Manual synchronization|Synchronize on a record-by-record basis.<br /><br /> You can synchronize individual records in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as a customer, with a corresponding [!INCLUDE[crm_md](includes/crm_md.md)] record, such as an account. This is typically how users will work with [!INCLUDE[crm_md](includes/crm_md.md)] data in [!INCLUDE[d365fin](includes/d365fin_md.md)].|[Couple and Synchronize Records Manually](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
|  |Synchronize on a table mapping basis.<br /><br /> You can synchronize all records in a [!INCLUDE[d365fin](includes/d365fin_md.md)] table with an entity [!INCLUDE[crm_md](includes/crm_md.md)] entity.|[Synchronize Individual Table Mappings](admin-manual-synchronization-of-table-mappings.md#synchronize-individual-table-mappings)|  
||Synchronize all modified records for all table mappings.<br /><br /> You can synchronize all of the records that have been modified in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables since the last synchronization.|[Synchronizing All Modified Records](admin-manual-synchronization-of-table-mappings.md#synchronizing-all-modified-records)|
||Full synchronization of all data for all table mappings.<br /><br /> You can synchronize all of the data in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables and [!INCLUDE[crm_md](includes/crm_md.md)] entities that are mapped, and create new records in the destination solution for uncoupled records in the source solution.<br /><br /> Full synchronization synchronizes all data and ignores coupling. Typically, you do a full synchronization when you set up the integration and only one of solutions contains data. A full synchronization can also be useful in a demonstration environment.|[Run a Full Synchronization](admin-manual-synchronization-of-table-mappings.md#run-a-full-synchronization)|  
|Scheduled synchronization|Synchronize all changes to data for all table mappings.<br /><br /> You can synchronize [!INCLUDE[d365fin](includes/d365fin_md.md)] with [!INCLUDE[crm_md](includes/crm_md.md)] on scheduled intervals by setting up jobs in the job queue.|[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)|  

## Standard Sales Entity Mapping for Synchronization
Entities in [!INCLUDE[crm_md](includes/crm_md.md)], such as accounts, are integrated with equivalent types of entities in [!INCLUDE[d365fin](includes/d365fin_md.md)],such as customers. To work with [!INCLUDE[crm_md](includes/crm_md.md)] data you set up links, called couplings, between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].

The following table lists the standard mapping between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] that [!INCLUDE[d365fin](includes/d365fin_md.md)] provides.

|[!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[crm_md](includes/crm_md.md)]|Synchronization Direction|Default Filter|
|-------------------------------------------|-----|-------------------------|--------------|
|Salesperson/Purchaser|User|[!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Status** is **No**, **User Licensed** is **Yes**, Integration user mode is **No**|
|Customer|Account|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales account filter: **Relationship Type** is **Customer** and **Status** is **Active**.|
|Contact|Contact|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] contact filter: **Type** is **Person** and the contact is assigned to a company. Sales contact filter: The contact is assigned to a company and the parent customer type is **Account**|
|Currency|Transaction Currency|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Unit of Measure|Unit Group|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Item|Product|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Product Type** is **Sales Inventory**|
|Resource|Product|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Product Type** is **Services**|
|Customer Price Group|Price List|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Sales Price|Product Price List|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] contact filter: **Sales Code** is not blank, **Sales Type** is **Customer Price Group**|
|Opportunity|Opportunity|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]| |
|Sales Invoice Header|Invoice|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Sales Invoice Line|Invoice Product|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Sales Order Header|Sales Order|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] Sales Header filter: **Document Type** is Order, **Status** is Released|
|Sales Order Notes|Sales Order Notes|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]| |

### Tip for Admins: Viewing Entity Mappings
You can view the mapping between the entities in [!INCLUDE[crm_md](includes/crm_md.md)] and the tables in [!INCLUDE[d365fin](includes/d365fin_md.md)] on the **Integration Table Mappings** page, where you can also apply filters. You define the mapping between the fields in [!INCLUDE[d365fin](includes/d365fin_md.md)] tables and the fields in [!INCLUDE[crm_md](includes/crm_md.md)] entities on the **Integration Field Mapping** page, where you can add additional mapping logic. For example, this can be useful if you need to troubleshoot synchronization.

### Tip for Developers: Mapping Fields in Business Central to the Option Sets in Sales
If you are a developer and you want to add options to the option sets in [!INCLUDE[crm_md](includes/crm_md.md)], you need to know this. There are three tables in [!INCLUDE[d365fin](includes/d365fin_md.md)] that are mapped to the option fields of the **Account** entity in [!INCLUDE[crm_md](includes/crm_md.md)]. Records in the tables that are not linked to options in [!INCLUDE[crm_md](includes/crm_md.md)] will not be synchronized. This means that the **Option** field will be blank in [!INCLUDE[crm_md](includes/crm_md.md)].

The following table shows mappings from [!INCLUDE[d365fin](includes/d365fin_md.md)] tables for the **Option** field in the **Account** entity in [!INCLUDE[crm_md](includes/crm_md.md)].

|Table|Option Field in the Account Entity|
|----------------------|-------------------------------------------|
|Payment Terms|Payment Terms|
|Shipment Method|Address 1: Freight Terms|
|Shipping Agent|Address 1: Shipping Method|

### Synchronization Rules
The following table describes rules that control the synchronization between the apps.

> [!NOTE]  
> Changes to data in [!INCLUDE[crm_md](includes/crm_md.md)] that were made by the [!INCLUDE[crm_md](includes/crm_md.md)] connection user account are not synchronized. Therefore, we recommended that you do not change data while using that account. For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

|Table|Rule|
|-----|----|
|Customers|Before a customer can be synchronized to an account, the salesperson that is assigned to the customer must be coupled to a user in [!INCLUDE[crm_md](includes/crm_md.md)]. Therefore, when you run the CUSTOMERS - Dynamics 365 Sales synchronization job and you set it up to create new records, make sure that you synchronize salespeople with [!INCLUDE[crm_md](includes/crm_md.md)] users before you synchronize customers with accounts in [!INCLUDE[crm_md](includes/crm_md.md)]. <br /> <br />The CUSTOMERS - Dynamics 365 Sales synchronization job only synchronizes Sales accounts that have the relationship type Customer.|
|Contacts|Only contacts in [!INCLUDE[crm_md](includes/crm_md.md)] that are associated with an account will be created in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The Salesperson Code value defines the owner of the coupled entity in [!INCLUDE[crm_md](includes/crm_md.md)].|
|Currencies|Currencies are coupled to transaction currencies in [!INCLUDE[crm_md](includes/crm_md.md)] based on ISO codes. Only currencies that have a standard ISO code will be coupled and synchronized with transaction currencies.|
|Units of Measure|Units of measure are synchronized with unit groups in [!INCLUDE[crm_md](includes/crm_md.md)]. There can only be one unit of measure defined in the unit group.|
|Items|When synchronizing items with [!INCLUDE[crm_md](includes/crm_md.md)] products, [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically creates a price list in [!INCLUDE[crm_md](includes/crm_md.md)]. To avoid synchronization errors, you should not modify this price list manually.|
|Salespersons|Salespersons are coupled to system users in [!INCLUDE[crm_md](includes/crm_md.md)]. The user must be enabled and licensed and must not be the Integration user. Note, that this is the first table that must be synchronized because it is used in customers, contacts, opportunities, and sales invoices.|
|Resources|Resources are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] products that have product type Service.|
|Customer Price Groups|Customer price groups are synchronized with Sales price lists.|
|Sales Prices|Sales prices that have sales type Customer Price Group and have a sales code defined are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] price list lines|
|Opportunities|Opportunities are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] opportunities. The Salesperson Code value defines the owner of the coupled entity in [!INCLUDE[crm_md](includes/crm_md.md)].|
|Posted Sales Invoices|Posted sales invoices are synchronized with sales invoices. Before an invoice can be synchronized, it is better to synchronize all other entities that can participate in the invoice, from salespersons to price lists. The Salesperson Code value in the invoice header defines the owner of the coupled entity in Sales.|
|Sales Orders|When sales order integration is enabled, sales orders in [!INCLUDE[d365fin](includes/d365fin_md.md)] that are created from submitted sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] are synchronized with sales orders in INCLUDE SALES when they are released. Before you synchronize orders, we recommend that you first synchronize all entities that the are involved with the order, such as sales persons and price lists. The Salesperson Code field in the order header defines the owner of the coupled entity in [!INCLUDE[crm_md](includes/crm_md.md)].|  

## See Also  
[Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md)   
[Schedule a Synchronization](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md)   
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)
