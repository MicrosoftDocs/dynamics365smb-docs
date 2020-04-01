---
    title: How to Automatically Transfer and Post CODA Statements
    description: After you have applied and processed all CODA statement lines, you can transfer the CODA statement lines to a financial journal.

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
# Automatically Transfer and Post CODA Statements
After you have applied and processed all CODA statement lines, you can transfer the CODA statement lines to a financial journal.  

After transferring the statement lines, you can post the lines in a corresponding general journal. If no such general journal exists, you cannot transfer the lines. You can create a journal to handle CODA statements. For more information, see [Create Financial Journals](how-to-create-financial-journals.md).  

Alternatively, you can manually transfer and post CODA statements. For information, see [Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md).  

## To automatically transfer statement lines  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.  
2.  Select the bank account, and then choose the **CODA Statements** action.  
3.  Select the CODA statement, and then choose the **Edit** action.  
4.  Choose the **Transfer to General Ledger** action.  
5.  Choose the **Yes** button.  

The batch job will now transfer the CODA statement lines to the financial journal.  

After transferring the statement lines to the journal, you can post the statement lines in the corresponding financial journal.  

## See Also  
 [CODA Bank Statements](coda-bank-statements.md)   
 [Import CODA Statements](how-to-import-coda-statements.md)   
 [Apply CODA Statements](how-to-apply-coda-statements.md)   
 [Create Financial Journals](how-to-create-financial-journals.md)   
 [Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md)
