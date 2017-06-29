---
title: "How to: Set Up Customer Prepayments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "invoicing, prepayments"
  - "prepayments, creating an invoice"
  - "prepayments, setting up"
  - "advance payments"
ms.assetid: 55dd614a-b0be-41c6-9c17-eda1410d5c56
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Set Up Customer Prepayments
Prepayments are advance payments on sales orders that are received, invoiced, and posted before the final invoice is issued. For example, you may require a deposit before you manufacture and ship an item to a customer. Prepayments let you invoice and collect advance payments from customers and post the payments against the correct invoices and accounts.  
  
### To set up customer prepayments  
  
1.  In the Search box, enter **\($ N\_459 Sales & Receivables Setup $\)**, and then choose the related link.  
  
2.  On the **Numbering** FastTab, verify that the number series for the **Posted Prepmt. Inv. Nos.** is the same as the **Posted Invoice Nos.**. Also verify that the number series for the **Posted Prepmt. Cr. Memo Nos.** is the same as the **Posted Credit Memo Nos.**.  
  
3.  On the **Prepayment** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Use Prepayment Account**|Select to post prepayments using the subaccount specified in the **Prepayment Account** field in the **Customer Posting Groups** window.|  
    |**Create Prepayment Invoice**|Select to create an invoice for the prepayment. If this field is not selected, an invoice for the prepayment will not be created.|  
    |**Posted Prepayment Nos.**|Enter the code of the number series that you want to use for prepayment invoices.|  
    |**Posted PD Doc. Nos.**|Enter the code of the number series that you want to use for prepayment documents.|  
    |**PD Doc. Nos. Type**|Select if you want to use a number series or symbol to identify prepayment documents.|  
    |**Symbol for PD Doc.**|Enter a symbol to be printed on prepayment documents.|  
    |**PD Gains Condition Dim Value**|Enter the code for the dimension that is used to generate conditional prepayment gains.|  
    |**PD Losses Condition Dim Value**|Enter the code for the dimension that is used to generate conditional prepayment losses.|  
    |**PD Gains Kind Dim Value**|Enter the code for the dimension that is used to generate payment in kind prepayment gains.|  
    |**PD Losses Kind Dim Value**|Enter the code for the dimension that is used to generate payment in kind prepayment gains.|  
  
4.  Open the **Customer Posting Groups** window.  
  
5.  In the **Prepayment Account** field, specify the general ledger accounts that you want to use for posting customer prepayments.  
  
6.  Choose **Close** to close the window and save your entries.  
  
 You can now invoice and collect advance payments from customers and post the payments to the correct invoices and accounts.  
  
## See Also  
 [Walkthrough: Setting Up and Invoicing Sales Prepayments](../../GettingStarted/walkthrough-setting-up-and-invoicing-sales-prepayments.md)   
 [Invoice Prepayments](../../Finance/invoice-prepayments.md)   
 [Set Up Prepayments](../../Finance/set-up-prepayments.md)   
 [How to: Correct Prepayments](../../Finance/how-to-correct-prepayments.md)