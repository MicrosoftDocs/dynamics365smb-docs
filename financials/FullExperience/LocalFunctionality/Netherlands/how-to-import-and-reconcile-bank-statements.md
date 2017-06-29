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
# How to: Import and Reconcile Bank Statements
Banks provide electronic bank statements for all your financial interactions. You can import these statements into the bank or giro journals.  
  
 The import bank statement is supported by the following protocols:  
  
-   Rabobank mut.asc  
  
-   Rabobank vvmut.ac  
  
-   Rabobank ASCII  
  
-   SEPA CAMT  
  
 For more information, see Import Protocol.  
  
### To import and reconcile bank statements  
  
1.  In the **Search** box, enter **Import Bank Statement**, and then choose the related link.  
  
2.  In the **Import Protocol List** window, select the required import protocol, and then choose the **OK** button.  
  
3.  To reconcile the bank statements automatically when importing, on the **Options** FastTab, select the **Automatic Reconciliation** check box.  
  
    > [!NOTE]  
    >  This function does not work for bank statement files of type SEPA CAMT. Instead, use the **Match Automatically** action in the **Bank Acc. Reconciliation** window. For more information, see [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../FullExperience/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md).  
  
4.  Choose the **OK** button.  
  
5.  To import the file that contains the electronic bank statement, specify the file name and path, and then choose the **Open** button.  
  
     The electronic bank statement is imported into the bank or giro journals. For more information, see [Dutch Electronic Banking](../FullExperience/dutch-electronic-banking.md).  
  
## See Also  
 [Dutch Electronic Banking](../FullExperience/dutch-electronic-banking.md)   
 Import Protocol   
 Reconciliation Status Field   
 CBG Statement Line Table   
 Bank-Giro Journal Window   
 [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../FullExperience/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md)