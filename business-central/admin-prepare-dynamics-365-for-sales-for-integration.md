---
title: Integrating with Dynamics 365 Sales| Microsoft Docs
description: Learn how to get Dynamics 365 Business Central ready to integrate with Dynamics 365 Sales.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, integrating
ms.date: 04/01/2020
ms.author: bholtorf

---
# Integrating with Dynamics 365 Sales
The sales person role is often considered as one the most outward-facing jobs in a business. However, it can be helpful for sales people to be able to look inward in the business and see what is happening on the back end. By integrating [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)], you can give your sales people that insight by enabling them to view information in [!INCLUDE[d365fin](includes/d365fin_md.md)] while they are working in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, when preparing a sales quote it could be useful to know whether you have enough inventory to fulfill the order. For more information, see [Using Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md).

> [!NOTE]
> This topic describes the process of integrating the online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)] through [!INCLUDE[d365fin](includes/cds_long_md.md)]. For information about on-premises configuration, see [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration.md).

## Integrating Through Common Data Service
[!INCLUDE[d365fin](includes/d365fin_md.md)] also integrates with [!INCLUDE[d365fin](includes/cds_long_md.md)], which makes it easy to connect and synchronize data with other Dynamics 365 applications, such as [!INCLUDE[crm_md](includes/crm_md.md)], or even apps that you build yourself. If you are integrating for the first time, we recommend that you do so through [!INCLUDE[d365fin](includes/cds_long_md.md)]. For more information, see [Integration with Common Data Service](admin-common-data-service.md).

If you have already integrated [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[d365fin](includes/d365fin_md.md)], you can continue to synchronize data using your setup. However, if you upgrade or turn off your [!INCLUDE[crm_md](includes/crm_md.md)] integration, to turn it on again you must connect through [!INCLUDE[d365fin](includes/cds_long_md.md)]. For more information, see [Upgrading an Integration with Dynamics 365 Sales](admin-upgrade-sales-to-cds.md).

> [!NOTE]
> Reconnecting through [!INCLUDE[d365fin](includes/cds_long_md.md)] will apply default synchronization settings, and will overwrite any configurations you have. For example, the default table mappings will be applied.

## Integration Settings that are Specific to a [!INCLUDE[crm_md](includes/crm_md.md)] Integration
Integration with [!INCLUDE[d365fin](includes/d365fin_md.md)] happens through [!INCLUDE[d365fin](includes/cds_long_md.md)], and there are a lot of standard settings and entities that are provided by the integration. In addition to the standard settings, there are some that are specific to [!INCLUDE[crm_md](includes/crm_md.md)]. The following sections list those.

## Permissions and Security Roles for User Accounts in Sales
When you install the Integration Solution, permissions for the integration user account are configured. If those permissions are changed you might need to reset them. You can do that by reinstalling the Integration Solution by choosing **Redeploy Integration Solution** on the **Dynamics 365 Connection Setup** page. The following security roles are deployed:

* Dynamics 365 Business Central Integration Administrator
* Dynamics 365 Business Central Integration User
* Dynamics 365 Business Central Product Availability User

### Connection Settings in the Setup Guide
You can use an assisted setup guide to quickly set up the connection and specify advanced features, such as coupling between records.

1. Choose **Setup and Extensions**, and then choose **Assisted Setup**.
2. Choose **Set up the Dynamics 365 Sales Connection** to start the assisted setup guide.
3. Fill in the fields as necessary.
4. Optionally, there are advanced settings that can enhance security and enable additional capabilities, such as sales order processing and viewing inventory levels. The following table describes the advanced settings.  

|Field|Description|
|-----|-----|
|**Import Dynamics 365 Sales Solution**|Enable this to install and configure the integration solution in [!INCLUDE[crm_md](includes/crm_md.md)]. <!--For more information, see [About the Base CDS Integration Solution](admin-common-data-service.md#about-the-business-central-integration-solution). Need to add a new topic-->|
|**Publish Item Availability Web Service**|Enable people who are using [!INCLUDE[crm_md](includes/crm_md.md)] to view the availability of items (products) in inventory in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This requires a [!INCLUDE[d365fin](includes/d365fin_md.md)] user account with a web services access key. Assigning the key is a two-step process. On the user account in [!INCLUDE[d365fin](includes/d365fin_md.md)] you must choose the **Change Web Service Key** action. In the Set Up Dynamics 365 Sales Connection assisted setup guide, you must specify the Dynamics 365 Business Central OData web service URL, and provide [!INCLUDE[d365fin](includes/d365fin_md.md)] user credentials for accessing the service. For more information, see [OData Web Services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services).|
|**Business Central OData Web Service URL**|If you enable the web service for viewing item availability, the URL for the OData Web service is provided for you.|
|**Business Central OData Web Service Username**|The name of the [!INCLUDE[d365fin](includes/d365fin_md.md)] user account that [!INCLUDE[crm_md](includes/crm_md.md)] uses to retrieve information about item availability in [!INCLUDE[d365fin](includes/d365fin_md.md)] through the OData web service.|
|**Business Central OData Web Service Accesskey**|The access key for the user account that [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through the OData web service. The key is assigned to the user chosen in the **Business Central OData Web Service Username** field. To get the key, choose the **Look up value** button next to the user name, choose the user, choose **Manage**, and then **Edit**. On the user card, choose **Actions**, **Authentication**, and then choose **Change Web Service Key**.|
|**Enable Sales Order Integration**|When people create sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] and fullfill orders in [!INCLUDE[d365fin](includes/d365fin_md.md)], this integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration). This requires that you provide credentials for an administrator user account in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Handling Sales Order Data](marketing-integrate-dynamicscrm.md#handling-sales-order-data).|
|**Enable CDS Connection**|Enable the connection to [!INCLUDE[d365fin](includes/cds_long_md.md)].|
|**Dynamics 365 SDK Version**|This is relevant only if you are integrating with an on-premises version of [!INCLUDE[crm_md](includes/crm_md.md)]. This is the Dynamics 365 software development kit (also referred to as Xrm) you use to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)], and equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)].|

### Connection Settings on the Microsoft Dynamics 365 Connection Setup Page 
Enter the following information for the connection from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)].

|Field|Description|
|-----|-----|
|**Dynamics 365 Sales URL**|The URL of your [!INCLUDE[crm_md](includes/crm_md.md)] instance. This enables users to open corresponding records in [!INCLUDE[d365fin](includes/d365fin_md.md)] from records in [!INCLUDE[crm_md](includes/crm_md.md)], such as an account or product. The [!INCLUDE[d365fin](includes/d365fin_md.md)] records open in [!INCLUDE[d365fin](includes/d365fin_md.md)].|
|**Item Availability Web Service Enabled**|Enable people who are using [!INCLUDE[crm_md](includes/crm_md.md)] to view the availability of items (products) in inventory in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you enable this, you must also provide a user name and an access key for the [!INCLUDE[crm_md](includes/crm_md.md)] to use to query OData Web Service for availablity of items (products). For more information, see [OData Web Services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services.md).|
|**Dynamics 365 Business Central OData Web Service URL**|If you enable the Item Availability Web Service, the URL for the OData Web service is provided for you. Set this field to the URL of the [!INCLUDE[d365fin](includes/d365fin_md.md)] instance to use.<br /><br /> To reset the field to the default URL for the [!INCLUDE[d365fin](includes/d365fin_md.md)], choose **Reset Web Client URL** action.<br /><br /> This field is relevant only if the [!INCLUDE[d365fin](includes/d365fin_md.md)] Integration Solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)].|
|**Dynamics 365 Business Central OData Web Service Username**|The name of the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web service.|
|**Dynamics 365 Business Central OData Web Service Accesskey**|The access key for the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web service. The key is assigned to the user chosen in the **Dynamics 365 Business Central OData Web Service Username** field. To get the key, choose the **Look up value** button next to the user name, choose the user, choose **Manage**, and then **Edit**. On the user card, choose **Actions**, **Authentication**, and then choose **Change Web Service Key**.|
|**Dynamics 365 SDK Version**|If you are integrating with an on-premesis version of [!INCLUDE[crm_md](includes/crm_md.md)], this is the Dynamics 365 software development kit (also referred to as Xrm) you use to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version that you select must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)]. This version equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)].|-->

In addition to the settings above, enter the following settings for [!INCLUDE[crm_md](includes/crm_md.md)].

|Field|Description|
|-----|-----|
|**Sales Order Integration is Enabled**|Enable users to submit sales orders and activated quotes in [!INCLUDE[crm_md](includes/crm_md.md)] and then view and process them in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration).|
|**Automatically Create Sales Orders**|Create a sales order in [!INCLUDE[d365fin](includes/d365fin_md.md)] when a user creates and submits one in [!INCLUDE[crm_md](includes/crm_md.md)].|
|**Automatically Process Sales Quotes**|Process a sales quote in [!INCLUDE[d365fin](includes/d365fin_md.md)] when a user creates and activates one in [!INCLUDE[crm_md](includes/crm_md.md)].|

<!--
### User Account Settings
Integrate with Business Central through Common Data Service requires an administrator user account and an account that is used only for the connection between the apps. This account is called the "integration user." When you install the CDS Base Integration Solution, permissions for the integration user account are configured in [!INCLUDE[crm_md](includes/crm_md.md)]. If those permissions are changed you might need to reset them. You can do that by reinstalling the Integration Solution or by manually resetting them. The following tables list the minimum permissions for the user accounts in [!INCLUDE[crm_md](includes/crm_md.md)].  -->

### Standard Sales Entity Mapping for Synchronization
Entities in [!INCLUDE[crm_md](includes/crm_md.md)], such as orders, are integrated with equivalent types of entities in [!INCLUDE[d365fin](includes/d365fin_md.md)],such as sales orders. To work with [!INCLUDE[crm_md](includes/crm_md.md)] data you set up links, called couplings, between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].

The following table lists the standard mapping between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] that [!INCLUDE[d365fin](includes/d365fin_md.md)] provides.

|[!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[crm_md](includes/crm_md.md)]|Synchronization Direction|Default Filter|
|-------------------------------------------|-----|-------------------------|--------------|
|Unit of Measure|Unit Group|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Item|Product|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Product Type** is **Sales Inventory**|
|Resource|Product|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Product Type** is **Services**|
|Customer Price Group|Price List|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Sales Price|Product Price List|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] contact filter: **Sales Code** is not blank, **Sales Type** is **Customer Price Group**|
|Opportunity|Opportunity|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[d365fin](includes/cds_long_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]| |
|Sales Invoice Header|Invoice|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Sales Invoice Line|Invoice Product|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
|Sales Order Header|Sales Order|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] Sales Header filter: **Document Type** is Order, **Status** is Released|
|Sales Order Notes|Sales Order Notes|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]| |

### Synchronization Rules
The following table lists the rules that control the synchronization between [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)]. These are in addition to rules defined for Common Data Service, which also apply. For more information, see [Standard Entity Mapping](/dynamics365/business-central/admin-synchronizing-business-central-and-sales?branch=master-cds-crm#standard-entity-mapping-for-synchronization).

> [!NOTE]  
> Changes to data in  that were made by the integration user account are not synchronized. Therefore, we recommended that you do not change data while using that account. For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

|Table|Rule|
|-----|----|
|Units of Measure|Units of measure are synchronized with unit groups in [!INCLUDE[crm_md](includes/crm_md.md)]. There can only be one unit of measure defined in the unit group.|
|Items|When synchronizing items with [!INCLUDE[crm_md](includes/crm_md.md)] products, [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically creates a price list in [!INCLUDE[crm_md](includes/crm_md.md)]. To avoid synchronization errors, you should not modify this price list manually.|
|Resources|Resources are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] products that have product type Service.|
|Customer Price Groups|Customer price groups are synchronized with Sales price lists.|
|Sales Prices|Sales prices that have sales type Customer Price Group and have a sales code defined are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] price list lines|
|Opportunities|Opportunities are synchronized with [!INCLUDE[crm_md](includes/crm_md.md)] opportunities. The Salesperson Code value defines the owner of the coupled entity in [!INCLUDE[crm_md](includes/crm_md.md)].|
|Posted Sales Invoices|Posted sales invoices are synchronized with sales invoices. Before an invoice can be synchronized, it is better to synchronize all other entities that can participate in the invoice, from salespersons to price lists. The Salesperson Code value in the invoice header defines the owner of the coupled entity in Sales.|
|Sales Orders|When sales order integration is enabled, sales orders in [!INCLUDE[d365fin](includes/d365fin_md.md)] that are created from submitted sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] are synchronized with sales orders in INCLUDE SALES when they are released. Before you synchronize orders, we recommend that you first synchronize all entities that the are involved with the order, such as sales persons and price lists. The Salesperson Code field in the order header defines the owner of the coupled entity in [!INCLUDE[crm_md](includes/crm_md.md)].|

### Synchronization Jobs for a Sales Integration
The jobs are run in the following order to avoid coupling dependencies between entities. There are additional jobs available from Common Data Service. For more information, see [Use Job Queues to Schedule Tasks](/dynamics365/business-central/admin-job-queues-schedule-tasks.md).

1. UNITOFMEASURE - Dynamics 365 Sales synchronization job  
2. RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job  
3. ITEM-PRODUCT - Dynamics 365 Sales synchronization job  
4. CUSTPRCGRP-PRICE - Dynamics 365 Sales synchronization job.
5. SALESPRC-PRODPRICE - Dynamics 365 Sales synchronization job.
6. POSTEDSALESINV-INV - Dynamics 365 Sales synchronization job.

### Default Synchronization Job Queue Entries  
The following table describes the default synchronization jobs for Sales.  

|Job Queue Entry|Description|Direction|Integration Table Mapping|Default Synchronization Frequency (mins)|Default inactivity sleep time (mins)|  
|---------------------|---------------------------------------|---------------|-------------------------------|-----|-----|  
|UNITOFMEASURE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] unit groups with [!INCLUDE[d365fin](includes/d365fin_md.md)] units of measure.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|UNIT OF MEASURE|30|720<br> (12 hrs)|
|RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] products with [!INCLUDE[d365fin](includes/d365fin_md.md)] resources.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|RESOURCE-PRODUCT|30|720<br> (12 hrs)|
|ITEM - PRODUCT - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] products with [!INCLUDE[d365fin](includes/d365fin_md.md)] items.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|ITEM-PRODUCT|30|1440<br> (24 hrs)|
|CUSTPRCGRP-PRICE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] sales price lists with [!INCLUDE[d365fin](includes/d365fin_md.md)] customer price groups.| |CUSTOMER PRICE GROUPS-SALES PRICE LISTS|30|1440<br> (24 hrs)|
|SALESPRC-PRODUCTPRICE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] product prices with [!INCLUDE[d365fin](includes/d365fin_md.md)] sales prices.||PRODUCT PRICE-SALES PRICE|30|1440<br> (24 hrs)|
|POSTEDSALESINV-INV - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[crm_md](includes/crm_md.md)] invoices with [!INCLUDE[d365fin](includes/d365fin_md.md)] posted sales invoices.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]|INVOICES-POSTED SALES INVOICES|30|1440<br> (24 hrs)|
|Customer Statistics - Dynamics 365 Sales synchronization|Updates [!INCLUDE[crm_md](includes/crm_md.md)] accounts with the latest [!INCLUDE[d365fin](includes/d365fin_md.md)] customer data. In [!INCLUDE[crm_md](includes/crm_md.md)], this information appears in **Business Central Account Statistics** quick view form of accounts that are coupled to [!INCLUDE[d365fin](includes/d365fin_md.md)] customers.<br /><br /> This data can also be updated manually from each customer record. For more information, see [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md). </BR></BR>**Note:**  This job queue entry is relevant only if the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)]. |Not applicable|Not applicable|30|Not applicable| 


### Note for On-Premises Versions
> [!Note]
> If you are connecting an on-premises version of [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)] and you want to configure a connection to a [!INCLUDE[crm_md](includes/crm_md.md)] instance with a specific authentication type, fill in the fields on the **Authentication Type Details** FastTab. For more information, see [Use connection strings in XRM tooling to connect to Dynamics 365](https://go.microsoft.com/fwlink/?linkid=843055). This step is not required when connecting an online version of [!INCLUDE[d365fin](includes/d365fin_md.md)].

## See Also  
[Setting Up User Accounts for Integrating with [!INCLUDE[crm_md](includes/crm_md.md)]](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to [!INCLUDE[crm_md](includes/crm_md.md)]](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronizing Business Central and [!INCLUDE[crm_md](includes/crm_md.md)]](admin-synchronizing-business-central-and-sales.md)  
[Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration)
