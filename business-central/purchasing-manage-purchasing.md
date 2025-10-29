---
title: Overview of tasks to manage purchasing 
description: Outlines tasks to manage your purchasing or procurement processes, including how purchase invoices and purchase orders work.
author: brentholtorf
ms.topic: overview
ms.search.keywords: procurement, supply, vendor order, purchsing
ms.search.form: 460, 9307
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Purchasing

You create a purchase invoice or purchase order to record the cost of purchases and to track accounts payable. If you need to control an inventory, purchase invoices are also used to dynamically update inventory levels so that you can minimize your inventory costs and provide better customer service. The purchasing costs, including service expenses, and inventory values that result from posting purchase invoices contribute to profit figures and other financial KPIs on your Role Center.

You must use purchase orders if your purchasing process requires that you record partial receipts of an order quantity. For example, because the full quantity wasn't available at the vendor. If you sell items by delivering directly from your vendor to your customer, as a drop shipment, then you must also use purchase orders. Learn more in [Make Drop Shipments](sales-how-drop-shipment.md). In all other aspects, purchase orders work the same way as purchase invoices.

You can have purchase invoices created automatically by using the OCR (Optical Character Recognition) service to convert PDF invoices from your vendors to electronic documents, which are then converted to purchase invoices by a workflow. To use this functionality, you must first sign up for the OCR service, and then perform various setups. Learn more in [Incoming Documents](across-income-documents.md).

Products can be both inventory items and services. Learn more in [Register New Items](inventory-how-register-new-items.md).

For all purchase processes, you can use an approval workflow, for example, to require that an accounting manager approves large purchases. Learn more in [Use Approval Workflows](across-how-use-approval-workflows.md).

The following sections describe a sequence of tasks, with links to the articles that cover them.

## Get started with purchase capabilities

Before you to buy goods, specify how you want to manage your company's purchase processes.

|To...| Go to... |
|---|---|
| Configure the rules and values that define your company's purchase policies. | [Set up purchase](purchasing-setup-purchasing.md) |
| Register each vendor you purchase from with a vendor card. | [Register new vendors](purchasing-how-register-new-vendors.md) |

## Purchase analytics

This section describes the analytical tools you can use to get insights into your purchase processes.

| To... | Go to... |
| --- | --- |
| Get an overview of your capabilities for analyzing purchase data. | [Purchasing analytics overview](purchasing-analytics-overview.md) |
| Analyze and monitor your procurement KPIs with the Power BI Purchasing app. | [Power BI Purchasing app](purchases-powerbi-app.md) |
| Do ad-hoc analysis of purchase data directly on list pages and queries. | [Ad-hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md) |
| Explore built-in purchase reports. | [Built-in purchasing reports](purchase-reports.md) |

## Quote to order for purchase invoices

The following table describes how to use simple purchase processes.

| To... | Go to... |
| --- | --- |
|Create a purchase quote to reflect a request for quote from your vendor, which you can later convert to a purchase order.|[Request Quotes](purchasing-how-request-quotes.md)|
| Create a purchase invoice for all or selected lines on a sales invoice. |[Purchase Items for a Sale](purchasing-how-purchase-products-sale.md) |
| Create a purchase invoice to record your agreement with a vendor to purchase products on certain delivery and payment terms. |[Record Purchases](purchasing-how-record-purchases.md) |
| Learn how [!INCLUDE[prod_short](includes/prod_short.md)] calculates when you must order an item to receive it on a certain date.|[Date Calculation for Purchases](purchasing-date-calculation-for-purchases.md)|
|Understand what happens when you post purchase documents.|[Posting Purchases](ui-post-purchases.md)|

If you need more complex purchase processes, the following table lists articles that explain what you can do with [!INCLUDE[prod_short](includes/prod_short.md)].

| To... | Go to... |
| --- | --- |
| Perform an action on an unpaid posted purchase invoice to automatically create a credit memo and either cancel the purchase invoice or recreate it so you can make corrections. |[Correct or Cancel Unpaid Sales Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md) |
| Create a purchase credit memo to revert a specific posted purchase invoice to reflect which products you're returning to the vendor and which payment amount you collect. |[Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md) |
|Manage your commitment to a vendor to purchase large quantities delivered in several shipments over time.|[Work With Blanket Purchase Orders](sales-how-to-create-blanket-sales-orders.md)|

## Canceled orders, refunds, and returns

The following table describes how to deal with canceled orders, refunds, and returns of goods that you purchase.

| To | Go to |
| --- | --- |
|Prepare to invoice multiple receipts from the same vendor once by combining the receipts on one invoice.|[Combine Receipts on a Single Invoice](purchasing-how-to-combine-receipts.md)|
|Convert, for example, electronic invoices from your vendors to purchase invoices inside Business Central.|[Receive and Convert Electronic Documents](purchasing-how-to-receive-and-convert-electronic-documents.md)|

## Other processes in sales

The following table describes how to deal with other purchase processes.

| To... | Go to... |
| --- | --- |
|Resolve confusion when two or more records exist for the same vendor.|[Merge Duplicate Records](sales-how-merge-duplicate-records.md)|

## External document numbers

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## Related information

[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Purchasing analytics overview](purchasing-analytics-overview.md)  
[Managing Payables](payables-manage-payables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
