---
title: Cash Desk Localization for Czech (Extension)  
description: Provides features for cash register operations in compliance with Czech legislation and best practices for Microsoft Dynamics 365 Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: Czech, CashDesk, Finance, CZ, Cash
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
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
- Reconciliation function provides a preview of journal movements and balances after posting, across all accounts (including G/L accounts and other types of accounts such as bank, vendor, and customer).
- Cash Desk inventory
- Output documents (receipt cash document, withdrawal cash document)
- Reports - Cash Desk Account Book, Cash Desk Book, Cash Desk Hand Over

The Cash Desk card contains basic information about the Cash Desk, such as number, currency, contact details, etc. It also contains settings for posting, definitions for controls and limits, and preset No. series for Cash Desk documents.

:::image type="content" source="media/cash-desk.png" alt-text="Screenshot of the cash desk card.":::

Cash Desk documents are either receipts or withdrawals and can be in different currencies depending on the Cash Desk. The documents also allow issuing, posting, and printing of output documents.

:::image type="content" source="media/cash-desk-document.png" alt-text="Screenshot of the cash desk document.":::

## Cash desk user setup

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Desks**, and then choose the related link.
1. Open the card of the cash desk you want to set up, and then, on the **Navigate** tab, choose **Cash Desk Users**.
1. The **Cash Desk Users** page opens. To create a new user, choose **New**.
1. In the row, select the **Cash Desk No.** that the user will be working on. Next, select the **User ID** and select whether the user has the option to **Create**, **Issue**, **Post**, or **Post EET Only**.
1. After setup, close the page.

## Set up No. series for receipts and withdrawals

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Desks**, and then choose the related link.
1. Open the card of the selected cash desk.
1. On the **Cash Desk Card**, you can find the **Numbering** FastTab.
1. In the **Cash Document Receipt Nos.** and **Cash Document Withdrawal Nos.** fields, select the number series you want to use.
1. After setting up, close the cash desk card.

## Set up cash desk events

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Desk Events Setup**, and then choose the related link.
1. Use **New** to create an event on the **Cash Desk Events Setup** list.
1. Fill in the following fields as required:
    - **Code** and **Description**
    - **Document Type** (receipt or withdrawal)
    - **Gen. Document Type**, **Account Type**, **Account No.**, and **Gen. Posting Type**
    - **VAT Bus. Posting Group** and **VAT Prod. Posting Group**
    - **Global Dimension 1 Code** and **Global Dimension 2 Code**, and, if applicable, whether it's an **EET Transaction**
1. After setting up, close the list.

## Cash desk inventory

For the purpose of Cash Desk inventory in Business Central, you can find a report for generating the balance in the Cash Desk.

### Nominal value setup

First, you need to define which banknotes and coins you use in different currencies. It's necessary to define their nominal value for each currency.

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currency Nominal Values**, and then choose the related link.
1. Create rows in the table using the combination of **Currency Code** and **Nominal Value**. Don't select a currency code to set the local currency of the system.
1. After defining the rows, you can close the page.

### Cash Desk Inventory report

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Desk Inventory**, and then choose the related link.
1. On the page before running the report, select input parameters such as:
    - **Cash Desk No.** for which the inventory is being taken.
    - **Date** when the inventory is carried out.
    - Option **Show Statistics** of the cash register in the report.
    - Next on the page, fill in the table **Nominal values**, that is, the number of individual banknotes and coins.
1. After setting the filters, use the **Preview and Close** button. You'll then see a page where you can see the status of the selected Cash Desk.

:::image type="content" source="media/cash-desk-inven.png" alt-text="Screenshot of the cash desk inventory.":::

## Payment application with customer and vendor ledger entries

The Apply Entries function can be run from the cash document lines to select customer or vendor entries to be reconciled. Similarly, functions are available for balancing with advance invoices.

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Documents**, and then choose the related link.
1. In the **Cash Documents** list, create a cash document by choosing **New**.
1. Fill in the fields on the cash receipt card:
    - **Document Type**: Receipt or Withdrawal
    - **Payment Purpose**: the text that specifies the purpose of the payment
    - **Posting Date**, **Document Date**, and **VAT Date**
    - Other fields as required
1. In the lines, select:
    - **Account Type**: Customer or Vendor
    - **Account No.**: the customer or vendor number
    - In the functions above the line, choose **Apply Entries** to find the entry you want to apply.
1. After selecting the entry, you can post the document.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)
