---
title: Set Up Service Management Processes
description: Learn how to set up processes that help ensure your customers are satisfied with your services.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: service, number sequences, setup, warnings, fee, contracts, warranties
ms.date: 03/17/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Configure service management processes

The following are some examples of the settings you can apply to service management processes:  
  
* Some overall settings for various processes, such as warnings, next service calculations for service items, the start-up fee to assess, the fault reporting level to use, and so on.  
* The types of information that technicians enter on service documents. For example, you can require them to specify the type of order, the start and/or end dates for the work, and the type of work that was done.  
* Some default settings for response times and warranties. These include a default response time for starting service, warranty discount percentages for parts and labor, and how long warranties are valid for.  
* Settings for contracts, such as the maximum number of days that you can use for contract service orders, whether to use reason codes when a contract is canceled, standard texts for descriptions, and contract values.  
* The number sequences to use for service-related documents and items.  

## To enter general and mandatory settings

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Management Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## Set up service invoice posting policies for users

Companies often have unique processes for invoices and shipments. For example, processes can vary from one person posting everything on a service order to multiple employees, each working with their own pages.

You can use posting policies to restrict users from posting service invoices, or require them to post invoices together with the related service shipment. To set up a posting policy, on the **User Setup** page, in the **Service Invoice Posting Policy** field, choose one of the following options:

* **Allowed** (Default): Keep the current behavior, where you can choose the posting options, such as **Ship**, **Invoice**, and **Ship and Invoice**.
* **Prohibited**: Prevent people from posting service invoices. [!INCLUDE [prod_short](includes/prod_short.md)] shows a confirmation dialog that only provides the **Ship** option.
* **Mandatory**: Let people post invoices along with service shipments. [!INCLUDE [prod_short](includes/prod_short.md)] shows a confirmation dialog that only provides the **Ship and Invoice** option.

This setting affects the following documents:

* Service orders
* Warehouse shipments
* Service invoices
* Service credit memos

The following table describes the effects on different documents.

|Document  |Allow<br>Displays a series of options   |Prohibited<br>Conformation dialog  |Mandatory<br>Confirmation dialog  |
|---------|---------|---------|---------|
|Service order     | * Ship<br>* Invoice<br>* Ship and Invoice<br>* Ship and Consume         |* Ship<br>* Ship and Consume  |Do you want to post the shipment and invoice?         |
|Warehouse Shipment     |* Ship<br>* Ship and Invoice         |Do you want to post the shipment?         | Do you want to post the shipment and invoice?        |
|Service invoice     | Do you want to post the invoice?         | Error: you cannot post.       |Do you want to post the invoice?         |
|Service credit memo     | Do you want to post the credit memo?         | Error: you cannot post.        |Do you want to post the credit memo?         |

> [!NOTE]
> When you post service invoices and credit memos, you don't have any posting options. The documents always post physical and financial transactions together. You can't partially post service invoices and credit memos.

## Send service documents to the right people

Your business probably deals with multiple customer and vendor contacts who are responsible for different areas of operation. For example, accountants, purchasers, and warehouse staff. Because their interests typically differ, you might want to generate and send different types of documents to them. You can save time when you send documents to different customer or vendor contacts by setting up specific contacts to use with specific documents. For example, send service invoices to accountant contacts and service orders to your customers' purchasers.

You can use the **Document Layouts** page to specify who to send service quotes, orders, invoices, and credit memos to for vendors and customers based on settings on the **Report Selection** page. To send specific documents to specific company contacts, choose the company contacts to use for specific document layouts. To learn more about document layouts, go to [Define document layouts for customers and vendors](ui-define-customer-vendor-document-layouts.md).

## Related information  

[Set Up Fault Reporting](service-how-setup-fault-reporting.md)  
[Set Up Resource Allocation](service-how-setup-resource-allocation.md)  
[Set Up Codes for Standard Services](service-how-setup-service-coding.md)  
[Set Up Additional Costs for Services](service-how-setup-service-costs-pricing.md)  
[Set Up Troubleshooting](service-how-setup-troubleshooting.md)  
[Service Management](service-service.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
