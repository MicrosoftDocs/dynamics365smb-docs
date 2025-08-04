---
title: Overview of usage based billing 
description: Get an overview of the features for usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Overview of usage based billing

Demand-based provisioning of services requires a high degree of flexibility in how you create and bill the services. Subscription billing combines all of the steps in usage based billing in one place, from import of billing data to creating and posting documents.  

Depending on the pricing model, a monthly basic fee plus a usage-dependent fee (such as per user, per transaction, and so on) can be charged for use. In addition, prices can often also vary depending on the quantity. For example, you can use graduated prices.

## Import and process usage data

If your company offers services on demand, it can be time-consuming to bill these individually. Information is often missing, or the billing is confusing. Usage based billing extends the recurring billing features of subscription billing. To learn more, go to [Overview of subscription billing](../SRB/welcome.md). Usage based billing lets you seamlessly import usage data from various vendors into [!INCLUDE [prod_short](../includes/prod_short.md)], which processes the data and calculates prices. Using contracts, you can create contract invoices. If you want, you can also display a detailed overview of all items on the invoices. You can include the overview when you print the invoice.

## Usage data​

If usage data is the basis for billing service commitments, you can import and process the data. Processing the data creates any data that missing, such as service objects, service commitments, and contracts. You process data one time per subscription. Afterwards, [!INCLUDE [prod_short](../includes/prod_short.md)] processes usage data automatically.

The types of usage data can be quite different. The following types are widely used:

* Quantity used per period
* Transaction volume
* Consumption based usage of resources

## Features for usage data billing

The usage based billing features in subscription billing offer a flexible way to bill customers for monthly usage data for subscription contracts. The features make it easier to transform the large amount of monthly usage data that cloud-based services generate, for example, into individual invoices.

* Import usage data from suppliers using files or web services. Usage based billing offers a generic import for CSV files that you can use individually and independent of suppliers.
* Do accurate daily billing, even for quantity changes and partial periods.
* Create billing proposals with details for all services to bill in a single overview.
* Overview billing details in contract invoices. If needed, the overview can show all items individually.
* Issue contract credits and refunds. Unused quantities can automatically lead to credit memos for vendor and customer contract invoices.

## The process flow in usage based billing

First, you set up a **Usage Data Supplier**, and then use **Data Exchange Definitions** to create an import schema for usage data. You'll link the data exchange definition to the **Usage Data Supplier**.

Afterwards, a new **Usage Data Import** is created for the supplier so that you can import usage data in files.

The imported data is then processed. If an error occurs (e.g. because new usage data not previously known to the system is included in the import), the reasons for the non-processing can be corrected and the processing restarted.

## Billing for usage based service commitments​

You link usage data and related usage data subscriptions contracts through service commitments. When you process usage data, prices are calculated. For service commitments for vendors, the prices of the supplier are taken over. For service commitments for customers, the calculation is done using the corresponding methods for pricing.

The final step is to create contract invoices. You can create invoices for the contracts that include the usage based service commitments from several places:

* The **Recurring Billing** page
* The **Customer Contract** and **Vendor Contract** pages
* The **Usage Data Imports** page

## Related information

[Extension of service commitments](masterdata/service-commitments.md)  
[Linking subscription with service object](processing-usage-data/connect-subscription-service-object.md)  
[Imports and processing](processing-usage-data/imports-processing.md)
[Extend contract](processing-usage-data/extend-contract.md)
