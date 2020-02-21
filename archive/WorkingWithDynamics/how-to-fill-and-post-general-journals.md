---
    title: How to Fill and Post General Journals | Microsoft Docs
    description: General journals are used to post to general ledger, bank, customer, vendor, and fixed assets accounts.
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
# Fill and Post General Journals
General journals are used to post to general ledger, bank, customer, vendor, and fixed assets accounts.  

 Payment journals are based on general journal batches and are used to post payments due on purchase documents to vendor accounts. The **Payment Journal** window is unique in that it can be used to export payment files for processing by electronic banks. For more information, see [Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../FullExperience/make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).  

### To fill in and post a general journal  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.  

2.  Fill in the fields on the first line manually.  

     Alternatively, if you process payments in the general journal, import a bank statement file to fill the lines automatically. For more information, see [Import Bank Statements](../FullExperience/how-to-import-bank-statements.md).  

3.  The **Gen. Posting Type**, **Gen. Bus. Posting Group**, and **Gen. Prod. Posting Group** fields, and the corresponding fields for the balancing account, are automatically filled in, but they can be changed if necessary.  

4.  If you process payments, apply payments to the related open sales or purchase documents where necessary. You can apply payments automatically or manually. For more information, see [Reconcile Payments Using Automatic Application](../FullExperience/how-to-reconcile-payments-using-automatic-application.md) or Applies-to ID.  

5.  After filling in the fields, post the journal. On the **Home** tab, in the **Process** group, choose **Post**.  

 When you post the journal, the lines are processed one-by-one to verify that the journal balances for each posting date. If the **Force Doc. Balance** field in the **General Journal Templates** window has been selected, the lines for each document type and document number are also verified. If you receive any error messages, correct the errors and post the journal again. After you have corrected all of the errors, the lines are posted one by one. For each account in the **Account No.** and **Bal. Account No.** fields, a general ledger entry is created, as well as a customer, vendor, or bank account ledger entry for each account of these types.  

### To fill in and post a payment journal  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  

2.  Fill payment journal lines, for example, by using the **Suggest Vendor Payments** function. For more information, see [Suggest Vendor Payments](../FullExperience/how-to-suggest-vendor-payments.md).  

    > [!NOTE]  
    >  You can select how posting dates are inserted on the journal lines. For more information, see [Insert Due Date as Posting Date on Payment Journal Lines](../FullExperience/how-to-insert-due-date-as-posting-date-on-payment-journal-lines.md).  

3.  When you have completed all payment journal lines, you can choose to export the payment lines to an electronic bank file. For more information, see [Export Payments to a Bank File](../FullExperience/how-to-export-payments-to-a-bank-file.md).  

4.  When you are ready post the payments, on the **Home** tab, in the **Process** group, choose **Post**.  

## See Also  
 [Enter VAT-liable Amounts Without VAT in General Journals](../FullExperience/how-to-enter-vat-liable-amounts-without-vat-in-general-journals.md)   
 [Fill In Recurring Journals](../FullExperience/how-to-fill-in-recurring-journals.md)   
 [Set Up Multiple Journal Batches](../FullExperience/how-to-set-up-multiple-journal-batches.md)   
 [Set Up Default Balancing Accounts](../FullExperience/how-to-set-up-default-balancing-accounts.md)   
 [Reconcile Liquid Accounts](../FullExperience/how-to-reconcile-liquid-accounts.md)   
 [Reverse Journal Postings and Undo Receipts/Shipments](../FullExperience/how-to-reverse-journal-postings.md)   
 [Import Bank Statements](../FullExperience/how-to-import-bank-statements.md)   
 [Reconcile Payments Using Automatic Application](../FullExperience/how-to-reconcile-payments-using-automatic-application.md)   
 Applies-to ID   
 [Suggest Vendor Payments](../FullExperience/how-to-suggest-vendor-payments.md)   
 [Insert Due Date as Posting Date on Payment Journal Lines](../FullExperience/how-to-insert-due-date-as-posting-date-on-payment-journal-lines.md)   
 [Export Payments to a Bank File](../FullExperience/how-to-export-payments-to-a-bank-file.md)   
 [Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../FullExperience/make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)
