---
title: "How to: Import ESR Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "ESR payments, importing"
ms.assetid: 72f065d1-bd53-47c0-a7fa-792b96d722cd
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Import ESR Payments
After you receive payment from a customer, you receive a file that contains information about paid invoices. You can receive this file from your bank electronically, or by mail.  
  
 You can import the Einzahlungsschein mit Referenznummer \(ESR\) invoice data from the file, print the data by using the sales invoice ESR report or the sales ESR coupon report, and verify before posting. For more information, see [How to: Print ESR Invoices](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-print-esr-invoices.md).  
  
### To import ESR payments  
  
1.  In the **Search** box, enter **Cash Receipt Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch.  
  
    > [!NOTE]  
    >  The journal must be empty before you import the ESR file. You cannot import more than one ESR file into the same cash receipt journal.  
  
3.  On the **Home** tab, in the **Process** group, choose **Read ESR File**.  
  
    > [!NOTE]  
    >  If you have defined more than one ESR bank, a warning message displays instructing you to choose the relevant bank. For more information, see the ESR Setup table.  
  
4.  Choose the **Yes** button, and then choose the **OK** button.  
  
 The payments information is imported to the journal lines. The payments are automatically applied to the respective invoices according to unique ESR reference numbers.  
  
## See Also  
 [Swiss Electronic Payments Using ESR](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-esr.md)   
 [How to: Print ESR Invoices](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-print-esr-invoices.md)   
 ESR Setup   
 Cash Receipt Journal   
 Customer ESR Journal