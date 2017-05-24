---
title: "How to: Post LSV+ Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "direct debit"
  - "LSV payments, posting"
ms.assetid: bbac585f-c5bf-4d35-a5b3-23e5f5f030bf
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Post LSV+ Payments
You can post payments after you have received Lastschrift Verfahren \(LSV\+\) payment advice from the bank.  
  
### To post LSV\+ payments  
  
1.  In the **Search** box, enter **Cash Receipt Journals**, and then choose the related link.  
  
2.  Select the required journal, and on the **Home** tab, in the **Process** group, choose **Edit Journal**.  
  
    > [!NOTE]  
    >  You can select the journal batch for LSV where the balance account you want to address is defined. You cannot import more than one LSV journal line into the same cash receipt journal. For more information, see the [\($ N\_255 Cash Receipt Journal $\)](../../Finance/-$-n_255-cash-receipt-journal-$-.md) window.  
  
3.  On the **Home** tab, in the **Process** group, choose **Get From LSV Journal**.  
  
4.  In the **LSV Journal List** window, select the LSV journal line that you want to import to the cash receipt journal.  
  
    > [!NOTE]  
    >  You can only import journal lines where the **\($ T\_3010832\_5 LSV Status $\)** field is set to **File Created**.  
  
5.  Choose the **OK** button.  
  
     The LSV journal line is imported into the cash receipt journal. The value in the **\($ T\_3010832\_5 LSV Status $\)** field in the **\($ N\_3010832 LSV Journal List $\)** window changes from **File Created** to **Finished**.  
  
     You can check the imported payments, and compare them with your bank payment advice in the **\($ N\_255 Cash Receipt Journal $\)** window. You can also delete the payment lines that could not be processed by the bank, and for which you must follow up with the customer manually.  
  
6.  On the **Home** tab, in the **Posting** group, choose **Post**.  
  
## See Also  
 [Swiss Electronic Payments Using LSV\+](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-lsv-.md)   
 [How to: Process an LSV Collection](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-process-an-lsv-collection.md)   
 [How to: Close an LSV Collection](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-close-an-lsv-collection.md)   
 [How to: Export Payments Using LSV](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-export-payments-using-lsv.md)   
 [\($ N\_255 Cash Receipt Journal $\)](../../Finance/-$-n_255-cash-receipt-journal-$-.md)   
 [\($ T\_3010832 LSV Journal $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_3010832-lsv-journal-$-.md)   
 [\($ T\_3010834 LSV Journal Line $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_3010834-lsv-journal-line-$-.md)