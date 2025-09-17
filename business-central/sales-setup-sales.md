---
title: Overview of tasks to configure sales processes
description: Overview of tasks required to set up rules and values that define your sales policies and processes including general set-up and finance related sales set-up.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: trade, sell, configure
ms.search.form: 170, 172, 300, 301, 428, 456, 459, 1401
ms.date: 06/06/2024
ms.service: dynamics-365-business-central

---
# Setting up sales

Before you can manage sales processes, you must configure the rules and values that define the company's sales policies.

You must define the general setup on the **Sales & Receivables** page, such as which sales documents are required, how their values are posted, and the type of lines to create by default. This general setup is typically performed once during the initial implementation.

A separate series of tasks related to registering new customers is to record any special price or discount agreements that you have with each customer. For more information, see [Record Special Sales Prices and Discounts](sales-how-record-sales-price-discount-payment-agreements.md).

Finance-related sales setup, such as payment methods and currencies, are covered in the Finance Setup section. For more information, see [Setting Up Finance](finance-setup-finance.md).

| To | See |
| --- | --- |
| Create a customer card for each customer that you sell to. |[Register New Customers](sales-how-register-new-customers.md) |
| Enable customers to pay through PayPal by choosing the PayPal logo on sales documents. |[Enable Customer Payment Through PayPal](sales-how-enable-payment-service-extensions.md) |
| Enter the different discounts and special prices that you grant to customers depending on item, quantities, and/or date. |[Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md) |
| Set up salespeople so that you can assign them to customer contacts or measure salespeople's performance as a basis for calculating the sales commission or bonus. |[Set Up Salespeople](sales-how-setup-salespeople.md) |
| Specify for individual customers or for all customers how sales documents are sent by default when you choose the **Post and Send** action. |[Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md) |
| Set your email up to contain a summary of information in the sales document that is being sent. |[Send Documents by Email](ui-how-send-documents-email.md) |
|Use an EU web service to verify a customer's VAT registration number.|[Verify VAT Registration Numbers](finance-setup-vat.md)|
|Define the different incoterms that you offer to customers or that your vendors offer you.|[Set Up Shipment Methods](sales-how-set-up-shipment-methods.md)|
|Enter information about the different transportation vendors you use, including a link to their package tracking service.|[Set Up Shipping Agents](sales-how-to-set-up-shipping-agents.md)|
|Specify default reports to be used for different document types.|[Report Selection in Business Central](across-report-selections.md)|
|Specify whether users are allowed to post sales invoices, and whether they must post them together with a shipment. |[Define an invoice posting policy for users](admin-setup-invoice-posting-policy.md)|

## Related information
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
