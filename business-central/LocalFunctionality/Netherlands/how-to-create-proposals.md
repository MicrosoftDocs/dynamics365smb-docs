---
title: How to Create Proposals
description: Generate proposals manually or automatically based on either vendor or customer ledger entries.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: generate proposals, proposals, generate proposals manually, generate proposals electronically, customer ledger entries, vendor ledger entries, Dutch version, Netherlands
ms.date: 03/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create proposals

Proposals can be generated manually or automatically based on either vendor or customer ledger entries.  

> [!IMPORTANT]  
> To create a proposal, you must use the **Owner Information** field in the **Vendor Bank Account Card** and **Customer Bank Account Card** pages.  
> [!NOTE]  
> At any time and at any level, before processing a proposal, the transaction mode and bank account can be modified. At the lowest level on the relevant vendor or customer ledger entries.  

## Create proposals manually  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Telebank - Bank Overview**, and then choose the related link.  
1. Select the relevant bank account and then choose the **Proposal** action.  
1. At a minimum, you must fill in the **Account Type**, **Account No.**, **Transaction Mode**, **Bank Account No.**, and **Amount** fields.  
1. If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## Create proposals automatically from sales  

1. Set up a card for the customer who sent the invoice with appropriate values for the **Currency Code**, **Transaction Mode**, and **Bank Account** fields.
1. Create a sales invoice or credit memo, enter the customer and relevant items and post the invoice.
1. Check whether the **Currency Code**, **Transaction Mode**, and **Bank Account** fields of the invoice/credit memo contain appropriate values. By default, they're copied from the customer card.  
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Telebank - Bank Overview**, and then choose the related link.  
1. Select the relevant bank account, and then choose the **Proposal** action.  
1. Choose the **Get Entries** action.  

   You can use the Get Proposal Entries Batch Job to generate proposal lines based on relevant customer ledger entries.  

   > [!NOTE]  
   > Only proposal lines are created for ledger entries that have a transaction mode of account type **Customer** and a link to the active bank account.  

1. If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## Create proposals automatically from purchases  

1. Set up a card for the vendor that sent the invoice with appropriate values for **Currency Code**, **Transaction Mode**, and **Bank Account** fields.  
1. Create a purchase invoice or credit memo, enter the vendor and relevant items.
1. Post the invoice.
1. Check whether the **Currency Code**, **Transaction Mode**, and **Bank Account** fields of the invoice/credit memo contain appropriate values. By default, they're copied from the vendor card.  
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Telebank - Bank Overview**, and then choose the related link.  
1. Select the relevant bank account, and then choose the **Proposal** action.  
1. Choose the **Get Entries** action.  

   You can use the Get Proposal Entries Batch Job to generate proposal lines based on relevant vendor ledger entries.  

   > [!NOTE]  
   > Only proposal lines are created for ledger entries that have a transaction mode of account type **Vendor** and a link to the active bank account.  

1. If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## Related information

- [Register New Customers](../../sales-how-register-new-customers.md)
- [Invoice Sales](../../sales-how-invoice-sales.md)
- [Record Purchases](../../purchasing-how-record-purchases.md)
- [Create and Export Payment History](how-to-create-and-export-payment-history.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
