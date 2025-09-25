---
title: Cash Desk Localization for Czech (Extension)  
description: Provides features for cash register operations in compliance with Czech legislation and best practices for Microsoft Dynamics 365 Business Central.
author: v-pejano
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: Czech, CashDesk, Finance, CZ, Cash
ms.date: 09/25/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Cash desk localization for Czech (extension)

In the Czech version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)], the Cash Desk functionality helps companies with the legislation requirements and best practices in Cash Desk operations.

The Cash Desks and Cash Documents features allow you to define cash accounts and Cash Desks for the physical receipt and money withdrawal. Each Cash Desk must have a separate number series of the cash documents. You can set up separate number series for the receipt cash documents and withdrawal cash documents. The Cash Desk cases are predefined cases to simplify data entry. You can specify individual user authorized to operate with the particular Cash Desk and transmit Cash Desks between users.

## Key features

- Cash Desk setup, Cash Desk users
- Receipt cash document, withdrawal of cash documents and their posting
- Cash Desk cases used as templates for usual accounting transactions
- Payment application with customer and vendor ledger entries
- Payment Application with advance invoices
- The Reconciliation function - a preview of journal movements and balances after posting across all accounts (G/L accounts, other types of accounts: bank, vendor, customer, etc.).
- Cash Desk inventory
- Output documents (receipt cash document, withdrawal cash document)
- Reports - Cash Desk Account Book, Cash Desk Book, Cash Desk Hand Over

The Cash Desk card contains basic information about the Cash Desk, such as number, currency, contact details, etc. It also contains settings for posting, definitions for controls and limits, and preset No. series for Cash Desk documents.

![Cash Desk card](Media/cash-desk.png)

Cash Desk documents are either receipts or withdrawals and can be in different currencies depending on the Cash Desk. The documents also allow issuing, posting, and printing of output documents.

![Cash Desk documents](Media/cash-desk-document.png)

## Cash desk user setup

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Cash Desk Setup**, and then choose the related link.
1. On the **Cash Desk Setup** page under the **Navigation** tab, use the **Cash Desk Users** feature.
1. The Cash Desk Users tab opens. To create a new user, use the **New** function.
1. In the row, select the **Cash Desk No.** that the user will be working on. Next, select the **User ID** and select whether the user has the option to **Issue**, **Post**, or **Post EET only**.
1. After setup, close the page.

## Setting up No. series for receipts and withdrawals

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Cash Desk Setup** and then choose the related link.
1. Open the card of the selected Cash Desk.
1. On the **Cash Desk Setup Card**, you can find the **No. series** tab.
1. In the **Cash Receipt Order No.** and **Withdrawal Receipt No.** fields, select the No. series you want to use.
1. After setting up, close the Cash Desk settings card.

## Setting up cash desk events

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Cash Desk Events Setup**, and then choose the related link.
1. Use the **New** function to create an event on the **Cash Desk** list.
1. Fill in the following fields as required:
    - Code, description
    - Type of Cash Desk document (receipt or withdrawal)
    - Account Type, Account No., Gen. Posting Type, Posting Group
    - Global Dimension Code 1 and Global Dimension Code 2 and, if applicable, whether it's an EET transaction
1. After setting up, close the list.

## Cash desk inventory

For the purpose of Cash Desk inventory in Business Central, you can find a report for generating the balance in the Cash Desk.

### Nominal value setup

First, you need to define which banknotes and coins you use in different currencies. It's necessary to define their nominal value for each currency.

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Currency Nominal Values**, and then choose the related link.
1. Create rows in the table using the combination of **Currency Code** and **Value**. Don't select a currency code to set the local currency of the system.
1. After defining the rows, you can close the page.

### Cash Desk Inventory Report

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Cash Desk Inventory**, and then choose the related link.
1. On the page before running the report, select input parameters such as:
    - **Cash Desk Code** for which the inventory is being taken.
    - **Date** when the inventory is carried out.
    - Option **Show Statistics** of the cash register in the report.
    - Next on the page, fill in the table **Nominal values**, that is, the number of individual banknotes and coins.
1. After setting the filters, use the **Preview and Close** button. You'll then see a page where you can see the status of the selected Cash Desk.

![Cash Desk Inventory](Media/cash-desk-inven.png)

## Payment application with customer and vendor ledger entries

The Apply Entries function can be run from the cash document lines to select customer or vendor entries to be reconciled. Similarly, functions are available for balancing with advance invoices.

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Cash Document**, and then choose the related link.
1. In the **Cash Document list**, create a cash document using the **New** button.
1. Fill in the fields on the cash receipt card:
    - Document type: Receipt or Withdrawal
    - Payment Purpose: list the text that specifies the purpose of the payment
    - Posting date, Document date and VAT
    - Possibly other fields as required
1. In the lines select:
    - Account Type: Customer or Vendor
    - Account number: Select Customer or Vendor number
    - In the functions above the line, use the **Apply Entries** function to find the entry you want to apply.
1. After selecting the entry, you can post the document.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)
