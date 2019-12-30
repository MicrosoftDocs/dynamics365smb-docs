---
title: Czech Local Functionality - Bank feature| Microsoft Docs
description: This section describes Czech local functionality - Bank feature
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Bank, Finance, CZ, Bank feature
ms.date: 12/30/2019
ms.reviewer: v-pejano
ms.author: v-makune
---

# Local Banking Feature
This feature provides improved efficiency and prevents user from making mistakes during entering the Customer and Vendor bank account data by capturing the bank specific information and eliminating the need to re-enter it every time. Such functionality is needed even more as more bank transactions are executed electronically.

## Banking Setup
New Banking setup introduces: 
- General Information – assigning to Bank Account No.
- Numbering – Payment orders Nos., Bank statement No.
- Import, Export Information
- Information for posting and applying
- Settings for payment orders / bank statements
  
New fields added in Bank Account, Customer Bank Account and in Vendor Bank Account.

## Company Default Bank Account

Default Bank Account Code added to the Company Information.

## Sales Documents and Bank Accounts

It is quite common for companies to have multiple bank accounts open with multiple banking institutions in order to lower the cost of financial transactions. For that purpose [!INCLUDE[d365fin](../../includes/d365fin_md.md)] needs to enable users to select the preferred bank account to be printed on Sales Documents.
Bank Account Code selection was added on Sales Documents, and information from selected bank account is transferred to the Sales Header.

Additional fields for payment identification were added to the Sales Header (Specific Symbol, Variable Symbol, Constant Symbol, etc.). This information is transferred to the posted document and Customer Ledger Entry during posting. This allows payments application to invoices precisely.

## Purchase Documents and Bank Accounts

It is quite common for Vendors to have multiple bank accounts open with multiple banking institutions. For this purpose [!INCLUDE[d365fin](../../includes/d365fin_md.md)] needs to enable users to select Vendor bank account for payment on Purchase Documents.

Vendor Bank Account Code selection was added on Purchase documents and information from selected Vendor bank account is transferred to the Purchase Header.

Additional fields for payment identification were added to the Purchase Header (Specific Symbol, Variable Symbol, Constant Symbol, etc.). This information is transferred to the posted document and Vendor Ledger entry during posting. This allows using this information for payments suggesting and also applying afterwards.

## Bank statement and Payment Orders

Allows you to create payment orders and bank statements. Unlimited number of bank accounts can be registered various banking institutions and in different currencies. You can import and export files (listings and orders) from banking software.

### Main Features:
- Create, post and export a payment order
- Create, import, and post a bank statement
- Bank statement rollover into a payment reconciliation journal
- Pairing entries in the payment reconciliation journal and posting

### Other supported features:
- The Payment Order and Bank Statement documents can be used in addition to their own import / export functions and standard tools for the definition of import and export formats of banking components.
- Only standard payment reconciliation journal is used to process statement files. The standard options for automatic alignment of the options are extended by specification (eg, the O variable symbol has been extended for payment comparison rules).
- Additional information and rules for calculating payments and text-based account mapping.
- Text mapping of accounts - for automatic matching of bank statement entries from the text given in the description, extension and mapping of accounts according to variable symbol, constant symbol, specific symbol, bank account, IBAN code and SWIFT.
- Payment reconciliation journal - the option to start and change automatically.

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)
