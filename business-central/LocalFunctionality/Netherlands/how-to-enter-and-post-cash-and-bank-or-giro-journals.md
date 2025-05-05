---
title: How to Enter and Post Cash and Bank or Giro Journals
description: Learn how to use the cash and bank journals to record transactions affecting cash and bank accounts via Cash Book and Bank Book.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: cash journals, bank journals, cash book, bank book, Dutch version, Netherlands, cash and bank accounts, telebanking
ms.date: 04/24/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Enter and post cash and bank/giro journals

The cash journal and the bank/giro journal help you post transactions into the system in an easier and more direct way than using the general journal.  

In conjunction with Telebanking, they allow you to import electronic bank statements into the **Bank/Giro Journal** page. The system can automatically reconcile these statements during the import process and determine whether a statement can be applied to open ledger entries for the relevant vendor/customer.

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can use the cash and bank journals to enter the transactions that affect the cash and bank accounts by using the **Cash Book** and **Bank Book** types.  

You can enter increases or decreases to the cash account on the **Cash Journal** page. For example, you can use this journal for paying out petty cash or receiving transfers from a different bank account.  

The **Bank/Giro Journal** page records the inflow or outflow of the cash to a specific bank account. This journal forms the basis for bank reconciliation. The layout of this journal resembles the paper bank statement, so you can transpose the required fields from the paper statement to the journal, or you can import an electronic bank statement file. The transactions can be customer payments or vendor payments.  

You can apply the payments from customers to the open invoices from accounts receivables. You can also enter general ledger transactions to capture miscellaneous amounts, such as bank charges or interest income. VAT codes can also be applied to these transaction lines. You can define a journal for every bank account.  

## Post cash journals  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Journal**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Cash Journal** page, on the **Lines** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Date**|The journal entry date.|  
    |**Document No.**|The document number for which journal entry is created.|  
    |**Account Type**|The account type to which the entry is to be posted.|  
    |**Account No.**|The account number to which the entry is to be posted.|  
    |**Description**|The description of the entry. This field automatically populates the description of the account number selected in the **Account No.** field.|  
    |**VAT Prod. Posting Group**|The VAT product posting group code used to post the entry. You can select a code in this field only if the **Account Type** is **G/L Account**. Learn more in VAT Product Posting Groups.|  
    |**Amount**|The total amount that the statement line consists of. You must enter the debit amount without a plus or minus sign and the credit amount with a minus sign.<br><br> If this amount includes the VAT amount, then select the **Amount incl. VAT** checkbox.|  

1. Choose the **Post** action.  

   > [!NOTE]  
   > If there's a difference between the opening balance and the closing balance, you must change the closing balance before posting the entry.  

   The entries are posted to the general ledger. Learn more in **General Ledger Entries**.  

## Post bank or giro journals  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank/Giro Journal**, and then choose the related link.  
1. Choose the **New** action.  
1. Select the relevant journal template, and then choose the **OK** button.  
1. On the **Bank/Giro Journal** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Opening Balance**|The current balance of the bank or giro account. It equals the closing balance of previously posted entries for the journal.|  
    |**Closing Balance**|The new closing balance of the journal.|  

1. On the **Lines** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Date**|The journal entry date.|  
    |**Account Type**|The account type to which the journal entry is to be posted.|  
    |**Account No.**|The account number to which the journal entry is to be posted.|  
    |**Identification**|The identification number that links the statement line to a payment history line.|  
    |**Description**|The description of the entry.|  
    |**VAT Prod. Posting Group**|The VAT product posting group code that is used when you post the entry on the statement line.|  
    |**Amount**|The total amount that the statement line consists of. You must enter the debit amount without a plus or minus sign and the credit amount with a minus sign.<br><br> If this amount includes the VAT amount, then select the **Amount incl. VAT** checkbox.|  

1. Choose the **Post** action.  

> [!NOTE]  
> If there's a difference between the opening balance and the closing balance, you must change the closing balance before posting the entry.  

The entries are posted to the general ledger. Learn more in [General Ledger Entries](../../finance-general-ledger.md).  

## Related information

- [Print the Test Reports for Cash and Bank or Giro Journals](how-to-print-the-test-reports-for-cash-and-bank-or-giro-journals.md)  
- [Telebanking](telebanking.md)   
- [Enter and Post Cash and Bank or Giro Journals](how-to-enter-and-post-cash-and-bank-or-giro-journals.md)  
- [Applying Payments Automatically and Reconciling Bank Accounts](../../receivables-apply-payments-auto-reconcile-bank-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
