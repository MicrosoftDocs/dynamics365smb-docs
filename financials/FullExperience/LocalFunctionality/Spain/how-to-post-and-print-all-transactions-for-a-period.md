---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Post and Print All Transactions for a Period
Companies must submit their business transaction entries, grouped by transaction numbers, in an annual report to tax authorities. Every general ledger transaction must have a sequential number for the fiscal year. Posting transactions will assign transaction numbers to general ledger entries.  
  
### To post all transactions for a period  
  
1.  In the **Search** box, enter **General Journal**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|Select the required general journal batch name.|  
    |**Transaction No.**|Enter the transaction number. **Note:**  If the transaction is balanced, the next number displays automatically, and the related transaction details appear in the next row. If the transaction is not balanced, the same transaction number is displayed with related transaction details.|  
  
3.  On the **Home** tab, in the **Process** action group, choose **Post**, and then choose the **Yes** button to confirm posting.  
  
4.  Choose the **OK** button.  
  
     After the journal is posted, a final transaction number is assigned to entries in the journal. This number is a sequential, non\-gap number. Thus, for each fiscal year, all of the entries grouped by their transaction number are sorted by date in sequential order, with no gaps or blanks.  
  
### To print all transactions for a period  
  
1.  In the **Search** box, enter **G\/L Registers**, and then choose the related link.  
  
2.  To set the **Period Trans. No.** field for all of the general ledger entries in the period in a sequential order, on the **Actions** tab, in the **Functions** group, choose **Set Period Transaction No.**.  
  
3.  Select the appropriate filters.  
  
4.  Choose the **OK** button.  
  
    > [!NOTE]  
    >  All transactions are ordered by posting date, and a sequential number is assigned to each entry in the **Period Trans. No.** field.  
  
5.  In the **G\/L Registers** window, on the **Actions** tab, choose **Print Page**.  
  
## See Also  
 [Transaction Numbers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/transaction-numbers.md)