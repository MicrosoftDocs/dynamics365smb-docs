---
title: Create Dutch Telebanking Payment Proposals
description: Create Dutch telebanking payment proposals manually or from posted customer and vendor ledger entries, then review the payment details before processing.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: generate proposals, proposals, generate proposals manually, generate proposals electronically, customer ledger entries, vendor ledger entries, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create proposals

Proposals can be generated manually or automatically based on either vendor or customer ledger entries.  

> [!IMPORTANT]  
> Complete the account holder details on the **Account Holder** FastTab of the relevant **Vendor Bank Account Card** or **Customer Bank Account Card** page. Proposal processing checks the account holder name and city, along with the bank details required by the export protocol.

> [!NOTE]  
> Review the transaction mode and bank account before you process the proposal. You can change them on the proposal lines.

## Create proposals manually  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Telebank - Bank Overview**, and then choose the related link.  
1. Select the relevant bank account and then choose the **Proposal** action.  
1. At a minimum, you must fill in the **Account Type**, **Account No.**, **Transaction Mode**, **Bank Account No.**, and **Amount** fields.  
1. If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## Create proposals automatically from sales  

1. Set up a card for the customer who will receive the invoice with appropriate values for the **Currency Code**, **Transaction Mode Code**, and **Preferred Bank Account Code** fields.
1. Create a sales invoice or credit memo and enter the customer and relevant items.
1. Before posting, check the **Currency Code**, **Transaction Mode Code**, and **Bank Account Code** fields. By default, these values are copied from the customer card. Then post the document.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Telebank - Bank Overview**, and then choose the related link.  
1. Select the relevant bank account, and then choose the **Proposal** action.  
1. Choose the **Get Entries** action.  

   You can use the Get Proposal Entries Batch Job to generate proposal lines based on relevant customer ledger entries.  

   > [!NOTE]  
   > Only proposal lines are created for ledger entries that have a transaction mode of account type **Customer** and a link to the active bank account.  

1. If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## Create proposals automatically from purchases  

1. Set up a card for the vendor that sent the invoice with appropriate values for **Currency Code**, **Transaction Mode Code**, and **Preferred Bank Account Code**.
1. Create a purchase invoice or credit memo, enter the vendor and relevant items.
1. Before posting, check the **Currency Code**, **Transaction Mode Code**, and **Bank Account Code** fields. By default, these values are copied from the vendor card. Then post the document.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Telebank - Bank Overview**, and then choose the related link.  
1. Select the relevant bank account, and then choose the **Proposal** action.  
1. Choose the **Get Entries** action.  

   You can use the Get Proposal Entries Batch Job to generate proposal lines based on relevant vendor ledger entries.  

   > [!NOTE]  
   > Only proposal lines are created for ledger entries that have a transaction mode of account type **Vendor** and a link to the active bank account.  

1. If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

The **Get Proposal Entries** report selects open ledger entries that aren't on hold. The transaction mode must be included in payment proposals. Due dates, payment discount dates, and your filters also affect which entries are selected. Entries for blocked or privacy-blocked vendors are skipped.

## Related information

- [Register New Customers](../../sales-how-register-new-customers.md)
- [Invoice Sales](../../sales-how-invoice-sales.md)
- [Record Purchases](../../purchasing-how-record-purchases.md)
- [Create and Export Payment History](how-to-create-and-export-payment-history.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
