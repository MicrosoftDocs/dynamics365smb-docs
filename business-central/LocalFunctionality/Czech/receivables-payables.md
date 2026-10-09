---
title: Payables and receivables in the Czech Version
description: Learn about payables and receivables features specific to the Czech version, including compensations, exchange rate adjustments, and local reporting requirements.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, Receivables, Payables, Finance, CZ, Cash
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Payables and receivables in the Czech version

## Compensations

Sometimes, a company's customers are also, to some extent, company vendors. In such situations, it's common for companies to compensate (offset) their receivables and payables.

The main features of the compensation functionality are:

- **View Balance as Vendor/Balance as Customer**: To view the balance as vendor on a customer card and the balance as customer on a vendor card, you must set a customer and vendor business relation with a contact to indicate that even though a particular company is registered as both a vendor and a customer, it's in fact the same company.
- **Compensations Setup**: **Compensation Nos.**, **Compensation Bal. Account No.**, and so on.
- **Compensation Card**: Choose the customer or vendor, and propose lines or entries for compensation.
- **Agreement on Mutual Settlement of Receivables and Payables** printout.
- **Compensation posting**: A posted compensation is created, and applications for entries are posted.

You can enter entries to count manually on the **Compensation Card** page, or use the **Propose Compensation Lines** action to propose them automatically. There are also functions to mark entries to count and recalculate the balance.

For more information, go to [Compensation localization extension for the Czech version](ui-extensions-compensations-localization-cz.md).

## Exchange rates adjustment feature

Most companies in the Czech Republic request the following improvements to be implemented in Exchange Rates Adjustment:

- Ability to run Exchange Rates Adjustment for Customers, Vendors, and Bank Accounts separately
- Ability to have Exchange Rates Adjustment batch post adjustments in detail and summarized per currency
- Ability to run Exchange Rates Adjustment just as simulation (without posting) in Test Mode

When the Core Localization Pack for Czech is installed, the standard **Exchange Rate Adjustment** report is replaced with the **Adjust Exchange Rates Enhanced** report. On this report, you can:

- Set Bank Account, Customer, Vendor filter for adjustment
- Choose adjustment for Customer or Vendor or Bank Account
- Choose the test mode
- Choose to summarize entries
- Choose the method for dimensions transfer

The Adjust Exchange Rates Enhanced report also changes the calculation principle for realized gains and losses, based on the Income Tax Act. This feature calculates the realized gain or loss against the most recently adjusted amount.

By contrast, the standard version of Microsoft [!INCLUDE[prod_short](../../includes/prod_short.md)] reverses the unrealized gain or loss first, and then calculates the realized gain or loss. That calculation is based on the amount at the initial exchange rate, from when the payment was applied to the invoice.

The new calculation principle accounts for fluctuation in the already adjusted exchange rate. The Adjust Exchange Rates batch job has also been extended for Czech Advance Payments.

## Multiple payables/receivables accounts

Users often post transactions, like bad debt or other types of receivable/payable transactions, that need to be recorded in the customer and vendor ledgers, but posted to a different receivable/payable G/L account than the one specified on the customer's or vendor's posting group. This capability is provided by the standard [!INCLUDE[prod_short](../../includes/prod_short.md)] alternative posting groups feature. For more information, go to [Set up posting groups](../../finance-posting-groups.md#allow-alternative-posting-groups-on-documents).

## Customers/vendors reconciliations

At the end of each fiscal year (or another period, when requested), companies send a statement of balances to customers and vendors to reconcile them with the customer and vendor records. Customers and vendors either confirm the statement or send it back with corrections, based on their own information. This feature lets you prepare such a statement in [!INCLUDE[prod_short](../../includes/prod_short.md)] by choosing the **Balance Reconciliation** action on the customer or vendor card.

## Sales correcting documents

Under the VAT law amendment, companies must differentiate types of sales credit memo documents. This feature lets you set up the following credit memo types:

- Corrective Tax Document
- Internal Correction
- Insolvency Tax Document

The credit memo type defines how postponed VAT is handled on sales credit memo documents.

## Contacts actualization from ARES

ARES stands for Access to Register of Economic Subjects. ARES is an information system that lets you retrieve information on economic entities registered in the Czech Republic.

To turn on the integration, go to the **Registration No. Validation Service Setup** page, and fill in the **Service Endpoint** field. After you turn on the **Enabled** toggle, [!INCLUDE[prod_short](../../includes/prod_short.md)] automatically checks the registration number against ARES whenever you enter or change the **Registration Number** field on the Contact, Vendor, or Customer card. If the information that's returned from ARES doesn't fully match the record, the **Registration No. Check** page opens so you can review and choose which fields to update (Name, Address, City, Post Code).

## New design of output documents

A new set of printed reports for external documents is created. All documents have the same layout design (headers, footers, font type, and size, and so on).

In addition to standardization, Dynamics NAV documents are extended to meet the requirements of Czech legislation:

- Registration No., VAT Registration No.
- Deduction of advances with information about invoice and date of payment received
- VAT specification printout grouped by VAT Identifier
- Naming of tax corrective documents based on Credit Memo type
- Printout of documents related to advance payments

### List of reports in the CZ document set

- **Sales - Advance Letter**
- **Sales - Invoice with Advance**
- **Purchase - Advance Letter**
- **Purchase - Invoice with Advance**
- **Purchase Quote**
- **Purchase Order**
- **Sales Return Order Confirmation**
- **Sales Quote**
- **Sales Order Confirmation**
- **Sales Invoice**
- **Sales Credit Memo**
- **Sales Shipment**
- **Sales Return Reciept**
- **Finance Charge Memo**
- **Reminder**
- **Service Contract**
- **Service Contract Quote**
- **Service Quote**
- **Service Order**
- **Service Invoice**
- **Service Credit Memo**
- **Service Shipment**

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
