---
author: brentholtorf
ms.topic: include
ms.date: 02/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

> [!NOTE]
> New capabilities for creating bank deposits are available in Business Central 2022 release wave 1 for a lot of country/region versions. If you used Business Central in the United States, Canada, or Mexico before that release, you might be using the earlier capabilities. You can continue, but the new capabilities will replace the old ones in a future release. To start using the new features right away, your administrator can go to the **Feature Management** page and turn on **Feature Update: Standardized bank reconciliation and deposits**. For more information, see [Create Bank Deposits](../../../bank-create-bank-deposits.md).

You can make bank deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.  

The **Deposits** page specifies bank deposit information such as the bank account number, total deposit amount, deposit lines, posting date, document date, department code, currency code, and bank deposit notes. You can use the page to create new bank deposits, post deposits, print deposits, view deposit comments, or view a report that shows the deposit amount to reconcile.

The **Deposit** report displays customer and vendor deposits with the original deposit amount, the amount of the deposit that remains open, and the amount applied. The report also shows the total posted deposit amount to reconcile.

Bank deposit lines contain information about the individual deposited items, such as checks from customers. This information includes the document date and number, account type and number, and amount. The total of the amounts on the lines must add up to the total amount of the deposit.

After you fill in the deposit information and lines, you must post it in order to update the relevant ledgers, such as the bank ledger, general ledger, or customer ledger. Posted deposits are stored for future reference and can be viewed on the **Posted Deposits** page.

## Create a deposit

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Deposits**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **General** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|The unique identification number for the deposit.|  
    |**Bank Account No.**|The bank account number for the deposit.|  
    |**Total Deposit Amount**|The total deposit amount posted to the bank ledger.<br> <br/> You can post this deposit only if the sum of the deposit lines is equal to the value in this field.|  
    |**Posting Date**|The posting date for the deposit.|
    |**Document Date**|The deposit document date.| 

1. On the **Lines** FastTab, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|The account type.|  
    |**Account No.**|The unique identification account number that is associated with the selected account type, to which the entry is posted.|  
    |**Description**|The journal line entry description.|  
    |**Document Date**|The journal line entry document date.|  
    |**Document Type**|The journal line entry document type.|  
    |**Document No.**|The journal line entry document number.|  
    |**Credit Amount**|The total credit amount on the journal line.|  

1. Optionally, choose the **Dimensions** action, and then add dimensions on the **Dimension Set Entries** page.  
1. Choose the **Post** action.  

    > [!TIP]
    > To post a bank deposit as a single bank account ledger entry with the total sum of amounts in the bank deposit lines, turn on the **Post as Lump Sum** toggle on the bank deposit. To post lump sums for new bank deposits by default, on the **Sales & Receivables Setup** page, turn on the **Post Bank Deposits as Lump Sum** toggle.
    > [!NOTE]  
    > You can post a deposit only if the amounts in the **Total Deposit Lines** and **Total Deposit Amount** fields are equal.  

Next, you can use the **Deposit Test** and **Deposit** reports to reconcile your posted deposits with outstanding invoices and credit memos.  
