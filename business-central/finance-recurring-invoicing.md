---
title: Work with recurring revenue
description: Learn about the available options to automate sending subscription invoices to your customers and register recurring revenue.
author: brentholtorf
ms.topic: reference
ms.devlang: al
ms.search.keywords: recurring, invoicing, subscription, billing
ms.search.form: 283 
ms.reviewer: bholtorf
ms.date: 03/07/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Work with recurring revenue in [!INCLUDE[prod_short](includes/prod_short.md)]

Many companies are moving from a business revenue model where revenue is made from a customer's one-time purchase to a subscription model where revenue is made on a recurring basis in return for consistent access to the delivery of a good or service.
[!INCLUDE[prod_short](includes/prod_short.md)] has the following options for automating how you send subscription invoices to your customers and register recurring revenue. 

## Register revenue with a recurring general journal

A recurring journal is a general journal with specific fields for managing transactions that you post frequently with few or no changes, such as rent, subscriptions, electricity, or heat. Using these fields for recurring transactions, you can post both fixed and variable amounts. 
With a recurring journal, entries that are posted regularly need to be typed in only once. That is, the accounts, dimensions and dimension values, and so on, that you enter will remain in the journal after posting. If any adjustments are necessary, you can make them with each posting.

### Why use this option

With this option, you define flexible invoicing periods with [Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

However, with this option, you can't print and send invoices in the default version of [!INCLUDE[prod_short](includes/prod_short.md)].  

For more information, see [Work with Recurring Journals](ui-work-general-journals.md#work-with-recurring-journals).  

## Create multiple invoices based on a recurring project journal

The recurring job journal is a more advanced alternative to the general journal. You define Items, Resources, and G/L Accounts that must be repeated for each job and you specify the frequency of recurrence.  

After posting a recurring project journal, you can create multiple invoices with the **Create Job Sales Invoice** task. You can review and post created invoices in the **Sales Invoices** page.

### Why use this option

With this option, you follow the standard invoicing procedure with all the benefits of that, including standard and customer layouts for communication preferences. You can also define prices for each project individually.

However, for each new customer, you must create a new project and add lines to the recurring journal. 

For more information, see [Create project journal lines](projects-how-record-job-usage.md#to-create-project-journal-lines-manually) and [Create multiple project sales invoices](projects-how-invoice-jobs.md#to-create-multiple-project-sales-invoices).

## Create multiple invoices based on recurring sales lines

If you often need to create sales and purchase lines with similar information, you can set up recurring sales lines that you can then insert on recurring sales and purchase documents, for example, for recurring replenishment orders. Use the **Create Recurring Sales Invoices** batch job to create sales invoices according to recurring sales lines that are assigned to the customers and with posting dates within the valid-from and valid-to dates that you specify on the recurring sales lines.  

### Why use this option

With this option, you can assign the same recurring lines to multiple customers. You can define period of validity for the recurring sales lines for specific customer. You can assign multiple recurring lines to the same customer and all of them will be included in the invoice.

However, there's no way to set fixed prices for items because [!INCLUDE[prod_short](includes/prod_short.md)] will use the actual prices and discount valid on document date, trying to find best combination that gives the lowest price.  

For more information, see [Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md).

## Recurring invoices with service contract

A service contract contains the service contract agreements between your customers and your company. A service contract includes service level agreements and the service items that you service as a part of the contract.  

You can define the starting date of the contract, the invoice period, whether or not the contract is prepaid, price update specifications if you plan to change prices while contract is active. You can use both service items or items in service contract lines.
You can create contract templates to define how to create certain types of contracts.  

### Why use this option

With this option, you use a part of the advanced service management functionality that not limited to issuing of recurring invoices but support repair shop and field service operations.

However, this option requires the Premium license. Setting up service management and maintaining it might not give huge advantages in simpler subscription scenarios.  

For more information, see [Work with Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md) and [Invoice several service contracts](service-how-create-invoices.md#invoice-several-service-contracts).

## Related features
There are several related capabilities in [!INCLUDE[prod_short](includes/prod_short.md)].

### Blanket sales orders

A blanket sales order represents a framework for a long-term agreement between your company and your customer.
A blanket order is typically made when a customer has committed to purchasing large quantities that are to be delivered in several smaller shipments over a certain period of time. Often blanket orders cover only one item with predetermined delivery dates. The main reason for using a blanket order rather than a sales order is that quantities entered on a blanket order don't affect item availability, however it can be used for planning purposes.

#### Why use this option

With this option, you use the anticipated demand, so the information is considered during the normal planning routines. For more information, see [Demand Forecasts and Blanket Orders](design-details-central-concepts-of-the-planning-system.md#demand-forecasts-and-blanket-orders).  

However, the default version doesn't offer an out-of-the-box possibility to process multiple blanket orders in bulk.

For more information, see [Work with Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md).

### Recurring Orders (Norway)

You can use recurring orders to create blanket order templates so that sales orders can be created based on date intervals that you define. For example, if you deliver the same sales order every two weeks, you can use a blanket sales order and create recurring orders.
You can use recurring groups to define a range of parameters that show how you make the orders. These groups are assigned to blanket orders that have to be created regularly. To create the recurring orders, you'll have to periodically run the create recurring orders process.

#### Why use this option

With this option, you can choose between fixed and "best" prices.

However, this is only available in Norway. Validity period can be defined on the recurring group level.

For more information, see [Recurring Orders](LocalFunctionality/Norway/recurring-orders.md).

### Recurring revenue and subscription billing by other providers

At [AppSource.microsoft.com](https://appsource.microsoft.com/), you can get extensions for Business Central. Some extensions are provided by Microsoft, and other extensions are provided by other companies. The list of the extensions by other companies grows each month. So keep an eye out for [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646) and get apps to help you in your work in Business Central.  

## Related information

[Date Formulas](ui-enter-date-ranges.md#use-date-formulas)  
[Work with Recurring Journals](ui-work-general-journals.md#work-with-recurring-journals)  
[Create project journal lines](projects-how-record-job-usage.md#to-create-project-journal-lines-manually)  
[Create multiple project sales invoices](projects-how-invoice-jobs.md#to-create-multiple-project-sales-invoices)  
[Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md)  
[Work with Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md)  
[Invoice several service contracts](service-how-create-invoices.md#invoice-several-service-contracts)  
[Demand Forecasts and Blanket Orders](design-details-central-concepts-of-the-planning-system.md#demand-forecasts-and-blanket-orders)  
[Work with Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md)  
[Recurring Orders (Norway)](LocalFunctionality/Norway/recurring-orders.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
