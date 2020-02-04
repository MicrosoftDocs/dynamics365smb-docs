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
ms.date: 10/01/2019
ms.author: bholtorf

---
# Integrating with Dynamics 365 Sales
The sales person role is often considered as one the most outward-facing jobs in a business. However, it can be helpful for sales people to be able to look inward in the business and see what is happening on the back end. By integrating [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)], you can give your sales people that insight by enabling them to view information in [!INCLUDE[d365fin](includes/d365fin_md.md)] while they are working in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, when preparing a sales quote it could be useful to know whether you have enough inventory to fulfill the order. For more information, see [Using Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md).

> [!NOTE]
> These steps describe the process of integrating the online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)]. For information about on-premises configuration, see [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

<!--## Software Requirements
You must have an Office 365 subscription, and both [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)] must be part of the same organization.  -->

## Overview of the Integration Process
The following steps provide an overview of the steps to integrate [!INCLUDE[crm_md](includes/crm_md.md)] with [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!Note]  
> These tasks require the **System Administrator** security role in [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)].  

1. In the Microsoft 365 admin center, set up a user account for connecting to and synchronizing data with [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

2. Assign licenses for [!INCLUDE[crm_md](includes/crm_md.md)] to the [!INCLUDE[d365fin](includes/d365fin_md.md)] users who will use the integrated apps.

3. Set up a connection to [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Set Up a Connection to Dynamics 365 Sales](admin-how-to-set-up-a-dynamics-crm-connection.md).  

4. Optional: Couple [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] records. For more information, see [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md).

5. Synchronize data between the apps. For more information, see [Synchronizing Business Central and Dynamics 365 Sales](admin-synchronizing-business-central-and-sales.md).  

## About the Business Central Integration Solution
The solution lets people view information in [!INCLUDE[d365fin](includes/d365fin_md.md)] while they are working in [!INCLUDE[crm_md](includes/crm_md.md)]. For example, it can provide insights into customer statistics, allows users to couple and view records in [!INCLUDE[d365fin](includes/d365fin_md.md)] from [!INCLUDE[crm_md](includes/crm_md.md)], and allows people to see whether products are available in [!INCLUDE[d365fin](includes/d365fin_md.md)].

By default, the **Set Up Dynamics 365 Sales Connection** assisted setup guide will import the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution. To do that, the setup guide uses an administrator user account. This account must also be a valid user in [!INCLUDE[crm_md](includes/crm_md.md)] with the following security roles:

* System Administrator  
* Solution Customizer  

For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md), [Create users in Microsoft Dynamics 365 (online) and assign security roles](/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles), and [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

This account is used only one time during the setup. After the solution is imported into [!INCLUDE[d365fin](includes/d365fin_md.md)] the account is no longer needed. Integration will continue to use the user account that was created specifically for the integration.

In addition to customizing [!INCLUDE[crm_md](includes/crm_md.md)], the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution also creates the following roles in [!INCLUDE[crm_md](includes/crm_md.md)] for the integration:

* **Integration Administrator** - Allows users to manage the connection between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)]. Typically assigned only to the user account for synchronization.  
* **Integration User** - Allows users to access synchronized data. Typically assigned to the user account for synchronization and any other user who needs to view or access the synchronized data.
* **Product Availability User** - Allows users to query product availability in [!INCLUDE[d365fin](includes/d365fin_md.md)] from [!INCLUDE[crm_md](includes/crm_md.md)].

For details about each role, such as the permissions and access levels, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

At the end of the setup guide, [!INCLUDE[d365fin](includes/d365fin_md.md)] prompts you to couple sales people to users in [!INCLUDE[crm_md](includes/crm_md.md)]. Records in [!INCLUDE[crm_md](includes/crm_md.md)] usually have an owner (user) assigned to them, and if coupling between the user in [!INCLUDE[crm_md](includes/crm_md.md)] and the sales person in [!INCLUDE[d365fin](includes/d365fin_md.md)] does not exist, synchronization will fail. You can also do this later by using the **Couple Salespersons** action on the **Microsoft Dynamics 365 Connection Setup** page.

## Integration Settings that are Specific to a [!INCLUDE[crm_md](includes/crm_md.md)] Integration
Integration with [!INCLUDE[d365fin](includes/d365fin_md.md)] happens through [!INCLUDE[d365fin](includes/cds_long_md.md)], and there are a lot of standard settings and entities that are provided by the integration. In addition to the standard settings, there are some that are specific to [!INCLUDE[crm_md](includes/crm_md.md)]. The following sections list those.

### Connection Settings in the Setup Guide
The **Sales Connection Setup** assisted setup guide can help you set up the connection and specify advanced features, such as coupling between records.

1. Choose **Setup and Extensions**, and then choose **Assisted Setup**.
2. Choose **Sales Connection Setup** to start the assisted setup guide.
3. Fill in the fields as necessary.
4. Optionally, there are advanced settings that can enhance security and enable [!INCLUDE[d365fin](includes/cds_long_md.md)] additional capabilities, such as sales order processing and viewing inventory levels. The following table describes the advanced settings.  

|Field|Description|
|-----|-----|
|**Import Integration Solution**|Enable this to install and configure the integration solution in [!INCLUDE[d365fin](includes/cds_long_md.md)]. For more information, see [About the Business Central Integration Solution](admin-prepare-dynamics-365-for-sales-for-integration.md#about-the-business-central-integration-solution).|
|**Publish Item Availability Web Service**|Enable people who are using [!INCLUDE[d365fin](includes/cds_long_md.md)] to view the availability of items (products) in inventory in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This requires that the [!INCLUDE[d365fin](includes/d365fin_md.md)] user account with a web services access key. Assigning the key is a two-step process. On the user account in [!INCLUDE[d365fin](includes/d365fin_md.md)] you must choose the **Change Web Service Key** action. In the Set Up Dynamics 365 Sales Connection assisted setup guide, you must specify the Dynamics 365 Business Central OData web service URL, and provide [!INCLUDE[d365fin](includes/d365fin_md.md)] user credentials for accessing the service. For more information, see [OData Web Services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services).|
|**Dynamics 365 Business Central OData Web Service URL**|If you enable the Item Availability Web Service, the URL for the OData Web service is provided for you.|
|**Dynamics 365 Business Central OData Web Service Username**|The name of the [!INCLUDE[d365fin](includes/d365fin_md.md)] user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to retrieve information about item availability in [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web Service.|
|**Dynamics 365 Business Central OData Web Service Accesskey**|The access key for the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web Service. The key is assigned to the user chosen in the **Dynamics 365 Business Central OData Web Service Username** field. To get the key, choose the **Look up value** button next to the user name, choose the user, choose **Manage**, and then **Edit**. On the user card, choose **Actions**, **Authentication**, and then choose **Change Web Service Key**.|
|**Enable Sales Order Integration**|When people create sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] and fullfill orders in [!INCLUDE[d365fin](includes/d365fin_md.md)], this integrates the process in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration). This requires that you provide credentials for an administrator user account in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Handling Sales Order Data](marketing-integrate-dynamicscrm.md#handling-sales-order-data).|
|**Enable CDS Connection**|Enable the connection to [!INCLUDE[d365fin](includes/cds_long_md.md)].|
<!-- Is this relevant? |**Dynamics 365 SDK Version**|This is relevant only if you are integrating with an on-premises version of [!INCLUDE[crm_md](includes/crm_md.md)]. This is the Dynamics 365 software development kit (also referred to as Xrm) you use to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to [!INCLUDE[crm_md](includes/crm_md.md)]. The version must be compatible with the SDK version that is used by [!INCLUDE[crm_md](includes/crm_md.md)], and equal to or newer than the version used by [!INCLUDE[crm_md](includes/crm_md.md)].|-->

### Connection Settings on the Sales Connection Setup Page 
<!--verify the name of the page in the heading-->
Enter the following information for the connection from [!INCLUDE[crm_md](includes/crm_md.md)] to [!INCLUDE[d365fin](includes/d365fin_md.md)].

|Field|Description|
|-----|-----|
|**Dynamics 365 Business Central Web Client URL**|The URL of your [!INCLUDE[d365fin](includes/d365fin_md.md)] instance. This enables users in [!INCLUDE[crm_md](includes/crm_md.md)] to open corresponding records in [!INCLUDE[d365fin](includes/d365fin_md.md)] from records in [!INCLUDE[crm_md](includes/crm_md.md)], such as an account or product. The [!INCLUDE[d365fin](includes/d365fin_md.md)] records open in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Set this field to the URL of the [!INCLUDE[d365fin](includes/d365fin_md.md)] instance to use.<br /><br /> To reset the field to the default URL for the [!INCLUDE[d365fin](includes/d365fin_md.md)], choose **Reset Web Client URL** action.<br /><br /> This field is relevant only if the [!INCLUDE[d365fin](includes/d365fin_md.md)] Integration Solution is installed in [!INCLUDE[crm_md](includes/crm_md.md)].|
|**Item Availability Web Service Enabled**|Enable people who are using [!INCLUDE[crm_md](includes/crm_md.md)] to view the availability of items (products) in inventory in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you enable this, you must also provide a user name and an access key for the [!INCLUDE[crm_md](includes/crm_md.md)] to use to query OData Web Service for availablity of items (products). For more information, see [OData Web Services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services.md).|
|**Dynamics 365 Business Central OData Web Service URL**|If you enable the Item Availability Web Service, the URL for the OData Web service is provided for you.|
|**Dynamics 365 Business Central OData Web Service Username**|The name of the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web service.|
|**Dynamics 365 Business Central OData Web Service Accesskey**|The access key for the user account that the [!INCLUDE[crm_md](includes/crm_md.md)] uses to get information about item availability from [!INCLUDE[d365fin](includes/d365fin_md.md)] through OData Web service. The key is assigned to the user chosen in the **Dynamics 365 Business Central OData Web Service Username** field. To get the key, choose the **Look up value** button next to the user name, choose the user, choose **Manage**, and then **Edit**. On the user card, choose **Actions**, **Authentication**, and then choose **Change Web Service Key**.|

In addition to the settings above, enter the following settings for [!INCLUDE[crm_md](includes/crm_md.md)].

|Field|Description|
|-----|-----|
|**Sales Order Integration is Enabled**|Enable users to submit sales orders and activated quotes in [!INCLUDE[d365fin](includes/cds_long_md.md)] and then view and process them in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This integrates the process in [!INCLUDE[d365fin](includes/cds_long_md.md)]. For more information, see [Enable sales order processing integration](/dynamics365/customer-engagement/sales-enterprise/developer/enable-sales-order-processing-integration).|
|**Automatically Create Sales Orders**|Create a sales order in [!INCLUDE[d365fin](includes/d365fin_md.md)] when a user creates and submits one in [!INCLUDE[d365fin](includes/cds_long_md.md)].|
|**Automatically Process Sales Quotes**|Process a sales quote in [!INCLUDE[d365fin](includes/d365fin_md.md)] when a user creates and activates one in [!INCLUDE[d365fin](includes/cds_long_md.md)].|

### User Account Settings
Integrate with Business Central through Common Data Service requires an administrator user account and an account that is used only for the connection between the apps. This account is called the "integration user." When you install the Integration Solution, permissions for the integration user account are configured in [!INCLUDE[crm_md](includes/crm_md.md)]. If those permissions are changed you might need to reset them. You can do that by reinstalling the Integration Solution or by manually resetting them. The following tables list the minimum permissions for the user accounts in [!INCLUDE[crm_md](includes/crm_md.md)].  

### Standard Sales Entity Mapping for Synchronization
<!--Need to rewrite this for CDS and move this content to Sales-->
Entities in [!INCLUDE[d365fin](includes/cds_long_md.md)], such as accounts, are integrated with equivalent types of entities in [!INCLUDE[d365fin](includes/d365fin_md.md)],such as customers. To work with [!INCLUDE[d365fin](includes/cds_long_md.md)] data you set up links, called couplings, between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)].

The following table lists the standard mapping between entities in [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[d365fin](includes/cds_long_md.md)] that [!INCLUDE[d365fin](includes/d365fin_md.md)] provides.

|[!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[d365fin](includes/cds_long_md.md)]|Synchronization Direction|Default Filter|
|-------------------------------------------|-----|-------------------------|--------------|
|Salesperson/Purchaser|User|[!INCLUDE[d365fin](includes/cds_long_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales contact filter: **Status** is **No**, **User Licensed** is **Yes**, Integration user mode is **No**|
|Customer|Account|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|Sales account filter: **Relationship Type** is **Customer** and **Status** is **Active**.|
|Contact|Contact|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)] -> [!INCLUDE[d365fin](includes/d365fin_md.md)]|[!INCLUDE[d365fin](includes/d365fin_md.md)] contact filter: **Type** is **Person** and the contact is assigned to a company. Sales contact filter: The contact is assigned to a company and the parent customer type is **Account**|
|Currency|Transaction Currency|[!INCLUDE[d365fin](includes/d365fin_md.md)] -> [!INCLUDE[crm_md](includes/crm_md.md)]| |
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
<!--Need to rewrite this for CDS and move this content to Sales-->
The following table describes rules that control the synchronization between the apps.

> [!NOTE]  
> Changes to data in  that were made by the integration user account are not synchronized. Therefore, we recommended that you do not change data while using that account. For more information, see [Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md).

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

### Synchronization Jobs for a Sales Integration
The jobs are run in the following order to avoid coupling dependencies between entities.  

1.  CURRENCY - Dynamics 365 Sales synchronization job  
2.  SALEPEOPLE - Dynamics 365 Sales synchronization job  
3.  UNITOFMEASURE - Dynamics 365 Sales synchronization job  
4.  CUSTOMER - Dynamics 365 Sales synchronization job  
5.  CONTACTS - Dynamics 365 Sales synchronization job  
6.  RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job  
7.  ITEM-PRODUCT - Dynamics 365 Sales synchronization job  

### Default Synchronization Job Queue Entries  
<!--Probably need to update these for CDS, and perhaps move this to the Sales content-->
The following table describes the default synchronization jobs.  

|Job Queue Entry|Description|Direction|Integration Table Mapping|Default Synchronization Frequency (mins)|Default inactivity sleep time (mins)|  
|---------------------|---------------------------------------|---------------|-------------------------------|-----|-----|  
|CONTACT - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service contacts with [!INCLUDE[d365fin](includes/d365fin_md.md)] contacts.|Bidirectional|CONTACT|30|720 <br>(12 hours)| 
|CURRENCY - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service transaction currencies with [!INCLUDE[d365fin](includes/d365fin_md.md)] currencies.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to Common Data Service|CURRENCY|30|720 <br> (12 hrs)| 
|CUSTOMER - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service accounts with [!INCLUDE[d365fin](includes/d365fin_md.md)] customers.|Bidirectional|CUSTOMER|30|720<br> (12 hrs)|
|CUSTPRCGRP-PRICE - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service sales price lists with [!INCLUDE[d365fin](includes/d365fin_md.md)] customer price groups.| |CUSTOMER PRICE GROUPS-SALES PRICE LISTS|30|1440<br> (24 hrs)|
|ITEM - PRODUCT - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service products with [!INCLUDE[d365fin](includes/d365fin_md.md)] items.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to Common Data Service|ITEM-PRODUCT|30|1440<br> (24 hrs)|
|POSTEDSALESINV-INV - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service invoices with [!INCLUDE[d365fin](includes/d365fin_md.md)] posted sales invoices.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to Common Data Service|INVOICES-POSTED SALES INVOICES|30|1440<br> (24 hrs)|
|RESOURCE-PRODUCT - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service products with [!INCLUDE[d365fin](includes/d365fin_md.md)] resources.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to Common Data Service|RESOURCE-PRODUCT|30|720<br> (12 hrs)|  
|SALESPEOPLE - Dynamics 365 Sales synchronization job|Synchronizes [!INCLUDE[d365fin](includes/d365fin_md.md)] salespeople with Common Data Service users.|From Common Data Service to [!INCLUDE[d365fin](includes/d365fin_md.md)]|SALESPEOPLE|30|1440<br> (24 hrs)|
|SALESPRC-PRODUCTPRICE - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service product prices with [!INCLUDE[d365fin](includes/d365fin_md.md)] sales prices.||PRODUCT PRICE-SALES PRICE|30|1440<br> (24 hrs)|
|UNITOFMEASURE - Dynamics 365 Sales synchronization job|Synchronizes Common Data Service unit groups with [!INCLUDE[d365fin](includes/d365fin_md.md)] units of measure.|From [!INCLUDE[d365fin](includes/d365fin_md.md)] to Common Data Service|UNIT OF MEASURE|30|720<br> (12 hrs)|  
|Customer Statistics - Dynamics 365 Sales synchronization|Updates Common Data Service accounts with the latest [!INCLUDE[d365fin](includes/d365fin_md.md)] customer data. In Common Data Service, this information appears in **Business Central Account Statistics** quick view form of accounts that are coupled to [!INCLUDE[d365fin](includes/d365fin_md.md)] customers.<br /><br /> This data can also be updated manually from each customer record. For more information, see [Couple and Synchronize Records Manually](admin-how-to-couple-and-synchronize-records-manually.md). </BR></BR>**Note:**  This job queue entry is relevant only if the [!INCLUDE[d365fin](includes/d365fin_md.md)] integration solution is installed in Common Data Service. For more information, see [About the Business Central Integration Solution](admin-prepare-dynamics-365-for-sales-for-integration.md#about-the-business-central-integration-solution).|Not applicable|Not applicable|30|Not applicable| 

## See Also  
[Setting Up User Accounts for Integrating with Common Data Service](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Common Data Service](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronizing Business Central and Common Data Service](admin-synchronizing-business-central-and-sales.md)  
[Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration)
