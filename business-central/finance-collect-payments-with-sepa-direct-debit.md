---
    title: SEPA Direct Debit in Business Central | Microsoft Docs
    description: You can collect payments directly from the customer’s bank account according to the SEPA format.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/21/2017
    ms.author: sgroespe

---
# Collecting Payments with SEPA Direct Debit
With your customer’s consent, you can collect payments directly from the customer’s bank account according to the SEPA format.  

 First, set up the export format of the bank file that instructs your bank to perform a direct debit. Then, set up the customer’s payment method. Last, set up the direct-debit mandate that reflects your agreement with the customer to collect their payments in a certain agreement period.  

 To instruct the bank to transfer the payment amount from the customer’s bank account to your company’s account, you create a direct-debit collection entry, which holds information about bank accounts, the affected sales invoices, and the direct-debit mandate. You then export an XML file that is based on the collection entry, which you send to your bank for processing. Any payments that could not be processed will be communicated to you by your bank, and you must then manually reject the direct debit-collection entries in question.  

 You can set up standard customer sales codes with the direct-debit payment method and mandate information. You can then use the **Create Standard Cust. Invoices** batch job to generate multiple sales invoices with the direct-debit information prefilled. This is can be done manually or automatically, according to the payment due date.  

 When payments are successfully processed, as communicated by your bank, you can post the payment receipts either directly from the **Direct Debit Collect. Entries** window or by moving the payment lines to the journal where you post payment receipts, such as the **Cash Receipt Journal** window. Alternatively, depending on your cash management process, you can wait and just apply the payments as a part of bank reconciliation.  

> [!NOTE]  
>  To collect payments using SEPA Direct Debit, the currency on the sales invoice must be EURO.  

 The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Prepare bank account formats, payment methods, and customer agreements for SEPA direct debit.|[Set Up SEPA Direct Debit](finance-how-to-set-up-sepa-direct-debit.md)|  
|Instruct your bank to transfer payment amounts from your customers’ bank accounts to your company’s account according to your setup of SEPA direct debit.|[Create SEPA Direct Debit Collection Entries and Export to a Bank File](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md)|  
|Set up standard customer sales codes for direct-debit invoices and generate sales invoices with direct-debit information when the invoices are due for payment.|[Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md)|  
|Post payments made as SEPA direct debits.|[Post SEPA Direct Debit Payment Receipts](finance-how-to-post-sepa-direct-debit-payment-receipts.md)|  

## See Also  
[Managing Receivables](receivables-manage-receivables.md)
