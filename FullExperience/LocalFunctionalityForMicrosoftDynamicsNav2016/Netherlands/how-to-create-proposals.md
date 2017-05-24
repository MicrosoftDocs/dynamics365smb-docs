---
title: "How to: Create Proposals"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "proposals"
ms.assetid: 043ede9c-6b74-42d1-b482-3acda0de3225
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Create Proposals
Proposals can be generated manually or automatically based on either vendor or customer ledger entries.  
  
> [!IMPORTANT]  
>  To create a proposal, you must use the **\($ T\_288\_11000000 Owner Information $\)** field in the [\($ N\_425 Vendor Bank Account Card $\)](../Topic/\($%20N_425%20Vendor%20Bank%20Account%20Card%20$\).md) and [\($ N\_423 Customer Bank Account Card $\)](../Topic/\($%20N_423%20Customer%20Bank%20Account%20Card%20$\).md) windows.  
  
> [!NOTE]  
>  At any time and at any level, before processing a proposal, the transaction mode and bank account can be modified. At the lowest level on the relevant vendor or customer ledger entries.  
  
#### To create proposals manually  
  
1.  In the **Search** box, enter **\($ N\_11000000 Telebank \- Bank Overview $\)**, and then choose the related link.  
  
2.  Select the relevant bank account. On the **Actions** tab, in the **Telebank** group, choose **Proposal**.  
  
3.  At a minimum, you must fill in the **Account Type**, **Account No.**, **Transaction Mode**, **Bank Account No.**, and **Amount** fields.  
  
     [!INCLUDE[bp_fieldhelp]()]  
  
4.  If you want to view or adjust the proposal's detail lines, in the **Lines** part, in the toolbar, choose **Detail Information**. To return to the proposal, close the **Proposal Detail Line** window.  
  
#### To create proposals automatically from sales  
  
1.  Set up a card for the customer who sent the invoice with appropriate values for the **Currency Code**, **Transaction Mode**, and **Bank Account** fields.  
  
     [!INCLUDE[bp_fieldhelp]()]  
  
2.  Create a sales invoice or credit memo, enter the customer and relevant items and post the invoice. Check whether the **Currency Code**, **Transaction Mode**, and **Bank Account** fields of the invoice\/credit memo contain appropriate values. By default, they will be copied from the customer card.  
  
     [!INCLUDE[bp_fieldhelp]()]  
  
3.  In the **Search** box, enter **\($ N\_11000000 Telebank \- Bank Overview $\)**, and then choose the related link.  
  
4.  Select the relevant bank account. On the **Actions** tab, in the **Telebank** group, choose **Proposal**.  
  
5.  On the **Actions** tab, in the **Proposal** group, choose **Get Entries**.  
  
     You can use the [\($ B\_11000000 Get Proposal Entries Batch Job $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-b_11000000-get-proposal-entries-batch-job-$-.md) batch job to generate proposal lines based on relevant customer ledger entries.  
  
    > [!NOTE]  
    >  Only proposal lines will be created for ledger entries that have a transaction mode of account type **Customer** and a link to the active bank account.  
  
6.  If you want to view or adjust the proposal's detail lines, in the **Lines** part, in the toolbar, choose **Detail Information**. To return to the proposal, close the **Proposal Detail Line** window.  
  
#### To create proposals automatically from purchases  
  
1.  Set up a card for the vendor that sent the invoice with appropriate values for **Currency Code**, **Transaction Mode**, and **Bank Account** fields.  
  
     [!INCLUDE[bp_fieldhelp]()]  
  
2.  Create a purchase invoice or credit memo, enter the vendor and relevant items. Post the invoice. Check whether the **Currency Code**, **Transaction Mode**, and **Bank Account** fields of the invoice\/credit memo contain appropriate values. By default, they will be copied from the vendor card.  
  
     [!INCLUDE[bp_fieldhelp]()]  
  
3.  In the **Search** box, enter **\($ N\_11000000 Telebank \- Bank Overview $\)**, and then choose the related link.  
  
4.  Select the relevant bank account. On the **Actions** tab, in the **Telebank** group, choose **Proposal**.  
  
5.  On the **Actions** tab, in the **Proposal** group, choose **Get Entries**.  
  
     You can use the [\($ B\_11000000 Get Proposal Entries Batch Job $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-b_11000000-get-proposal-entries-batch-job-$-.md) batch job to generate proposal lines based on relevant vendor ledger entries.  
  
    > [!NOTE]  
    >  Only proposal lines will be created for ledger entries that have a transaction mode of account type **Vendor** and a link to the active bank account.  
  
6.  If you want to view or adjust the proposal's detail lines, in the **Lines** part, in the toolbar, choose **Detail Information**. To return to the proposal, close the **Proposal Detail Line** window.  
  
## See Also  
 [How to: Register New Customers](../../Sales/how-to-register-new-customers.md)   
 [How to: Invoice Sales](../../Finance/how-to-invoice-sales.md)   
 [Record Purchase Invoices](../../Finance/record-purchase-invoices.md)   
 [How to: Create and Export Payment History](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-and-export-payment-history.md)