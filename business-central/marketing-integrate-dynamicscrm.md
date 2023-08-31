---
title: Manage Customers Using Dynamics 365 Sales(contains video) | Microsoft Docs
description: You can use Dynamics 365 Sales from inside Business Central with seamless integration and synchronization in the lead-to-cash process.
documentationcenter: ''
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: integration, synchronize, map, Sales
ms.search.forms: 9980, 5341, 5349, 5330, 1817, 5342, 5337, 5336, 5331, 5343, 5334, 5346, 5348, 5329, 5380, 5353, 5381, 5351, 5333, 5360, 5373, 5371, 5340, 5345, 5362, 1313, 5361, 1876, 5339, 5338, 5335, 5332, 6250
ms.date: 09/16/2022
ms.author: bholtorf
---
# Use Dynamics 365 Sales from Business Central
If you use Dynamics 365 Sales for customer engagement, you can enjoy seamless integration in the lead-to-cash process by using [!INCLUDE[prod_short](includes/prod_short.md)] for backend activities such as processing orders, managing inventory, and doing your finances.

Before you can use the integration capabilities, your system administrator must set up the connection and define users in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).

> [!NOTE]
> These steps describe the process of integrating online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)]. For information about on-premises configuration, see [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

Integrating the applications lets you access data in Sales from [!INCLUDE[prod_short](includes/prod_short.md)], and in some cases the other way around. You can work with and synchronize data that both services have in common, such as customers, contacts, and sales information, and keep the data up to date in both applications.  

For example, a sales person in [!INCLUDE[crm_md](includes/crm_md.md)] can use the price lists from [!INCLUDE[prod_short](includes/prod_short.md)] when they create a sales order. When they add the item to the sales order line in [!INCLUDE[crm_md](includes/crm_md.md)], they can see the inventory level (availability) of the item from [!INCLUDE[prod_short](includes/prod_short.md)].

Conversely, order processors in [!INCLUDE[prod_short](includes/prod_short.md)] can handle sales orders that are automatically or manually transferred from [!INCLUDE[crm_md](includes/crm_md.md)]. For example, they can create and post sales order lines for items or resources that were entered in [!INCLUDE[crm_md](includes/crm_md.md)] as write-in products. For more information, see [Handling Sales Order Data](marketing-integrate-dynamicscrm.md#handling-sales-order-data).

> [!IMPORTANT]  
> [!INCLUDE[prod_short](includes/prod_short.md)] integrates only with [!INCLUDE[crm_md](includes/crm_md.md)]. Other Dynamics 365 applications that change the standard workflow or data model in [!INCLUDE[crm_md](includes/crm_md.md)], for example Project Service Automation, can break the integration between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].

## Coupling Records
The assisted setup guide lets you choose the data to synchronize. Later, you can also set up synchronization for specific records. This is referred to as *coupling*. For example, you can couple a specific account in [!INCLUDE[crm_md](includes/crm_md.md)] with a specific customer in [!INCLUDE[prod_short](includes/prod_short.md)]. This section describes what to take into consideration when you couple records.

For example, if you want to see accounts in [!INCLUDE[crm_md](includes/crm_md.md)] as customers in [!INCLUDE[prod_short](includes/prod_short.md)], you must couple the two types of records. To do that, on the **Customers** list page in [!INCLUDE[prod_short](includes/prod_short.md)], use the **Set Up Coupling** action. Then specify which [!INCLUDE[prod_short](includes/prod_short.md)] customers to match to which accounts in [!INCLUDE[crm_md](includes/crm_md.md)].

You can also create (and couple) an account in [!INCLUDE[crm_md](includes/crm_md.md)] based on, for example, a customer record in [!INCLUDE[prod_short](includes/prod_short.md)] using **Create Account in Dynamics 365 Sales**, or vice versa, using **Create Customer in [!INCLUDE[prod_short](includes/prod_short.md)]**.

When you set up coupling between two records, you can also manually request current record, for example a customer, to be overwritten immediately by account data from Sales (or from [!INCLUDE[prod_short](includes/prod_short.md)]) using **Synchronize Now** action. **Synchronize Now** action which will ask whether to overwrite Sales or [!INCLUDE[prod_short](includes/prod_short.md)] record data.

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
At the end of the assisted setup guide you can choose the **Run Full Synchronization** action to start synchronizing all [!INCLUDE[prod_short](includes/prod_short.md)] records with all related records in [!INCLUDE[crm_md](includes/crm_md.md)]. On the **Dynamics 365 Sales Full Synch Review** page, you choose the **Start** action. Full synchronization can take some time to complete, but you can continue to work in [!INCLUDE[prod_short](includes/prod_short.md)] while it runs in the background.

To check the progress of individual jobs in a full synchronization, on the **Dynamics 365 Sales Full Synch Review** page choose an record to view details. To update the status during synchronization, refresh the page.

From the **Microsoft Dynamics 365 Connection Setup** page, you can get details about full synchronization at any time. From here, you can also open the **Integration Table Mappings** page to see details about the tables in [!INCLUDE[prod_short](includes/prod_short.md)] and Sales that must be synchronized.

## Handling Sales Order Data
Sales orders that people submit in [!INCLUDE[crm_md](includes/crm_md.md)] will be automatically transferred to [!INCLUDE[prod_short](includes/prod_short.md)] if you select the **Automatically Create Sales Orders** check box on the **Microsoft Dynamics 365 Connection Setup** page.
Alternatively, you can manually convert submitted sales orders from [!INCLUDE[crm_md](includes/crm_md.md)] by using the **Create in [!INCLUDE[prod_short](includes/prod_short.md)]** action available on **Sales Orders - Dynamics 365 for Sales** page.
On such sales orders, the **Name** field on the original order is transferred and mapped to the **External Document Number** field on the sales order in [!INCLUDE[prod_short](includes/prod_short.md)].

This can also work if the original sales order contains write-in products, meaning items or resources that are not registered in either app. In that case, you must fill in the **Write-in Product Type** and **Write-in Product No.** fields on the **Sales & Receivables Setup** page so that sales of non-registered products are mapped to a specified item or resource number.

> [!NOTE]
> You cannot map a write-in to an item or resource in [!INCLUDE[prod_short](includes/prod_short.md)] that is coupled with a product in [!INCLUDE[crm_md](includes/crm_md.md)]. To allow for write-ins, we recommend that you create an item or resource specifically for that purpose, and do not couple it with a product in [!INCLUDE[crm_md](includes/crm_md.md)]. 

If the description of the item on the original sales order is long, an additional sales order line of the type **Comment** is created to hold the full text on the sales order in [!INCLUDE[prod_short](includes/prod_short.md)].

Updates to fields on sales order headers, such as the Last Shipment Date or Requested Delivery Date fields, that are mapped in the **SALESORDER-ORDER** integration table mapping are periodically synchronized to [!INCLUDE[crm_md](includes/crm_md.md)]. Processes such as releasing, shipping, and invoicing a sales order are posted to the sales order timeline in [!INCLUDE[crm_md](includes/crm_md.md)]. For more information, see [Introduction to activity feeds](/dynamics365/sales-enterprise/manage-activities). To enable posting and activities for orders in [!INCLUDE[crm_md](includes/crm_md.md)], see [Set up the Notes control to access information about posts for a custom entity](/dynamics365/customerengagement/on-premises/customize/notes-control-legacy) in the Customer Engagement documentation. The article refers to Customer Engagement on-premises, but the steps are the same for the online version. <!--The /dynamics365/sales-enterprise/developer/introduction-activity-feeds link was broken. Should this actually point to /dynamics365/sales-enterprise/manage-activities-->

> [!NOTE]  
> Periodical synchronization based on the **SALESORDER-ORDER** integration table mapping will work only when sales order integration is enabled. For more information, see [Connection settings on the Sales Connection Setup Page](admin-prepare-dynamics-365-for-sales-for-integration.md). Only sales orders created from submitted sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] are synchronized. For more information, see [Enable Sales Order Processing Integration](/dynamics365/sales-enterprise/developer/enable-sales-order-processing-integration).

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098170]

## Handling Sales Quotes Data
Sales quotes that are activated in [!INCLUDE[crm_md](includes/crm_md.md)] will be transferred to [!INCLUDE[prod_short](includes/prod_short.md)] if you select the **Automatically Process Quotes** check box on the **Microsoft Dynamics 365 Connection Setup** page.
Alternatively, you can manually convert activated sales quotes from [!INCLUDE[crm_md](includes/crm_md.md)] by using the **Process in [!INCLUDE[prod_short](includes/prod_short.md)]** action on the **Sales Quotes - Dynamics 365 Sales** page.
On such sales quotes, the **Name** field on the original quote is transferred and mapped to the **External Document Number** field on the sales order in [!INCLUDE[prod_short](includes/prod_short.md)]. Also **Effective To** field on quote is transferred and mapped to the  **Quote Valid Until** field on sales quote in [!INCLUDE[prod_short](includes/prod_short.md)].  

Sales quotes go through many revisions while they are being finalized. Both manual and automatic processing of sales quotes in [!INCLUDE[prod_short](includes/prod_short.md)] ensures that previous versions of sales quotes are archived before processing new revisions of sales quotes from [!INCLUDE[crm_md](includes/crm_md.md)].

When you choose **Process** in [!INCLUDE[prod_short](includes/prod_short.md)] for a quote that is in state **Won**, a sales order is created in [!INCLUDE[prod_short](includes/prod_short.md)] only if a corresponding sales order is submitted in [!INCLUDE[crm_md](includes/crm_md.md)]. Otherwise, the quote is only released in [!INCLUDE[prod_short](includes/prod_short.md)]. If a corresponding sales order is submitted in [!INCLUDE[crm_md](includes/crm_md.md)] later, and a sales order is created from it, the **Quote No.** is updated on the sales order and the quote is archived.

## Handling Posted Sales Invoices, Customer Payments, and Statistics
After fulfilling a sales order, invoices will be created for it. When you invoice a sales order, you can transfer the posted sales invoice to [!INCLUDE[crm_md](includes/crm_md.md)] if you select the **Create Invoice in [!INCLUDE[crm_md](includes/crm_md.md)]** check box on the **Posted Sales Invoice** page. Posted invoices are transferred to [!INCLUDE[crm_md](includes/crm_md.md)] with the status, **Billed**.

When the customer payment is received for the sales invoice in [!INCLUDE[prod_short](includes/prod_short.md)], the sales invoice status will be changed to **Paid** with the **Status Reason** field set to **Partial**, if partially paid, or **Complete** if completely paid, when you choose the **Update Account Statistics** action on the customer page in [!INCLUDE[prod_short](includes/prod_short.md)]. The **Update Account Statistics** function will also refresh values, such as the **Balance** and **Total Sales** fields in the **[!INCLUDE[prod_short](includes/prod_short.md)] Account Statistics** FactBox in [!INCLUDE[crm_md](includes/crm_md.md)]. Alternatively, you can have the scheduled jobs, Customer Statistics and POSTEDSALESINV-INV automatically run both of these processes in the background. 

## Handling Sales Prices
> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. If you're a new customer using that version, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

The steps to complete this process differ, depending on whether your administrator has enabled the new pricing experience. 

> [!NOTE]
> If the standard price synchronization does not work for you, we recommend using integration customization capabilities. For more information, see [Customizing an Integration with Microsoft Dataverse](/dynamics365/business-central/dev-itpro/administration/administration-custom-cds-integration).

#### [Current Experience](#tab/current-experience/)
In the current pricing experience, [!INCLUDE[prod_short](includes/prod_short.md)] synchronizes sales prices that: 

* Apply to all customers. Default sales price lists are created based on the price in the **Unit Price** field on the **Item Card** page for the items.
* Apply to a specific customer price group. For example, sales prices for your retail or wholesale customers. To synchronize prices based on a customer price group, do the following:

    1. Couple the items for which prices are set by the customer price group.
    2. On the **Customer Price Groups** page, couple the customer price group by choosing **Related**, then **Dynamics 365 Sales**, **Coupling**, and then **Set up coupling**. The coupling will create an active price list in [!INCLUDE[prod_short](includes/prod_short.md)] with the same name as the customer price group in [!INCLUDE[crm_md](includes/crm_md.md)], and automatically synchronize all items for which the customer price group defines the price.

:::image type="content" source="media/customer-price-group.png" alt-text="Customer Price Group page.":::

#### [New Experience](#tab/new-experience/)  

The new pricing experience synchronizes price lists that meet the following criteria:

* **Allow Updating Defaults** is turned off.
* The price type is Sale.
* The amount type is Price.
* The product type on the lines must be Item or Resource. 
* A minimum quantity is not specified.

[!INCLUDE[prod_short](includes/prod_short.md)] synchronizes sales prices that apply to all customers. Default sales price lists are created based on the price in the **Unit Price** field on the **Item Card** page for the items.

To synchronize price lists, on the **Sales Price List** page, choose **Related**, **Dynamics 365 Sales**, **Coupling**, and then **Set up coupling**. 

:::image type="content" source="media/sales-price-list.png" alt-text="Sales Price List page.":::

---


## See Also
[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Relationship Management](marketing-relationship-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)    
[Overview of Sales and Sales Hub](/dynamics365/customer-engagement/sales-enterprise/overview)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]