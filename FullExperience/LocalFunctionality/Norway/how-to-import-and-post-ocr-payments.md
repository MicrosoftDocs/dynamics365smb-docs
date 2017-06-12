---
title: "How to: Import and Post OCR Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "OCR payments, importing"
  - "OCR payments, posting"
ms.assetid: 8d33b4db-a069-43c7-9a50-f3420df5aca4
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Import and Post OCR Payments
Before you can receive optical character recognition \(OCR\) payments, you must make the following preparations:  
  
-   Set up a cash receipt journal template to balance OCR transactions according to the document number, instead of the document type.  
  
-   Import and post the OCR payment files to a cash receipt journal.  
  
### To import OCR payments  
  
1.  In the **Search** box, enter **Cash Receipt Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select a journal batch.  
  
    > [!NOTE]  
    >  OCR payments can only be posted to a cash receipt journal that does not use a balance account in the **Bal. Account No.** field on the cash receipt journal line.  
  
3.  On the **Home** tab, in the **Process** group, choose **Import Payments**.  
  
4.  In the **OCR Payment\-BBS** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**File Name**|Enter the full path of the import file.|  
  
5.  Choose the **OK** button to import the payment file to the journal.  
  
### To post OCR payments  
  
1.  In the **Search** box, enter **Cash Receipt Journals**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Posting** group, choose **Post**.  
  
     The OCR payment files are posted to the cash receipt journal.  
  
## See Also  
 [Electronic Banking in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/electronic-banking-in-norway.md)   
 [How to: Set Up KID Numbers on Sales Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-kid-numbers-on-sales-documents.md)   
 [How to: Set Up OCR Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-ocr-payments.md)   
 [Cash Receipt Journal](../../Finance/-$-n_255-cash-receipt-journal-$-.md)   
 [How to: Fill and Post General Journals](../../Finance/how-to-fill-and-post-general-journals.md)   
 [How to: Print the OCR Journal \- Test Report](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-print-the-ocr-journal-test-report.md)