---
title: Payables and receivables in the Czech Version
description: Learn about payables and receivables features specific to the Czech version, including credits, exchange rate adjustments, and local reporting requirements.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, Receivables, Payables, Finance, CZ, Cash
ms.date: 06/05/2025
ms.reviewer: v-soumramani
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Payables and receivables in the Czech version

## Credits

Sometimes, a company's customers are also to some extent company vendors. In such situations, it's common for companies to compensate their receivables and payables.

The main features of the Credits functionality are:  

- View Balance as Vendor/Balance as Customer – to view the balance as vendor on a customer card and the balance as customer on a vendor card, users must set a customer and vendor business relation with a contact to indicate to the system that even though particular company is registered as a vendor and as a customer, it is in fact the same company.
- Credits Setup – Credit Nos., Credit Bal. Account No., etc.
- Credit Maintaining on Credit Card – choose Customer/Vendor, suggest lines/entries for compensation.
- Agreement printout.
- Credit posting – posted credit is created, entries application is posted.

Entries to be counted can be entered manually or automatically from the Credit Card. In addition, there are functions to mark entries to count and balance the balance.

There's also a print of the Agreement on Mutual Settlement of Receivables and Payables under Czech legislation.

## Exchange rates adjustment feature

The majority of companies in the Czech Republic request the following improvements to be implemented in Exchange Rates Adjustment:

- Ability to run Exchange Rates Adjustment for Customers, Vendors, and Bank Accounts separately
- Ability to have Exchange Rates Adjustment batch post adjustments in detail and summarized per currency
- Ability to run Exchange Rates Adjustment just as simulation (without posting) in Test Mode

On standard report Adjust Exchange Rates is now possible to:

- Set Bank Account, Customer, Vendor filter for adjustment
- Choose adjustment for Customer or Vendor or Bank Account
- Choose the test mode
- Choose summarizing entries
- Choose the method for dimension transfer

The Adjust Exchange Rate report feature also modifies the calculation principle for implemented gains and losses based on the Income Tax Act. This feature calculates the implemented gain or loss against the recently adjusted amount.

This feature in the standard version of Microsoft [!INCLUDE[prod_short](../../includes/prod_short.md)] reverses the non-implemented gain or loss first, and calculates the implemented gain or loss afterwards. The calculation is expressed against the amount in the initial exchange rate during the application of the payment and the invoice.

The new calculation principle is implemented for fluctuation in the already adjusted exchange rate.
The Adjust Exchange Rates batch job has been for Czech Advance Payments has also been extended.

## Multiple payables/receivables accounts

Users often post transactions like bad debt or other types of Receivable/Payable transactions that need to be recorded in Customer and Vendor Ledgers, but at same time posted to different Receivable/Payable GL Account, other than the one specified on Customer or Vendor posting groups. The easiest way to enable such functionality is to allow users to change Customer and Vendor posting groups in the moment of posing a particular transaction.

## Customers/vendors reconciliations

At the end of each fiscal year (or another period, when requested), companies send a statement of balances to Customers and Vendors in order to reconcile them with Customer and Vendor records. Customers and Vendors either confirm the statement or not and send it back with corrections, based on their own information. This feature allows users to prepare such report in [!INCLUDE[prod_short](../../includes/prod_short.md)].

## Sales correcting documents

According to the VAT law amendment, it's necessary to differentiate types of Sales Credit-Memo documents. This feature allows users to set up the following Credit Memo Types:

- Corrective Tax Document
- Internal Correction
- Insolvency Tax Document

This Credit Memo Type defines how is handled Postponed VAT on Sales Credit-Memo documents.

## Contacts actualization from ARES

ARES stands for Access to Register of Economic Subjects. ARES is an information system allowing retrieval of information on economic entities registered in the Czech Republic.  

The user can fill in ARES Http in Reg. No. Validation Service Setup.
It's possible to run ARES actualization from Contact, Vendor, and Customer Card. It's possible to search the company and decide which fields can be updated in [!INCLUDE[prod_short](../../includes/prod_short.md)](Name, Address, City, Post Code).

## New design of output documents

A new set of printed reports for external documents is created. All documents have the same layout design (headers, footers, font type, and size, etc.).
Additionally to standardization, Dynamics NAV documents were extended according to all requirements required by the Czech legislation:  

- Registration No., VAT Registration No.
- Deduction of advances with information about invoice and date of payment received
- VAT specification printout grouped by VAT Identifier
- Naming of tax corrective documents based on Credit Memo type
- Printout of documents related to advance payments

### List of reports in the CZ document set

- **Sales – Advance Letter CZ**
- **Sales – Advance Invoice CZ**
- **Sales – Advance Credit Memo CZ**
- **Purchase – Advance Letter CZ**
- **Purchase – Advance Invoice CZ**
- **Purchase – Advance Cr. Memo CZ**
- **Purchase – Quote CZ**
- **Order CZ**
- **Return Order Confirmation CZ**
- **Sales – Quote CZ**
- **Order Confirmation CZ**
- **Sales – Invoice CZ**
- **Sales – Credit Memo CZ**
- **Sales – Shipment CZ**
- **Sales – Return Receipt CZ**
- **Charge Memo CZ**
- **Reminder CZ**
- **Service - Contract CZ**
- **Service - Contract Quote**
- **Service - Quote CZ**
- **Service - Order CZ**
- **Service - Invoice CZ**
- **Service - Credit Memo CZ**
- **Service - Shipment CZ**

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
