---
title: Czech Local Functionality - Bank feature
description: Learn about the Czech local banking feature, which provides improved efficiency and prevents users from making mistakes when entering the customer and vendor bank account data.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, Bank, Finance, CZ, Bank feature, company default bank account, Czech version
ms.date: 06/02/2025
ms.reviewer: v-soumramani
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Local banking feature in the Czech version

This feature provides improved efficiency and prevents users from making mistakes when entering the customer and vendor bank account data by capturing the bank specific information and eliminating the need to re-enter it every time. Such functionality is needed even more as more bank transactions are executed electronically.

## Banking setup

The new banking setup introduces:

- General Information – assigning to bank account number
- Numbering – Payment order numbers, bank statement numbers
- Import, Export Information
- Information for posting and applying
- Settings for payment orders and bank statements

New fields are added on the **Bank Account**, **Customer Bank Account**, and **Vendor Bank Account** pages.

## Company default bank account

The **Default Bank Account Code** field is added on the **Company Information** page.

## Sales documents and bank accounts

It's quite common for companies to have multiple bank accounts open with multiple banking institutions in order to lower the cost of financial transactions. For that purpose [!INCLUDE[prod_short](../../includes/prod_short.md)] needs to enable users to select the preferred bank account to be printed on sales documents.

The **Bank Account Code** field is added on sales documents, and information from the selected bank account is transferred to the sales header.

Additional fields for payment identification are added to the sales header, such as **Specific Symbol**, **Variable Symbol**, and **Constant Symbol**. This information is transferred to the posted document and customer ledger entry during posting. This allows you to apply payments to invoices precisely.

## Purchase documents and bank accounts

It's quite common for vendors to have multiple bank accounts open with multiple banking institutions. For this purpose [!INCLUDE[prod_short](../../includes/prod_short.md)] needs to enable users to select a vendor bank account for payment on purchase documents.

The **Vendor Bank Account Code** field is added on purchase documents and information from the selected vendor bank account is transferred to the purchase header.

Additional fields for payment identification were added to the purchase header, such as **Specific Symbol**, **Variable Symbol**, and **Constant Symbol**. This information is transferred to the posted document and vendor ledger entry during posting. This allows you to use this information for payments suggesting and application.

## Bank statement and payment orders

This allows you to create payment orders and bank statements. An unlimited number of bank accounts can be registered for various banking institutions and in different currencies. You can import and export files (listings and orders) from banking software.

### Main features

- Create, post, and export a payment order
- Create, import, and post a bank statement
- Bank statement rollover into a payment reconciliation journal
- Pairing entries in the payment reconciliation journal and posting

### Other supported features

- The **Payment Order** and **Bank Statement** pages can be used in addition to their own import/export functions and standard tools for the definition of import and export formats of banking components.
- Only the standard payment reconciliation journal is used to process statement files. The standard options for automatic alignment of the options are extended by specification. For example, the **O** variable symbol has been extended for payment comparison rules.
- Additional information and rules for calculating payments and text-based account mapping.
- Text mapping of accounts - for automatic matching of bank statement entries from the text given in the description, extension and mapping of accounts according to the variable symbol, constant symbol, specific symbol, bank account, IBAN code, and SWIFT.
- Payment reconciliation journal - the option to start and change automatically.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)
- [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md)
- [Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
