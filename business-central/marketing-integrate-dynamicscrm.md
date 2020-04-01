---
title: Manage Customers Using Dynamics 365 Sales| Microsoft Docs
description: You can use Dynamics 365 Sales from inside Business Central to map data and have seamless integration and synchronization in the lead-to-cash process.
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: integration, synchronize, map, Sales
ms.date: 04/01/2020
ms.author: bholtorf
---
# Using Dynamics 365 Sales from Business Central
If you use Dynamics 365 Sales for customer engagement, you can enjoy seamless integration in the lead-to-cash process by using [!INCLUDE[d365fin](includes/d365fin_md.md)] for backend activities such as processing orders, managing inventory, and doing your finances.

Before you can use the integration capabilities, your system administrator must set up the connection and define users in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).

> [!NOTE]
> These steps describe the process of integrating online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[d365fin](includes/d365fin_md.md)]. For information about on-premises configuration, see [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

Integrating the applications lets you access data in Sales from [!INCLUDE[d365fin](includes/d365fin_md.md)], and in some cases the other way around. You can work with and synchronize data that both services have in common, such as customers, contacts, and sales information, and keep the data up to date in both applications.  

For example, a sales person in [!INCLUDE[crm_md](includes/crm_md.md)] can use the price lists from [!INCLUDE[d365fin](includes/d365fin_md.md)] when they create a sales order. When they add the item to the sales order line in [!INCLUDE[crm_md](includes/crm_md.md)], they can see the inventory level (availability) of the item from [!INCLUDE[d365fin](includes/d365fin_md.md)].

Conversely, order processors in [!INCLUDE[d365fin](includes/d365fin_md.md)] can handle sales orders that are automatically or manually transferred from [!INCLUDE[crm_md](includes/crm_md.md)]. For example, they can create and post sales order lines for items or resources that were entered in [!INCLUDE[crm_md](includes/crm_md.md)] as write-in products. For more information, see [Handling Sales Order Data](marketing-integrate-dynamicscrm.md#handling-sales-order-data).

> [!IMPORTANT]  
> [!INCLUDE[d365fin](includes/d365fin_md.md)] integrates only with [!INCLUDE[crm_md](includes/crm_md.md)]. Other Dynamics 365 applications that change the standard workflow or data model in [!INCLUDE[crm_md](includes/crm_md.md)], for example Project Service Automation, can break the integration between [!INCLUDE[d365fin](includes/d365fin_md.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].

## Coupling Records
The assisted setup guide lets you choose the data to synchronize. Later, you can also set up synchronization for specific records. This is referred to as *coupling*. For example, you can couple a specific account in [!INCLUDE[crm_md](includes/crm_md.md)] with a specific customer in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This section describes what to take into consideration when you couple records.

For example, if you want to see accounts in [!INCLUDE[crm_md](includes/crm_md.md)] as customers in [!INCLUDE[d365fin](includes/d365fin_md.md)], you must couple the two types of records. To do that, on the **Customers** list page in [!INCLUDE[d365fin](includes/d365fin_md.md)], use the **Set Up Coupling** action. Then specify which [!INCLUDE[d365fin](includes/d365fin_md.md)] customers to match to which accounts in [!INCLUDE[crm_md](includes/crm_md.md)].

You can also create (and couple) an account in [!INCLUDE[crm_md](includes/crm_md.md)] based on, for example, a customer record in [!INCLUDE[d365fin](includes/d365fin_md.md)] using **Create Account in Dynamics 365 Sales**, or vice versa, using **Create Customer in [!INCLUDE[d365fin](includes/d365fin_md.md)]**.

When you set up coupling between two records, you can also manually request current record, for example a customer, to be overwritten immediately by account data from Sales (or from [!INCLUDE[d365fin](includes/d365fin_md.md)]) using **Synchronize Now** action. **Synchronize Now** action which will ask whether to overwrite Sales or [!INCLUDE[d365fin](includes/d365fin_md.md)] record data.

In some cases you must couple certain sets of data before other sets of data, as shown in the following table.

|Data|What to couple first|
|-----|----|
|Customers and accounts|Couple salespeople with [!INCLUDE[crm_md](includes/crm_md.md)] users|
|Items and resources|Couple units of measure with [!INCLUDE[crm_md](includes/crm_md.md)] unit groups|
|Items and resource prices|Couple customer price groups with [!INCLUDE[crm_md](includes/crm_md.md)] prices|

> [!NOTE]  
> If your prices or customers use foreign currencies, make sure that you couple currencies to Sales transaction currencies.

In [!INCLUDE[crm_md](includes/crm_md.md)], sales orders depend on information such as customers, units of measure, currencies, customer price groups, and items and/or resources. For the integration with sales orders to work you must couple customers, units of measure, currencies, customer price groups, and items and/or resources.

## Fully Synchronizing Records
At the end of the assisted setup guide you can choose the **Run Full Synchronization** action to start synchronizing all [!INCLUDE[d365fin](includes/d365fin_md.md)] records with all related records in [!INCLUDE[crm_md](includes/crm_md.md)]. On the **Dynamics 365 Sales Full Synch Review** page, you choose the **Start** action. Full synchronization can take some time to complete, but you can continue to work in [!INCLUDE[d365fin](includes/d365fin_md.md)] while it runs in the background.

To check the progress of individual jobs in a full synchronization, on the **Dynamics 365 Sales Full Synch Review** page choose an record to view details. To update the status during synchronization, refresh the page.

From the **Microsoft Dynamics 365 Connection Setup** page, you can get details about full synchronization at any time. From here, you can also open the **Integration Table Mappings** page to see details about the tables in [!INCLUDE[d365fin](includes/d365fin_md.md)] and Sales that must be synchronized.

## Handling Sales Order Data
Sales orders that people submit in [!INCLUDE[crm_md](includes/crm_md.md)] will be automatically transferred to [!INCLUDE[d365fin](includes/d365fin_md.md)] if you select the **Automatically Create Sales Orders** check box on the **Microsoft Dynamics 365 Connection Setup** page.
Alternatively, you can manually convert submitted sales orders from [!INCLUDE[crm_md](includes/crm_md.md)] by using the **Create in [!INCLUDE[d365fin](includes/d365fin_md.md)]** action available on **Sales Orders - Dynamics 365 for Sales** page.
On such sales orders, the **Name** field on the original order is transferred and mapped to the **External Document Number** field on the sales order in [!INCLUDE[d365fin](includes/d365fin_md.md)].

This can also work if the original sales order contains write-in products, meaning items or resources that are not registered in either app. In that case, you must fill in the **Write-in Product Type** and **Write-in Product No.** fields on the **Sales & Receivables Setup** page so that such non-registered product sales are mapped to a specified item/resource number for financial analysis.

If the description of the item on the original sales order is long, an additional sales order line of the type **Comment** is created to hold the full text on the sales order in [!INCLUDE[d365fin](includes/d365fin_md.md)].

Updates to fields on sales order headers, such as the Last Shipment Date or Requested Delivery Date fields, that are mapped in SALESORDER-ORDER **Integration table mapping** are periodically synchronized to [!INCLUDE[crm_md](includes/crm_md.md)]. Processes such as releasing a sales order and shipping or invoicing a sales order are posted to the sales order timeline in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Introduction to activity feeds](/dynamics365/sales-enterprise/developer/introduction-activity-feeds). <!--The link is broken. Should this actually point to https://docs.microsoft.com/en-us/dynamics365/sales-enterprise/manage-activities-->

> [!NOTE]  
> Periodical synchronization based on the SALESORDER-ORDER **Integration table mapping** will work only when sales order integration is enabled. For more information, see [Connection settings on the Sales Connection Setup Page](admin-prepare-dynamics-365-for-sales-for-integration.md). Only sales orders created from submitted sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] are synchronized. For more information, see [Enable Sales Order Processing Integration](/dynamics365/sales-enterprise/developer/enable-sales-order-processing-integration).

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098170]

## Handling Sales Quotes Data
Sales quotes that are activated in [!INCLUDE[crm_md](includes/crm_md.md)] will be transferred to [!INCLUDE[d365fin](includes/d365fin_md.md)] if you select the **Automatically Process Quotes** check box on the **Microsoft Dynamics 365 Connection Setup** page.
Alternatively, you can manually convert activated sales quotes from [!INCLUDE[crm_md](includes/crm_md.md)] by using the **Process in [!INCLUDE[d365fin](includes/d365fin_md.md)]** action on the **Sales Quotes - Dynamics 365 Sales** page.
On such sales quotes, the **Name** field on the original quote is transferred and mapped to the **External Document Number** field on the sales order in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Also **Effective To** field on quote is transferred and mapped to the  **Quote Valid Until** field on sales quote in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

Sales quotes go through many revisions while they are being finalized. Both manual and automatic processing of sales quotes in [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that previous versions of sales quotes are archived before processing new revisions of sales quotes from [!INCLUDE[crm_md](includes/crm_md.md)].

## Handling Posted Sales Invoices, Customer Payments, and Statistics
After fulfilling a sales order, invoices will be created for it. When you invoice a sales order, you can transfer the posted sales invoice to [!INCLUDE[crm_md](includes/crm_md.md)] if you select the **Create Invoice in [!INCLUDE[crm_md](includes/crm_md.md)]** check box on the **Posted Sales Invoice** page. Posted invoices are transferred to [!INCLUDE[crm_md](includes/crm_md.md)] with the status, **Billed**.

When the customer payment is received for the sales invoice in [!INCLUDE[d365fin](includes/d365fin_md.md)], the sales invoice status will be changed to **Paid** with the **Status Reason** field set to **Partial**, if partially paid, or **Complete** if completely paid, when you choose the **Update Account Statistics** action on the customer page in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The **Update Account Statistics** function will also refresh values, such as the **Balance** and **Total Sales** fields in the **[!INCLUDE[d365fin](includes/d365fin_md.md)] Account Statistics** FactBox in [!INCLUDE[crm_md](includes/crm_md.md)]. Alternatively, you can have the scheduled jobs, Customer Statistics and POSTEDSALESINV-INV automatically run both of these processes in the background.

## See Also
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Relationship Management](marketing-relationship-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)    
[Overview of Sales and Sales Hub](/dynamics365/customer-engagement/sales-enterprise/overview)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
