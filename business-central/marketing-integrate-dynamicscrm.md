---
title: Manage customers using Dynamics 365 Sales
description: Learn how to use Dynamics 365 Sales from inside Business Central with seamless integration and synchronization in the lead-to-cash process.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: integration, synchronize, map, Sales
ms.search.forms: 9980, 5341, 5349, 5330, 1817, 5342, 5337, 5336, 5331, 5343, 5334, 5346, 5348, 5329, 5380, 5353, 5381, 5351, 5333, 5360, 5373, 5371, 5340, 5345, 5362, 1313, 5361, 1876, 5339, 5338, 5335, 5332, 6250
ms.date: 09/09/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Use Dynamics 365 Sales from Business Central

If you use [!INCLUDE [crm_md](includes/crm_md.md)] for customer engagement, you can enjoy seamless integration in the lead-to-cash process by using [!INCLUDE[prod_short](includes/prod_short.md)] for backend activities:

* Process orders
* Manage inventory
* Do your finances

Before you can use the integration capabilities, your system administrator must set up the connection and define users in [!INCLUDE[crm_md](includes/crm_md.md)]. Learn more in [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).

> [!NOTE]
> These steps describe the process of integrating online versions of [!INCLUDE[crm_md](includes/crm_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more about on-premises configurations in [Preparing Dynamics 365 Sales for Integration on-premises](/dynamics365/business-central/dev-itpro/administration/prepare-dynamics-365-for-sales-for-integration).

Integrating the applications lets you access data in Sales from [!INCLUDE[prod_short](includes/prod_short.md)], and in some cases the other way around. You can work with and synchronize data that both services have in common. For example, customers, contacts, and sales information. Synchronization keeps data up to date in both applications.  

For example, a sales person in [!INCLUDE[crm_md](includes/crm_md.md)] can use the price lists from [!INCLUDE[prod_short](includes/prod_short.md)] when they create a sales order. When they add the item to the sales order line in [!INCLUDE[crm_md](includes/crm_md.md)], they can check the inventory level (availability) of the item from [!INCLUDE[prod_short](includes/prod_short.md)].

Conversely, order processors in [!INCLUDE[prod_short](includes/prod_short.md)] can handle sales orders that are automatically or manually transferred from [!INCLUDE[crm_md](includes/crm_md.md)]. For example, they can create and post sales order lines for items or resources that were entered in [!INCLUDE[crm_md](includes/crm_md.md)] as write-in products. Learn more in [Handling Sales Order Data](marketing-integrate-dynamicscrm.md#handle-sales-order-data).

> [!IMPORTANT]  
> [!INCLUDE[prod_short](includes/prod_short.md)] integrates only with [!INCLUDE[crm_md](includes/crm_md.md)]. Other Dynamics 365 applications that change the standard workflow or data model in [!INCLUDE[crm_md](includes/crm_md.md)], for example Project Service Automation, can break the integration between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[crm_md](includes/crm_md.md)].

## Couple records

The assisted setup guide lets you choose the data to synchronize. Later, you can also set up synchronization for specific records, which is referred to as *coupling*. For example, you can couple a specific account in [!INCLUDE[crm_md](includes/crm_md.md)] with a specific customer in [!INCLUDE[prod_short](includes/prod_short.md)]. This section describes what to consider when you couple records.

For example, if you want to see accounts in [!INCLUDE[crm_md](includes/crm_md.md)] as customers in [!INCLUDE[prod_short](includes/prod_short.md)], you must couple the two types of records. To do that, on the **Customers list** page in [!INCLUDE[prod_short](includes/prod_short.md)], use the **Set Up Coupling** action. Then specify which [!INCLUDE[prod_short](includes/prod_short.md)] customers to match to which accounts in [!INCLUDE[crm_md](includes/crm_md.md)].

You can also create (and couple) an account in [!INCLUDE[crm_md](includes/crm_md.md)] based on, for example, a customer record in [!INCLUDE[prod_short](includes/prod_short.md)] using **Create Account in Dynamics 365 Sales**, or vice versa, using **Create Customer** in [!INCLUDE[prod_short](includes/prod_short.md)].

When you set up coupling between two records, you can also manually request current record, for example a customer, to be overwritten immediately by account data from Sales (or from [!INCLUDE[prod_short](includes/prod_short.md)]) using **Synchronize Now** action. The **Synchronize Now** action asks whether to overwrite Sales or [!INCLUDE[prod_short](includes/prod_short.md)] record data.

In some cases you must couple certain sets of data before other sets of data, as shown in the following table.

| Data | What to couple first |
|--|--|
| Customers and accounts | Couple salespeople with [!INCLUDE[crm_md](includes/crm_md.md)] users |
| Items and resources | Couple units of measure with [!INCLUDE[crm_md](includes/crm_md.md)] unit groups |
| Items and resource prices | Couple customer price groups with [!INCLUDE[crm_md](includes/crm_md.md)] prices |

> [!NOTE]  
> If your prices or customers use foreign currencies, make sure that you couple currencies to Sales transaction currencies.

In [!INCLUDE[crm_md](includes/crm_md.md)], sales orders depend on information such as customers, units of measure, currencies, customer price groups, and items and/or resources. For the integration with sales orders to work you must couple customers, units of measure, currencies, customer price groups, and items and/or resources.

## Fully synchronize records

At the end of the assisted setup guide, you can choose the **Run Full Synchronization** action to start synchronizing all [!INCLUDE[prod_short](includes/prod_short.md)] records with all related records in [!INCLUDE[crm_md](includes/crm_md.md)]. On the **Dynamics 365 Sales Full Synch Review** page, you choose the **Start** action. Full synchronization can take some time to complete, but you can continue to work in [!INCLUDE[prod_short](includes/prod_short.md)] while it runs in the background.

To check the progress of individual jobs in a full synchronization, on the **Dynamics 365 Sales Full Synch Review** page, choose a record to view details. To update the status during synchronization, refresh the page.

From the **Microsoft Dynamics 365 Connection Setup** page, you can get details about full synchronization at any time. From here, you can also open the **Integration Table Mappings** page to see details about the tables in [!INCLUDE[prod_short](includes/prod_short.md)] and Sales that must be synchronized.

## Synchronize on a recurring schedule

The integration provides a few default jobs in the job queue that synchronize data for you. The jobs synchronize data every 30 minutes, but you can change that schedule. Learn more about the default synchronization jobs in [Synchronization jobs for a Sales integration](admin-prepare-dynamics-365-for-sales-for-integration.md#synchronization-jobs-for-a-sales-integration). Learn more about the job queue in [Use job queues to schedule tasks](admin-job-queues-schedule-tasks.md).

## Handle sales order data

Sales orders that people submit in [!INCLUDE[crm_md](includes/crm_md.md)] transfer to [!INCLUDE[prod_short](includes/prod_short.md)] if you select the **Automatically Create Sales Orders** checkbox on the **Microsoft Dynamics 365 Connection Setup** page.

Alternatively, you can manually convert submitted sales orders from [!INCLUDE[crm_md](includes/crm_md.md)] by using the **Create in [!INCLUDE[prod_short](includes/prod_short.md)]** action on the **Sales Orders - Dynamics 365 for Sales** page.

On such sales orders, the **Name** field on the original order is transferred and mapped to the **External Document Number** field on the sales order in [!INCLUDE[prod_short](includes/prod_short.md)].

The same is true if the original sales order contains write-in products, meaning items or resources that aren't registered in either app. In that case, you must fill in the **Write-in Product Type** and **Write-in Product No.** fields on the **Sales & Receivables Setup** page so that sales of nonregistered products are mapped to a specified item or resource number.

> [!NOTE]
> You can't map write-ins to items or resources in [!INCLUDE[prod_short](includes/prod_short.md)] that are coupled with a product in [!INCLUDE[crm_md](includes/crm_md.md)]. To allow for write-ins, we recommend that you create an item or resource specifically for that purpose, and don't couple it with a product in [!INCLUDE[crm_md](includes/crm_md.md)].

If the description of the item on the original sales order is long, another sales order line of the type **Comment** is created to hold the full text on the sales order in [!INCLUDE[prod_short](includes/prod_short.md)].

Updates to fields on sales order headers, such as the **Last Shipment Date** or **Requested Delivery Date** fields, that are mapped in the **SALESORDER-ORDER** integration table mapping periodically synchronize to [!INCLUDE[crm_md](includes/crm_md.md)]. Processes such as releasing, shipping, and invoicing a sales order are posted to the sales order timeline in [!INCLUDE[crm_md](includes/crm_md.md)]. When sales orders in [!INCLUDE [prod_short](includes/prod_short.md)] are shipped, the **Last Shipment Date** field updates, and the status of the order in [!INCLUDE[crm_md](includes/crm_md.md)] is set to **Fulfilled**. Learn more in [Introduction to activity feeds](/dynamics365/sales-enterprise/manage-activities). Learn about the procedure to enable posting and activities for orders in [!INCLUDE[crm_md](includes/crm_md.md)] in [Set up the Notes control to access information about posts for a custom entity](/dynamics365/customerengagement/on-premises/customize/notes-control-legacy) in the Customer Engagement documentation. The article refers to Customer Engagement on-premises, but the steps are the same for the online version.

> [!NOTE]  
> Periodical synchronization based on the **SALESORDER-ORDER** integration table mapping works only when sales order integration is enabled. Learn more in [Connection settings on the Sales Connection Setup Page](admin-prepare-dynamics-365-for-sales-for-integration.md). Only sales orders created from submitted sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] synchronize. Learn more in [Enable Sales Order Processing Integration](/dynamics365/sales-enterprise/developer/enable-sales-order-processing-integration).

<!--> [!VIDEO https://go.microsoft] -->

If someone changes the price of a product in [!INCLUDE [crm_md](includes/crm_md.md)] and you include the item in sales orders in [!INCLUDE [prod_short](includes/prod_short.md)], [!INCLUDE [prod_short](includes/prod_short.md)] creates a new sales price list for each order. Learn more about price lists in [Handle sales prices](#handle-sales-prices).

Sales orders in [!INCLUDE[crm_md](includes/crm_md.md)] synchronize when their status is **Submitted**. Sales orders from [!INCLUDE [prod_short](includes/prod_short.md)] synchronize when their status is **Released**. The exception to this rule is when a prepayment is needed to complete a sales order in [!INCLUDE [prod_short](includes/prod_short.md)]. If an order is waiting prepayment, sales orders from [!INCLUDE[crm_md](includes/crm_md.md)] synchronize with a status of **Open** to let you complete the prepayment process. When you register the prepayment, the sales order's status changes to **Released** and synchronization continues.

## Handle sales quotes data

Sales quotes that are activated in [!INCLUDE[crm_md](includes/crm_md.md)] are transferred to [!INCLUDE[prod_short](includes/prod_short.md)] if you select the **Automatically Process Quotes** checkbox on the **Microsoft Dynamics 365 Connection Setup** page.

Alternatively, you can manually convert activated sales quotes from [!INCLUDE[crm_md](includes/crm_md.md)] by using the **Process in [!INCLUDE[prod_short](includes/prod_short.md)]** action on the **Sales Quotes - Dynamics 365 Sales** page.
On such sales quotes, the **Name** field on the original quote is transferred and mapped to the **External Document Number** field on the sales order in [!INCLUDE[prod_short](includes/prod_short.md)]. Also **Effective To** field on quote is transferred and mapped to the  **Quote Valid Until** field on sales quote in [!INCLUDE[prod_short](includes/prod_short.md)].  

Sales quotes go through many revisions while they're being finalized. Both manual and automatic processing of sales quotes in [!INCLUDE[prod_short](includes/prod_short.md)] ensures that previous versions of sales quotes are archived before processing new revisions of sales quotes from [!INCLUDE[crm_md](includes/crm_md.md)].

When you choose **Process** in [!INCLUDE[prod_short](includes/prod_short.md)] for a quote that is in state **Won**, a sales order is created in [!INCLUDE[prod_short](includes/prod_short.md)] only if a corresponding sales order is submitted in [!INCLUDE[crm_md](includes/crm_md.md)]. Otherwise, the quote is only released in [!INCLUDE[prod_short](includes/prod_short.md)]. If a corresponding sales order is submitted in [!INCLUDE[crm_md](includes/crm_md.md)] later, and a sales order is created from it, the **Quote No.** is updated on the sales order and the quote is archived.

## Handle posted sales invoices, customer payments, and statistics

After you fulfill a sales order, invoices are created for it. When you invoice a sales order, you can transfer the posted sales invoice to [!INCLUDE[crm_md](includes/crm_md.md)] if you select the **Create Invoice in [!INCLUDE[crm_md](includes/crm_md.md)]** checkbox on the **Posted Sales Invoice** page. Posted invoices transfer to [!INCLUDE[crm_md](includes/crm_md.md)] with the status, **Billed**.

When the customer payment is received for the sales invoice in [!INCLUDE[prod_short](includes/prod_short.md)], the sales invoice status changes to **Paid**. The **Status Reason** field is set to **Partial**, if partially paid, or **Complete** if fully paid, when you choose the **Update Account Statistics** action on the Customer Card page in [!INCLUDE[prod_short](includes/prod_short.md)]. The **Update Account Statistics** action refreshes values, such as the **Balance** and **Total Sales** fields in the **[!INCLUDE[prod_short](includes/prod_short.md)] Account Statistics** FactBox in [!INCLUDE[crm_md](includes/crm_md.md)]. Alternatively, you can run the Customer Statistics and POSTEDSALESINV-INV scheduled jobs for both of these processes in the background.

## Handle sales prices

> [!NOTE]
> In 2020 release wave 2, we released streamlined processes for setting up and managing prices and discounts. If you're a new customer using that version, you're using the new experience. If you're an existing customer, whether you're using the new experience depends on whether your administrator enabled the **New sales pricing experience** feature update in **Feature Management**. Learn more in [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

The steps to complete this process differ, depending on whether your administrator enabled the new pricing experience.

> [!NOTE]
> If the standard price synchronization doesn't work for you, we recommend using integration customization capabilities. Learn more in [Customizing an Integration with Microsoft Dataverse](/dynamics365/business-central/dev-itpro/administration/administration-custom-cds-integration).

#### [Current Experience](#tab/current-experience/)

In the current pricing experience, [!INCLUDE[prod_short](includes/prod_short.md)] synchronizes sales prices that:

* Apply to all customers. Default sales price lists are created based on the price in the **Unit Price** field on the **Item Card** page for the items.
* Apply to a specific customer price group. For example, sales prices for your retail or wholesale customers. To synchronize prices based on a customer price group, follow these steps:

    1. Couple the items for which the customer price group sets prices.
    2. On the **Customer Price Groups** page, couple the customer price group by choosing **Related**, then **Dynamics 365 Sales**, **Coupling**, and then **Set up coupling**. The coupling creates an active price list in [!INCLUDE[prod_short](includes/prod_short.md)] with the same name as the customer price group in [!INCLUDE[crm_md](includes/crm_md.md)]. It also automatically synchronizes all items for which the customer price group defines the price.

:::image type="content" source="media/customer-price-group.png" alt-text="Customer Price Group page.":::

#### [New Experience](#tab/new-experience/)  

The new pricing experience synchronizes price lists that meet the following criteria:

* **Allow Updating Defaults** is turned off.
* The price type is **Sale**.
* The amount type is **Price**.
* The product type on the lines must be **Item** or **Resource**.
* A minimum quantity isn't specified.

[!INCLUDE[prod_short](includes/prod_short.md)] synchronizes sales prices that apply to all customers. Default sales price lists are created based on the price in the **Unit Price** field on the **Item Card** page for the items.

To synchronize price lists, on the **Sales Price List** page, choose **Related**, **Dynamics 365 Sales**, **Coupling**, and then **Set up coupling**.

:::image type="content" source="media/sales-price-list.png" alt-text="Sales Price List page.":::

## Related information

- [Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
- [Relationship Management](marketing-relationship-management.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
- [Change Which Features are Displayed](ui-experiences.md)  
- [Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
- [Overview of Sales and Sales Hub](/dynamics365/customer-engagement/sales-enterprise/overview)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
