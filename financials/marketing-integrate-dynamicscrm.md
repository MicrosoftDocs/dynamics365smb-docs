---
title: Manage Customers Using Dynamics 365 for Sales| Microsoft Docs
description: You can use Dynamics 365 for Sales from inside Dynamics 365 for Financials to map data and have seamless integration and synchronization in the lead-to-cash process.
documentationcenter: ''
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: integration, synchronize, map
ms.date: 06/06/2017
ms.author: edupont
---
# Managing Your Customer Relationships using Dynamics 365 for Sales from inside Dynamics 365 for Financials
If you use Dynamics 365 for Sales for customer engagement, you can use [!INCLUDE[d365fin](includes/d365fin_md.md)] for order processing and finances and have seamless integration in the lead-to-cash process.

When your application is set up to integrate with Dynamics 365 for Sales, you have access to Sales data from [!INCLUDE[d365fin](includes/d365fin_md.md)] and the other way around in some cases. This integration enables you to work with and synchronize data types that are common to both services, such as customers, contacts, and sales information, and keep the data up to date in both locations.  

**Note**: In the current version of [!INCLUDE[d365fin](includes/d365fin_md.md)], Dynamics 365 for Sales is referred to as Dynamics CRM. For simplicity, the remainder of this article will use the terminology that is used in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

For example, the sales person in Dynamics CRM can use the price lists from [!INCLUDE[d365fin](includes/d365fin_md.md)] when they create a sales order. When they add the item to the sales order line in Dynamics CRM, they are also able to see the inventory level (availability) of the item from [!INCLUDE[d365fin](includes/d365fin_md.md)]. This data is published as part of the assisted setup guide, **Dynamics CRM Connection Setup**.  

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).  

## Setting up the connection
From Home, you can access the **Dynamics CRM Connection Setup** assisted setup guide that helps you set up the connection. Once that is done, you will have a seamless coupling of Dynamics CRM records with [!INCLUDE[d365fin](includes/d365fin_md.md)] records.  

**Note**: The following explains the assisted setup, but you can perform the same tasks manually in the **CRM Connection Setup** window.

In the assisted setup guide, you can choose which data to synchronize between the two services. You can also specify that you want to import your existing Dynamics CRM solution. In that case, you must specify an administrative user account.

### Setting up the user account for importing the solution
To import an existing Dynamics CRM solution, the setup guide uses an administrative account. This account must be a valid user in Dynamics CRM with the following security roles:

* System Administrator  
* Solution Customizer  

For more information, see [Create users and assign Microsoft Dynamics 365 (online) security roles](https://technet.microsoft.com/library/jj191623.aspx) on techNet and [How to: Manage Users and Permissions](ui-how-users-permissions.md).  

This account is only used during the setup. Once the solution is imported into [!INCLUDE[d365fin](includes/d365fin_md.md)], the account is no longer needed.

### Setting up the user account for synchronization
The integration relies on a shared user account. So in your Office 365 subscription, you must create a dedicated user that will be used for synchronization between the two services. This account must already be a valid user in Dynamics CRM, but you do not have to assign security roles to the account because the setup guide will do that for you. You must specify this user account one or more times in the setup guide, depending how much synchronization you want to enable. For more information, see [Create users and assign Microsoft Dynamics 365 (online) security roles](https://technet.microsoft.com/library/jj191623.aspx) on techNet.

If you choose to enable *item availability*, the integration user account must have a web services access key. This is a two-step thing in the [!INCLUDE[d365fin](includes/d365fin_md.md)] page for that user account, you must choose the **Change Web Service Key** button; and in the CRM connection setup guide, you must specify that user as the OData web service user.

If you choose to enable *sales order integration*, you must specify a user that can handle this synchronization - the integration user or another user account.

### Coupling records
In the assisted setup guide, you can choose to synchronize between the two services. But later, you can also set up synchronization of specific types of data. This is referred to as *coupling*, and this section provides recommendations for what you must take into consideration.

For example, if you want to see Dynamics CRM accounts as customers in [!INCLUDE[d365fin](includes/d365fin_md.md)], you must couple the two types of records. It is not very complicated - you open the **Customer List** window in [!INCLUDE[d365fin](includes/d365fin_md.md)], and there is an action in the ribbon to couple this data with Dynamics CRM. Then you specify which [!INCLUDE[d365fin](includes/d365fin_md.md)] customers match which accounts in Dynamics CRM.

In certain areas, the functionality relies on you couple certain sets of data before other sets of data as shown in the following list:

* Customers and accounts  
  * Couple salespeople with Dynamics CRM users first  
* Items and resources  
  * Couple units of measure with Dynamics CRM unit groups first  
* Items and resource prices  
  * Couple customer price groups with Dynamics CRM prices first  

**Note**: If you are using prices in foreign currencies, make sure that you couple currencies to Dynamics CRM transaction currencies.

Dynamics CRM sales orders depends on additional information like customers, units of measure, currencies, customer price groups, items and/or resources. In order for Dynamics CRM sales orders to work seamlessly, you must couple customers, units of measure, currencies, customer price groups, items and/or resources first.

### Synchronizing records fully
At the end of the assisted setup guide, you can choose the **Run Full Synchronization** action to start synchronizing all [!INCLUDE[d365fin](includes/d365fin_md.md)] records with all related records in the connected Dynamics CRM solution. In the **CRM Full Synch. Review** window, you choose the **Start** action. The synchronization then begins to execute jobs according to dependencies. For example, currency records are synchronized before customer records. The full synchronization may take a long time and will therefore run in the background so that you can continue to work in [!INCLUDE[d365fin](includes/d365fin_md.md)].

To check the progress of individual jobs in a full synchronization, drill down on the **Job Queue Entry Status**, **To Int. Table Job Status**, or **From Int. Table Job Status** field in the **CRM Full Synch. Review** window.

From the **CRM Connection Setup** window, you can get details about full synchronization at any time. From here, you can also open the **Integration Table Mappings** window to see details about the tables in Financials and in the Dynamics CRM solution that must be synchronized.

## See Also
[Relationship Management](marketing-relationship-management.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md)  
[How to: Manage Users and Permissions](ui-how-users-permissions.md)    
[Onboard your organization and users to Dynamics 365 (online)](https://www.microsoft.com/en-US/Dynamics/crm-customer-center/onboard-your-organization-and-users-to-dynamics-365-online.aspx)  
