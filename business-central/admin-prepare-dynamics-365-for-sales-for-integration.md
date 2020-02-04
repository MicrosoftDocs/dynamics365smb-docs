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

## Set Up a Connection 
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

## Setting Up User Accounts
Integrate with Business Central through Common Data Service requires an administrator user account and an account that is used only for the connection between the apps. This account is called the "integration user." When you install the Integration Solution, permissions for the integration user account are configured in [!INCLUDE[crm_md](includes/crm_md.md)]. If those permissions are changed you might need to reset them. You can do that by reinstalling the Integration Solution or by manually resetting them. The following tables list the minimum permissions for the user accounts in [!INCLUDE[crm_md](includes/crm_md.md)].  

## See Also  
[Setting Up User Accounts for Integrating with Common Data Service](admin-setting-up-integration-with-dynamics-sales.md)  
[Set Up a Connection to Common Data Service](admin-how-to-set-up-a-dynamics-crm-connection.md)  
[Synchronizing Business Central and Common Data Service](admin-synchronizing-business-central-and-sales.md)  
[Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration)
