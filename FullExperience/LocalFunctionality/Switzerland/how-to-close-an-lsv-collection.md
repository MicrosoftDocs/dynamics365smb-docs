---
title: "How to: Close an LSV Collection"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "direct debit"
  - "LSV payments, reopening"
  - "LSV payments, closing"
ms.assetid: a4bd9b6b-8619-459d-b981-035cc520639e
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Close an LSV Collection
You must close Lastschrift Verfahren \(LSV\+\) collections to write LSV files that can be sent to the bank for payment collection. When you close a collection, the collection is complete, and the postings in the LSV journal are combined.  
  
 When the collection is complete, the current collection number is assigned in the LSV journal, based on the last collection. This LSV number is transferred to the customer entries for all outstanding invoices. The collection file can be reconstructed at any time using the LSV number. The **On Hold** field is also populated with **LSV** in the customer entries to avoid the duplication of open entries. For more information, see the **LSV Journal** table and the **Cust. Ledger Entry** table. You can also reopen a closed collection.  
  
### To close an LSV collection  
  
1.  In the **Search** box, enter **LSV Journal List**, and then choose the related link.  
  
2.  Select the required journal line, on the **Actions** tab, in the **Functions** group, select **Modify Posting Date**. This will modify the value in the **Credit Date** field by using the value suggested during the LSV collection.  
  
3.  In the **New Date** field, enter the new date.  
  
4.  On the **Actions** tab, in the **Functions** group, select **Close Collection**.  
  
    > [!NOTE]  
    >  The fields on the **Options** FastTab for the **LSV Close Collection** batch job cannot be modified, and correspond to the selected journal line.  
  
5.  Choose the **OK** button.  
  
     In the **LSV Journal List** window, the value in the **LSV Status** field is changed from **Edit** to **Released**. The journal lines can no longer be modified.  
  
### To reopen an LSV collection  
  
1.  In the **Search** box, enter **LSV Journal List**, and then choose the related link.  
  
2.  Select the required journal line for which you want to reopen the collection, on the **Actions** tab, in the **Functions** group, select **Reopen Collection**.  
  
    > [!NOTE]  
    >  You can only reopen the collection if you have not yet submitted the LSV\+ file to the bank.  
  
3.  Choose the **Yes** button to confirm the reopening of the collection.  
  
## See Also  
 [Swiss Electronic Payments Using LSV\+](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-lsv-.md)   
 [How to: Process an LSV Collection](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-process-an-lsv-collection.md)   
 [How to: Post LSV\+ Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-post-lsv-payments.md)   
 [How to: Export Payments Using LSV](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-export-payments-using-lsv.md)   
 [LSV Journal](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_3010832-lsv-journal-$-.md)   
 [LSV Journal Line](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_3010834-lsv-journal-line-$-.md)   
 [Cust. Ledger Entry](../Topic/\($%20T_21%20Cust.%20Ledger%20Entry%20$\).md)