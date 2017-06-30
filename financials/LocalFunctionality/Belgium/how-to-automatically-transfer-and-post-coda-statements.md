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
# How to: Automatically Transfer and Post CODA Statements
After you have applied and processed all CODA statement lines, you can transfer the CODA statement lines to a financial journal.  
  
 After transferring the statement lines, you can post the lines in a corresponding general journal. If no such general journal exists, you cannot transfer the lines. You can create a journal to handle CODA statements. For more information, see [How to: Create Financial Journals](how-to-create-financial-journals.md).  
  
 Alternatively, you can manually transfer and post CODA statements. For information, see [How to: Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md).  
  
### To automatically transfer statement lines  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank account, and on the **Home** tab, in the **Process** group, choose **CODA Statements**.  
  
3.  Select the CODA statement, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Transfer to General Ledger**.  
  
5.  Choose the **Yes** button.  
  
     The batch job will now transfer the CODA statement lines to the financial journal.  
  
 After transferring the statement lines to the journal, you can post the statement lines in the corresponding financial journal.  
  
## See Also  
 [CODA Bank Statements](coda-bank-statements.md)   
 [How to: Import CODA Statements](how-to-import-coda-statements.md)   
 [How to: Apply CODA Statements](how-to-apply-coda-statements.md)   
 [How to: Create Financial Journals](how-to-create-financial-journals.md)   
 [How to: Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md)