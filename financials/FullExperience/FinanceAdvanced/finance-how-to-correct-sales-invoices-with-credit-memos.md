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
# How to: Correct Sales Invoices with Credit Memos
If you have posted an incorrect invoice, you can correct it by issuing a credit memo.  
  
### To correct a sales invoice with a credit memo  
  
1.  In the **Search** box, enter **Credit Memos**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a new credit memo.  
  
3.  Fill the lines with the posted sales entries that you want to correct.  
  
     You can fill the lines automatically with the following functions:  
  
    -   Use the **Copy Document** batch job to copy an existing document to the credit memo. It can be either a posted document or a document that is not yet posted.  
  
         This function only reverses cost exactly when exact cost reversing is required in the **\($ N\_459 Sales & Receivables Setup $\)** window. For more information, see the [How to: Assign Exact Cost Reversing in Sales](../how-to-assign-exact-cost-reversing-in-sales.md).  
  
    -   Use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents to the new credit memo document.  
  
         This function always exactly reverses the costs from the posted document line, regardless of whether exact cost reversing is required in the **\($ N\_459 Sales & Receivables Setup $\)** window.  
  
     When you use either of these functions, a link is created to the original item ledger entries in the **Appl.-from Item Entry** field to ensure that the costs are copied from the original posted document. If the line has item tracking, the **Appl.-from Item Entry** field is filled in on the item tracking line or lines instead of on the document line.  
  
4.  Post the credit memo.  
  
## See Also  
 [Correction of Incorrect Posted Documents](../correction-of-incorrect-posted-documents.md)   
 [How to: Assign Exact Cost Reversing in Sales](../how-to-assign-exact-cost-reversing-in-sales.md)   
 [Processing Sales Orders](../processing-sales-orders.md)   
 Copy Sales Document   
 Appl.-from Item Entry   
 Correction