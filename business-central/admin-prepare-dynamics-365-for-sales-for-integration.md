---
title: Integrating with Dynamics 365 Sales
description: Learn how to get Dynamics 365 Business Central ready to integrate with Dynamics 365 Sales.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: sales, crm, integration, integrating
ms.date: 07/02/2024
ms.service: dynamics-365-business-central
ms.custom:
  - bap-template
  - sfi-ropc-blocked
---
# Integrating with Dynamics 365 Sales

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

The sales person role is often considered as one the most outward-facing jobs in a business. However, it can be helpful for sales people to be able to look inward in the business and know what's happening on the back end. By integrating [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[crm_md](includes/crm_md.md)], you can give your sales people that insight. The integration lets people view information in [!INCLUDE[prod_short](includes/prod_short.md)] while they're working in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, when preparing a sales quote it could be useful to know whether you have enough inventory to fulfill the order. To learn more, go to [Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md).

> [!NOTE]
> This article describes the process of integrating the online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] through [!INCLUDE[prod_short](includes/cds_long_md.md)]. To learn more about on-premises configuration, go to [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

## Integrate through Dataverse

To make it easy to connect and synchronize data with other Dynamics 365 applications, [!INCLUDE[prod_short](includes/prod_short.md)] also integrates with [!INCLUDE[prod_short](includes/cds_long_md.md)]. For example, you can connect to [!INCLUDE[crm_md](includes/crm_md.md)], or even apps that you build yourself. If you're integrating for the first time, you must do so through [!INCLUDE[prod_short](includes/cds_long_md.md)]. To learn more, go to [Integration with Dataverse](admin-common-data-service.md).

If you already integrated [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[prod_short](includes/prod_short.md)], you can continue to synchronize data using your setup. However, if you upgrade or turn off your [!INCLUDE[crm_md](includes/crm_md.md)] integration, to turn it on again you must connect through [!INCLUDE[prod_short](includes/cds_long_md.md)]. To learn more, go to [Upgrading an Integration with Dynamics 365 Sales](admin-upgrade-sales-to-cds.md).

> [!NOTE]
> Reconnecting through [!INCLUDE[prod_short](includes/cds_long_md.md)] applies default synchronization settings, and overwrites any configurations you have. For example, the default table mappings are applied.

## Integration settings that are specific to a [!INCLUDE[crm_md](includes/crm_md.md)] integration

Integration with [!INCLUDE[prod_short](includes/prod_short.md)] happens through [!INCLUDE[prod_short](includes/cds_long_md.md)], and many standard settings and tables are provided. In addition to the standard settings, there are some that are specific to [!INCLUDE[crm_md](includes/crm_md.md)]. The following sections list those settings.

## Permissions and security roles for user accounts in Sales

When you install the Integration Solution, permissions for the integration user account are configured. If those permissions are changed, you might need to reset them. You can do that by reinstalling the Integration Solution by choosing **Redeploy Integration Solution** on the **Dynamics 365 Connection Setup** page. The following security roles are deployed:

* Dynamics 365 Business Central Integration Administrator
* Dynamics 365 Business Central Integration User

> [!NOTE]
> To use the **Open in Business Central** action in Sales, you must have the following privileges for the following tables:
>
> * You must have Read permissions for the Dynamics 365 Business Central Connection (nav_connection) table.
> * You must have Read, Write, and Delete permissions for the Default Dynamics 365 Business Central Connection (nav_defaultconnection) table.

### Connection settings in the setup guide

You can use an assisted setup guide to quickly set up the connection and specify advanced features, such as coupling between records.

1. Choose **Setup and Extensions**, and then choose **Assisted Setup**.
2. Choose **Set up the Dynamics 365 Sales Connection** to start the assisted setup guide.
3. Fill in the fields as necessary.
4. Optionally, there are advanced settings that can enhance security and enable more capabilities. The following table describes the advanced settings.  

| Field | Description |
|--|--|
| **Import Dynamics 365 Sales Solution** | Install and configure the integration solution in [!INCLUDE[crm_md](includes/crm_md.md)]. |
|**Automatically Synchronize Item Availability**|Specifies that the item availability job queue must be scheduled. The job queue runs every 30 minutes, and updates the availability of the coupled items.|
| **Enable Legacy Sales Order Integration** | When people create sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] and fulfill orders in [!INCLUDE[prod_short](includes/prod_short.md)], this setting integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. To learn more, go to [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration).<br><br>**Note:** You can't use this option if you use the **Bidirectional Synch of Sales Orders** option. The two settings are mutually exclusive. To learn more about this option, go to [Single and bi-directional synchronization of sales orders](#single-and-bi-directional-synchronization-of-sales-orders). |
|**Enable Dynamics 365 Sales Connection** | Enable the connection to [!INCLUDE[crm_md](includes/crm_md.md)]. |
| **Dynamics 365 SDK Version** | This is relevant only if you're integrating with an on-premises version of [!INCLUDE[crm_md](includes/crm_md.md)]. This SDK is the Dynamics 365 software development kit (also referred to as Xrm) you use to connect [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)], and equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)]. |
|**Bidirectional Synch of Sales Orders**|Synchronize sales orders in both directions. To learn more about this option, go [Single and bi-directional synchronization of sales orders](#single-and-bi-directional-synchronization-of-sales-orders).<br><br>**Note:** You can't use this option if you use the **Enable Legacy Sales Order Integration** option. The two settings are mutually exclusive.|

> [!TIP]
> If you also want to integrate with Microsoft Dynamics 365 Field Service, the guide provides an optional step that can help. To learn more about integrating with Field Service, go to [Integrate with Microsoft Dynamics 365 Field Service](admin-integrate-field-service.md).

### Connection settings on the Microsoft Dynamics 365 Connection Setup page

Enter the following information for the connection from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[prod_short](includes/prod_short.md)].

| Field | Description |
|--|--|
|**Dynamics 365 Sales URL**|The URL of your [!INCLUDE[crm_md](includes/crm_md.md)] instance. This setting lets users open the records in [!INCLUDE[prod_short](includes/prod_short.md)] that correspond to records in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, an account or product. The [!INCLUDE[prod_short](includes/prod_short.md)] records open in [!INCLUDE[prod_short](includes/prod_short.md)].|
|**Automatically Synchronize Item Availability**|Specifies that the item availability job queue must be scheduled. The job queue runs every 30 minutes, and updates the availability of the coupled items.|
|**Dynamics 365 SDK Version**|If you're integrating with an on-premises version of [!INCLUDE[crm_md](includes/crm_md.md)], you can use the Dynamics 365 software development kit (also referred to as Xrm) to connect [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version that you select must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)]. This version equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)].|

In addition to these settings, enter the following settings for [!INCLUDE[crm_md](includes/crm_md.md)].

| Field | Description |
|--|--|
| **Sales Order Integration is Enabled** | Enable users to submit sales orders and activated quotes in [!INCLUDE[crm_md](includes/crm_md.md)] and then view and process them in [!INCLUDE[prod_short](includes/prod_short.md)]. This setting integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. To learn more, go to [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration). |
| **Automatically Create Sales Orders** | Create a sales order in [!INCLUDE[prod_short](includes/prod_short.md)] when a user creates and submits one in [!INCLUDE[crm_md](includes/crm_md.md)]. |
| **Automatically Process Sales Quotes** | Process a sales quote in [!INCLUDE[prod_short](includes/prod_short.md)] when a user creates and activates one in [!INCLUDE[crm_md](includes/crm_md.md)]. To learn more, go to [Handling Sales Quotes Data](/dynamics365/business-central/marketing-integrate-dynamicscrm?tabs=new-experience#handling-sales-quotes-data). |
|**Bidirectional Synch of Sales Orders**|Synchronize sales orders in both directions. To learn more, go to [Single and bi-directional synchronization of sales orders](#single-and-bi-directional-synchronization-of-sales-orders).|
<!--
### User Account Settings
Integration with Business Central through [!INCLUDE [cds_long_md](includes/cds_long_md.md)] requires an administrator user account and an account that is used only for the connection between the apps. This account is called the "integration user." When you install the CDS Base Integration Solution, permissions for the integration user account are configured in [!INCLUDE[crm_md](includes/crm_md.md)]. If those permissions are changed you might need to reset them. You can do that by reinstalling the Integration Solution or by manually resetting them. The following tables list the minimum permissions for the user accounts in [!INCLUDE[crm_md](includes/crm_md.md)].  -->
### Single and bi-directional synchronization of sales orders

When you set up your integration, there are options that control the direction in which you synchronize sales orders, and how you submit them.

The **Bidirectional Synch of Sales Orders** option lets you synchronize sales orders from Sales to [!INCLUDE [prod_short](includes/prod_short.md)], and vice versa. For example, if a customer changes their mind about the product or quantity in [!INCLUDE[crm_md](includes/crm_md.md)], you can archive the sales document and create a new document in [!INCLUDE[prod_short](includes/prod_short.md)]. The same is true for changes in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, when prices, tax amounts, or expected shipment dates change, the changes synchronize to [!INCLUDE[crm_md](includes/crm_md.md)]. Bidirectional synchronization helps keep your sellers up to date with the latest changes and the status of sales orders.

For bidirectional synchronization, you make sales orders available for synchronization when you change their status to **Submitted** in Sales. When you set that status, you can no longer change information on the order's lines. When you synchronize, the order is transferred to [!INCLUDE [prod_short](includes/prod_short.md)] with the status **Released**. If there's a mistake, you can revert the order to **Open** (in [!INCLUDE [prod_short](includes/prod_short.md)]) or **Active** (in Sales), and then add or delete lines to correct the mistake, and submit the order again.

> [!TIP]
> When you enable the **Bidirectional Synch of Sales Orders** option, [!INCLUDE [prod_short](includes/prod_short.md)] creates a record on the **Sales Order Archives** page when you post or change information on an order. For example, the archived versions can be useful for exploring an order's history.

The **Enable Legacy Sales Order Integration** option synchronizes only from Sales to [!INCLUDE [prod_short](includes/prod_short.md)]. For this option, you use the **Submit** action in Sales to make orders available for synchronization. When you do, you can no longer change any information on the order. When you synchronize, the order is transferred to [!INCLUDE [prod_short](includes/prod_short.md)] with the status **Released**.

To use this option, you must provide credentials for an administrator user account in [!INCLUDE[crm_md](includes/crm_md.md)]. To learn more, go to [Handle Sales Order Data](marketing-integrate-dynamicscrm.md#handle-sales-order-data).

> [!NOTE]
> The **Bidirectional Synch of Sales Orders** and **Enable Legacy Sales Order Integration** options are mutually exclusive. You can't use both options at the same time.

For both options, [!INCLUDE [prod_short](includes/prod_short.md)] shows all sales orders with the **Submitted** status on the **Orders - Microsoft Dynamics 365 Sales** page.

### Standard Sales entity mapping for synchronization

Entities in [!INCLUDE[crm_md](includes/crm_md.md)], such as orders, are integrated with equivalent types of tables in [!INCLUDE[prod_short](includes/prod_short.md)], such as sales orders. To work with [!INCLUDE[crm_md](includes/crm_md.md)] data you set up links, called couplings, between tables in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].

The following table lists the standard mapping between tables in [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] that [!INCLUDE[prod_short](includes/prod_short.md)] provides.

| [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[crm_md](includes/crm_md.md)] | Synchronization Direction | Default Filter |
|--|--|--|--|
| Unit of Measure | Unit Group | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Item | Product | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | Sales contact filter: **Product Type** is **Sales Inventory** |
| Resource | Product | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] | Sales contact filter: **Product Type** is **Services** |
| Item Unit of Measure | CRM UOM |[!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
| Resource Unit of Measure | CRM UOM |[!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]||
| Unit Group | CRM Uomschedule | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] ||
| Customer Price Group | Price List | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Sales Price | Product Price List | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] | [!INCLUDE[prod_short](includes/prod_short.md)] contact filter: **Sales Code** isn't blank, **Sales Type** is **Customer Price Group** |
| Opportunity | Opportunity | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] |  |
| Sales Invoice Header | Invoice | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Sales Invoice Line | Invoice Product | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] |  |
| Sales Order Header | Sales Order | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] <br><br> To synchronize in both directions, you must turn on the **Bidirectional Synch of Sales Orders** toggle on the **Dynamics 365 Connection Setup** page.| [!INCLUDE[prod_short](includes/prod_short.md)] Sales Header filter: **Document Type** is **Order** and **Status** is **Released** |
| Sales Order Notes | Sales Order Notes | [!INCLUDE[prod_short](includes/prod_short.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[prod_short](includes/prod_short.md)] |  |

> [!NOTE]
> The mappings for the **Item Unit of Measure**, **Resource Unit of Measure**, and **Unit Group** tables are available only if your administrator turns on the **Unit Group Mapping** toggle on the **Microsoft Dynamics 365 Connection Setup** page. To learn more, go to [Synchronizing Items and Resources with Products in Different Units of Measure](admin-prepare-dynamics-365-for-sales-for-integration.md#synchronize-items-and-resources-with-products-with-different-units-of-measure).

## Synchronize items and resources with products with different units of measure

Businesses often produce or purchase the items in one unit of measure, and then sell them in another. To synchronize items that use multiple units of measure, you must turn on the **Unit Group Mapping** toggle on the **Microsoft Dynamics 365 Connection Setup** page.

When you turn on the feature update, a new Unit Group table is created and assigned to each item and resource in [!INCLUDE[prod_short](includes/prod_short.md)]. The tables let you map the Unit Group, Item Unit of Measure, and Resource Unit of Measure tables in [!INCLUDE[prod_short](includes/prod_short.md)] to the Dynamics 365 Sales Unit Group in [!INCLUDE[crm_md](includes/crm_md.md)]. The following image shows the mappings.

:::image type="content" source="media/unit group 1.png" alt-text="Table mappings for unit groups":::

You can create multiple units of measure for each unit group, and assign the groups to products in [!INCLUDE[crm_md](includes/crm_md.md)]. Afterward, you can synchronize the products with items and resources in [!INCLUDE[prod_short](includes/prod_short.md)]. You can manually couple item units of measure or resource units of measure with a unit group. When you do, if the unit group for the item or resource isn't coupled to a unit group in [!INCLUDE[crm_md](includes/crm_md.md)], [!INCLUDE[prod_short](includes/prod_short.md)] automatically creates the unit group in [!INCLUDE[crm_md](includes/crm_md.md)].

### Map items and resources to products

When you turn on the **Unit Group Mapping** toggle on the **Microsoft Dynamics 365 Connection Setup** page, the following happens:

* New mappings are created for items and resources.
* Existing mappings are deleted.
* A data upgrade creates unit groups for items and resources.

To use the new mappings, you must synchronize unit groups, item unit of measure, and resource unit of measures. You must also resynchronize items and resources.

> [!NOTE]
> [!INCLUDE[crm_md](includes/crm_md.md)] doesn't allow you to change a unit group for a product. Therefore, you must retire your products and uncouple the items and resources, and then synchronize by creating new products in [!INCLUDE[crm_md](includes/crm_md.md)]. 

The following steps describe the steps to start mapping unit groups:

1. Be sure that products in [!INCLUDE[crm_md](includes/crm_md.md)] aren't coupled with items or resources in [!INCLUDE[prod_short](includes/prod_short.md)]. If they are, go to the **Items** and/or **Resources** pages and use the filter options to select the coupled records. Then choose the **Dynamics 365 Sales** action, and select **Uncouple**. This action schedules a background job to uncouple the records. While the job is running, you can check its status by using the **Synchronization Log** action. To learn more, go to [Coupling and Synchronizing](admin-how-to-couple-and-synchronize-records-manually.md).
2. Because new products are created in [!INCLUDE[crm_md](includes/crm_md.md)] with new unit groups, to avoid duplicate names, do one of the following steps:

  * Rename your products, and then retire them in [!INCLUDE[crm_md](includes/crm_md.md)]. To learn more, go to [Retire products (Sales Hub)](/dynamics365/sales-enterprise/retire-product). To bulk edit your products in Microsoft Excel, sign in to Power Apps, choose your environment, go to the **Product** table, and then choose the **Data** tab. Clear any filters that are applied. In the **Data** group, choose the **Edit Data in Excel** action. Add a prefix or suffix to the coupled products, and then retire them.
    * Retire your products and delete them. 

3. Follow these steps to synchronize **Unit Groups**, **Unit of Measures**, **Items**, and **Resources**:
    1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the **Dynamics 365 Sales Connection Setup** page.
    2. Use the **Run Full Synchronization** action to open the **Dataverse Full Synch. Review** page.
    3. For the **ITEM UOM**, **RESOURCE UOM**, AND **UNIT GROUP** mappings, choose the **Recommend Full Synchronization** action.
    4. Choose the **Sync All** action.

    > [!NOTE]
    > This action fully synchronizes all mappings. To prevent mappings from synchronizing, delete the mappings from the page. Deleting the mappings only removes them from the current full synchronization, and doesn't delete the mappings.
4. Choose the **ITEM-PRODUCT** mapping, and then choose the **Restart** action. Restarting creates new products from the items in [!INCLUDE[crm_md](includes/crm_md.md)], and assigns a new unit group that is specific to the item.
5. Choose the **RESOURCE-PRODUCT** mapping, and then choose the **Restart** action. Restarting creates new products from the resources in [!INCLUDE[crm_md](includes/crm_md.md)], and assigns a new unit group that is specific to the resources.

### Synchronization rules

The following table lists the rules that control the synchronization between [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)]. These rules are in addition to rules defined for [!INCLUDE [cds_long_md](includes/cds_long_md.md)], which also apply. To learn more, go to [Standard Entity Mapping](admin-synchronizing-business-central-and-sales.md#standard-table-mapping-for-synchronization).

> [!NOTE]  
> Changes to data that were made by the integration user account aren't synchronized. Therefore, we recommended that you don't change data while using that account. To learn more, go to [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

|Table|Rule|
|-----|----|
|Units of Measure|Units of measure are synchronized with unit groups in [!INCLUDE[crm_md](includes/crm_md.md)]. There can only be one unit of measure defined in the unit group.|
|Items|When it synchronizes items with [!INCLUDE[crm_md](includes/crm_md.md)] products, [!INCLUDE[prod_short](includes/prod_short.md)] automatically creates a price list in [!INCLUDE[crm_md](includes/crm_md.md)]. To avoid synchronization errors, you shouldn't modify this price list manually.|
|Resources|Resources are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] products that have product type Service.|
|Customer Price Groups|Customer price groups are synchronized with Sales price lists.|
|Sales Prices|Sales prices that have sales type Customer Price Group and have a sales code defined are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] price list lines|
|Opportunities|Opportunities are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] opportunities. The Salesperson Code value defines the owner of the coupled table in [!INCLUDE[crm_md](includes/crm_md.md)].|
|Posted Sales Invoices|Posted sales invoices are synchronized with sales invoices. Before an invoice can be synchronized, it's better to synchronize all other tables that can participate in the invoice, from salespersons to price lists. The Salesperson Code value in the invoice header defines the owner of the coupled table in Sales.|
|Sales Orders|When you enable sales order integration, when you release sales orders in [!INCLUDE[prod_short](includes/prod_short.md)] that were created from submitted sales orders in [!INCLUDE[crm_md](includes/crm_md.md)], they synchronize with sales orders in [!INCLUDE[crm_md](includes/crm_md.md)]. Before you synchronize orders, we recommend that you first synchronize all tables involved with the order. For example, sales persons and price lists. The Salesperson Code field in the order header defines the owner of the coupled table in [!INCLUDE[crm_md](includes/crm_md.md)].|

### Synchronization jobs for a Sales integration

The jobs are run in the following order to avoid coupling dependencies between tables. There are more jobs available from [!INCLUDE [cds_long_md](includes/cds_long_md.md)]. To learn more, go to [Use Job Queues to Schedule Tasks](./admin-job-queues-schedule-tasks.md).

1. UNITOFMEASURE - Dynamics 365 Sales synchronization job  
2. RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job  
3. ITEM-PRODUCT - Dynamics 365 Sales synchronization job  
4. CUSTPRCGRP-PRICE - Dynamics 365 Sales synchronization job.
5. SALESPRC-PRODPRICE - Dynamics 365 Sales synchronization job.
6. POSTEDSALESINV-INV - Dynamics 365 Sales synchronization job.

### Default synchronization job queue entries

The following table describes the default synchronization jobs for [!INCLUDE[crm_md](includes/crm_md.md)].  

|Job Queue Entry|Description|Direction|Integration Table Mapping|Default Synchronization Frequency (mins)|Default inactivity sleep time (mins)|  
|---------------------|---------------------------------------|---------------|-------------------------------|-----|-----|  
|UNITOFMEASURE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] unit groups with [!INCLUDE[prod_short](includes/prod_short.md)] units of measure.|From [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|UNIT OF MEASURE|30|720<br> (12 hrs)|
|RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] products with [!INCLUDE[prod_short](includes/prod_short.md)] resources.|From [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|RESOURCE-PRODUCT|30|720<br> (12 hrs)|
|ITEM - PRODUCT - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] products with [!INCLUDE[prod_short](includes/prod_short.md)] items.|From [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|ITEM-PRODUCT|30|1440<br> (24 hrs)|
|CUSTPRCGRP-PRICE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] sales price lists with [!INCLUDE[prod_short](includes/prod_short.md)] customer price groups.| |CUSTOMER PRICE GROUPS-SALES PRICE LISTS|30|1440<br> (24 hrs)|
|SALESPRC-PRODUCTPRICE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] product prices with [!INCLUDE[prod_short](includes/prod_short.md)] sales prices.||PRODUCT PRICE-SALES PRICE|30|1440<br> (24 hrs)|
|POSTEDSALESINV-INV - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] invoices with [!INCLUDE[prod_short](includes/prod_short.md)] posted sales invoices.|From [!INCLUDE[prod_short](includes/prod_short.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|INVOICES-POSTED SALES INVOICES|30|1440<br> (24 hrs)|
|Customer Statistics - Dynamics 365 Sales synchronization|Updates [!INCLUDE[crm_md](includes/crm_md.md)] accounts with the latest [!INCLUDE[prod_short](includes/prod_short.md)] customer data. In [!INCLUDE[crm_md](includes/crm_md.md)], this information appears in **Business Central Account Statistics** quick view form of accounts that are coupled to [!INCLUDE[prod_short](includes/prod_short.md)] customers.<br /><br /> This data can also be updated manually from each customer record. To learn more, go to [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md). </BR></BR>**Note:**  This job queue entry is relevant only if the [!INCLUDE[prod_short](includes/prod_short.md)] integration solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)]. |Not applicable|Not applicable|30|Not applicable|

## Connect to on-premises versions of Business Central 2019 release wave 1 and Microsoft Dynamics NAV 2018

The Microsoft Power Platform team [announced](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-dataverse) that it's deprecating the Office 365 authentication type. If you're using a version of [!INCLUDE[prod_short](includes/prod_short.md)] on-premises that's earlier than [!INCLUDE [prod_short](includes/prod_short.md)] 2019 release wave 1, you must use the OAuth authentication type to connect to [!INCLUDE[crm_md](includes/crm_md.md)] online. The steps in this section describe how to connect the following product versions:

* Business Central 2019 release wave 1
* Microsoft Dynamics NAV 2018

### Prerequisites

* You must have a Microsoft Azure subscription. A trial account works for application registration.
* [!INCLUDE[crm_md](includes/crm_md.md)] is configured to use one of the following authentication types:

   * Office 365 (legacy)

     > [!IMPORTANT]
     > Effective April 2022, Office365 (legacy) is no longer supported. To learn more, go to [Important changes (deprecations) coming in Power Apps, Power Automate and customer engagement apps](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-dataverse).

   * OAuth

### Connect Business Central 2019 release wave 1 and Dynamics NAV 2018

1. Import the Microsoft Dynamics 365 Business Central Integration Solution into your [!INCLUDE[crm_md](includes/crm_md.md)] environment. The integration solution is available in the CrmCustomization folder on your [!INCLUDE[prod_short](includes/prod_short.md)] or Dynamics NAV 2018 installation DVD. Depending on your product version, import one of the following solutions:

   * For [!INCLUDE[prod_short](includes/prod_short.md)], the folder contains the DynamicsNAVIntegrationSolution_v9 and DynamicsNAVIntegrationSolution_v91. solutions. The solution you should import depends on the version of [!INCLUDE[crm_md](includes/crm_md.md)] you're connecting to. [!INCLUDE[crm_md](includes/crm_md.md)] online requires the DynamicsNAVIntegrationSolution_v91 integration solution.
   * For Dynamics NAV 2018, install the DynamicsNAVIntegrationSolution solution.

2. Create a non-interactive integration user in your [!INCLUDE[crm_md](includes/crm_md.md)] environment, and assign the user the following security roles. To learn more, go to [Create a non-interactive user account](/power-platform/admin/create-users-assign-online-security-roles#create-a-non-interactive-user-account).

   * Dynamics 365 Business Central Integration Administrator
   * Dynamics 365 Business Central Integration User

   > [!Important]
   > This user must not have the System Administrator security role. Also, you cannot use the system administrator account as the integration user.

3. In the Azure portal, create an app registration for [!INCLUDE[prod_short](includes/prod_short.md)]. To learn more, go to [Register an application in Microsoft Entra ID](/powerapps/developer/data-platform/walkthrough-register-app-azure-active-directory).
  
   > [!NOTE]
   > We recommend that you register the app in the same tenant as your [!INCLUDE [cds_long_md](includes/cds_long_md.md)] environment so that you don't have to consent to giving access to the environment. If you register the app in another environment, you must sign in to Microsoft Entra ID using the administrator account for your [!INCLUDE [cds_long_md](includes/cds_long_md.md)] environment and give consent.
   >
   > Additionally, the app that you register must not have a secret. Connecting an app with a secret to [!INCLUDE [cds_long_md](includes/cds_long_md.md)] is available only in [!INCLUDE [prod_short](includes/prod_short.md)] 2020 release wave 1 and later.
  
4. Depending on your product version, do one of the following steps:

    * In [!INCLUDE[prod_short](includes/prod_short.md)], search for **Microsoft Dynamics 365 Connection Setup**, and then choose the related link.
    * In Dynamics NAV 2018, search for **Microsoft Dynamics 365 for Sales Connection Setup**, and then choose the related link.

5. In the **Authentication Type** field, choose the option for OAuth.
6. Choose the CRM SDK version that matches solution version you imported in step 1.

   > [!NOTE]
   > This step is only relevant for [!INCLUDE[prod_short](includes/prod_short.md)].

7. Enter the URL of your [!INCLUDE[crm_md](includes/crm_md.md)] environment, and then enter the user name and password for the integration user. 

   * In [!INCLUDE[prod_short](includes/prod_short.md)], use the **Server Address** field.
   * In Dynamics NAV 2018, use the **Dynamics 365 Sales URL** field.

8. In the **Connection String** field, specify the ID of the app registration. This field has two tokens in which the ID of your application should be specified.

   |Token           |Description  |
   |----------------|-------------|
   |**AppId**       |Set to the application ID.      |
   |**RedirectUri** |Set to the application ID, but add the **app://** prefix.         |

    **Example**
    To review an example of the connection string, go to [Create a connection string](/power-apps/developer/data-platform/xrm-tooling/use-connection-strings-xrm-tooling-connect#create-a-connection-string) in the [!INCLUDE [cds_long_md](includes/cds_long_md.md)] documentation.
9. Enable the connection.

   > [!Note]
   > If you want to configure a connection to a [!INCLUDE[crm_md](includes/crm_md.md)] instance with a specific authentication type, fill in the fields on the **Authentication Type Details** FastTab. To learn more, go to [Authentication with Microsoft Dataverse web services](/powerapps/developer/data-platform/authentication). This step is not required when connecting an online version of [!INCLUDE[prod_short](includes/prod_short.md)].

## Related information

[Setting Up User Accounts for Integrating with [!INCLUDE[crm_md](includes/crm_md.md)]](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to [!INCLUDE[crm_md](includes/crm_md.md)]](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronizing Business Central and [!INCLUDE[crm_md](includes/crm_md.md)]](admin-synchronizing-business-central-and-sales.md)  
[Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration)

[!INCLUDE[footer-include](includes/footer-banner.md)]
