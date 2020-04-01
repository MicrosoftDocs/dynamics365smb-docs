---
    title: How to Post and Print All Transactions for a Period
    description: Companies must submit their business transaction entries, grouped by transaction numbers, in an annual report to tax authorities.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Post and Print All Transactions for a Period
Companies must submit their business transaction entries, grouped by transaction numbers, in an annual report to tax authorities. Every general ledger transaction must have a sequential number for the fiscal year. Posting transactions will assign transaction numbers to general ledger entries.  

## To post all transactions for a period  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|Select the required general journal batch name.|  
    |**Transaction No.**|Enter the transaction number. **Note:**  If the transaction is balanced, the next number displays automatically, and the related transaction details appear in the next row. If the transaction is not balanced, the same transaction number is displayed with related transaction details.|  

3.  Choose the **Post** action, and then choose the **Yes** button to confirm posting.  
4.  Choose the **OK** button.  

    After the journal is posted, a final transaction number is assigned to entries in the journal. This number is a sequential, non-gap number. Thus, for each fiscal year, all of the entries grouped by their transaction number are sorted by date in sequential order, with no gaps or blanks.  

## To print all transactions for a period  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Registers**, and then choose the related link.  
2.  To set the **Period Trans. No.** field for all of the general ledger entries in the period in a sequential order, choose the **Set Period Transaction No.** action.  
3.  Select the appropriate filters.  
4.  Choose the **OK** button.  

    > [!NOTE]  
    >  All transactions are ordered by posting date, and a sequential number is assigned to each entry in the **Period Trans. No.** field.  

5.  On the **G/L Registers** page, choose the **Print Page** action.  

## See Also  
 [Transaction Numbers](transaction-numbers.md)
