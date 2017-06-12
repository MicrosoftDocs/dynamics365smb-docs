---
title: "How to: Correct Sales Invoices with Credit Memos"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales invoices, correcting"
  - "sales credit memos, correcting sales invoices"
  - "credit memos, correcting sales invoices"
ms.assetid: f826d09b-b1d9-4b86-b140-16e15e6af804
caps.latest.revision: 8
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
---
# How to: Correct Sales Invoices with Credit Memos
If you have posted an incorrect invoice, you can correct it by issuing a credit memo.  
  
### To correct a sales invoice with a credit memo  
  
1.  In the **Search** box, enter **Credit Memos**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a new credit memo.  
  
3.  Fill the lines with the posted sales entries that you want to correct.  
  
     You can fill the lines automatically with the following functions:  
  
    -   Use the **Copy Document** batch job to copy an existing document to the credit memo. It can be either a posted document or a document that is not yet posted.  
  
         This function only reverses cost exactly when exact cost reversing is required in the **Sales & Receivables Setup** window. For more information, see the [How to: Assign Exact Cost Reversing in Sales](../Finance/how-to-assign-exact-cost-reversing-in-sales.md).  
  
    -   Use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents to the new credit memo document.  
  
         This function always exactly reverses the costs from the posted document line, regardless of whether exact cost reversing is required in the **Sales & Receivables Setup** window.  
  
     When you use either of these functions, a link is created to the original item ledger entries in the **Appl.\-from Item Entry** field to ensure that the costs are copied from the original posted document. If the line has item tracking, the **Appl.\-from Item Entry** field is filled in on the item tracking line or lines instead of on the document line.  
  
4.  Post the credit memo.  
  
## See Also  
 [Correction of Incorrect Posted Documents](../Finance/correction-of-incorrect-posted-documents.md)   
 [How to: Assign Exact Cost Reversing in Sales](../Finance/how-to-assign-exact-cost-reversing-in-sales.md)   
 [Processing Sales Orders](../Sales/processing-sales-orders.md)   
 [Copy Sales Document](../Sales/-$-b_292-copy-sales-document-$-.md)   
 [Appl.\-from Item Entry](../Topic/\($%20T_37_5811%20Appl.-from%20Item%20Entry%20$\).md)   
 [Correction](../Topic/\($%20T_114_98%20Correction%20$\).md)