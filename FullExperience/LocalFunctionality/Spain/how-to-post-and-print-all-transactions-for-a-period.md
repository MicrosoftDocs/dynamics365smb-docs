---
title: "How to: Post and Print All Transactions for a Period"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "transaction numbers, printing"
  - "transaction numbers, posting"
  - "posting, transactions for a period"
  - "transaction periods"
ms.assetid: 7f41b23d-d84e-409a-bfdc-08f4b85cdb24
caps.latest.revision: 24
ms.author: "edupont"
manager: "terryaus"
---
# How to: Post and Print All Transactions for a Period
Companies must submit their business transaction entries, grouped by transaction numbers, in an annual report to tax authorities. Every general ledger transaction must have a sequential number for the fiscal year. Posting transactions will assign transaction numbers to general ledger entries.  
  
### To post all transactions for a period  
  
1.  In the **Search** box, enter **\($ N\_39 General Journal $\)**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ N\_39\_39 Batch Name $\)**|Select the required general journal batch name.|  
    |**\($ T\_81\_10700 Transaction No. $\)**|Enter the transaction number. **Note:**  If the transaction is balanced, the next number displays automatically, and the related transaction details appear in the next row. If the transaction is not balanced, the same transaction number is displayed with related transaction details.|  
  
3.  On the **Home** tab, in the **Process** action group, choose **Post**, and then choose the **Yes** button to confirm posting.  
  
4.  Choose the **OK** button.  
  
     After the journal is posted, a final transaction number is assigned to entries in the journal. This number is a sequential, non\-gap number. Thus, for each fiscal year, all of the entries grouped by their transaction number are sorted by date in sequential order, with no gaps or blanks.  
  
### To print all transactions for a period  
  
1.  In the **Search** box, enter **\($ N\_116 G\/L Registers $\)**, and then choose the related link.  
  
2.  To set the **\($ T\_45\_10701 Period Trans. No. $\)** field for all of the general ledger entries in the period in a sequential order, on the **Actions** tab, in the **Functions** group, choose **Set Period Transaction No.**.  
  
3.  Select the appropriate filters.  
  
4.  Choose the **OK** button.  
  
    > [!NOTE]  
    >  All transactions are ordered by posting date, and a sequential number is assigned to each entry in the **\($ T\_45\_10701 Period Trans. No. $\)** field.  
  
5.  In the **\($ N\_116 G\/L Registers $\)** window, on the **Actions** tab, choose **Print Page**.  
  
## See Also  
 [Transaction Numbers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/transaction-numbers.md)