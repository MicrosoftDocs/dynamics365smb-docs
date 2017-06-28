---
title: "How to: Set Up OCR Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "OCR payments, setting up"
ms.assetid: f6c4e38a-cf68-470b-b32a-a931efeefeca
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Set Up OCR Payments
You can process electronic payments from customers according to a predefined payment ID. This is often referred to as an optical character recognition \(OCR\) payment. The payment ID is used with electronic payment transactions. Customers can refer to this ID when they make payments. The payment ID is also used to identify imported payment transactions and automatically apply imported payment data.  
  
### To set up OCR payments  
  
1.  In the **Search** box, enter **OCR Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_15000100\_2 Format $\)**|Select an OCR payment file format. Formats include **BBS** and **Data Dialog**.|  
    |**\($ T\_15000100\_10 FileName $\)**|Enter the full path of the OCR payment file.|  
    |**\($ T\_15000100\_11 Delete Return File $\)**|Select to rename the file after import and prevent the file from being imported more than one time.|  
  
3.  On the **Gen. Ledger** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_15000100\_20 Bal. Account Type $\)**|Select a balance account type. Balance account types include **Gen. Ledg. Account** and **Bank Account**.|  
    |**\($ T\_15000100\_21 Bal. Account No. $\)**|Select a balance account number.|  
    |**\($ T\_15000100\_24 Max. Divergence $\)**|Enter a maximum divergence value. If the divergence on a payment is less than or equal to the value entered, the divergence amount is automatically posted. Otherwise, the divergence is not automatically posted. In both situations, a warning is displayed in the cash receipt journal when importing OCR Giro payments.|  
    |**\($ T\_15000100\_25 Divergence Account No. $\)**|Enter the divergence account number that will receive posting.|  
    |**\($ T\_15000100\_22 Journal Template Name $\)**|Select the name of the journal template that should receive the imported OCR Giro payments.|  
    |**\($ T\_15000100\_23 Journal Name $\)**|Select the name of the journal that should receive the imported OCR Giro payments.<br /><br /> If the **\($ T\_15000100\_22 Journal Template Name $\)** and **\($ T\_15000100\_23 Journal Name $\)** fields are blank, you can import OCR Giro payments in any journal. Otherwise, you must import OCR Giro payments in the journal that is specified.|  
  
4.  Choose the **OK** button.  
  
> [!NOTE]  
>  OCR payments can only be posted to cash receipt journals when the **\($ T\_80\_18 Force Doc. Balance $\)** field has been cleared in the **\($ T\_80 Gen. Journal Template $\)** table. For more information, see [\($ T\_80 Gen. Journal Template $\)](assetId:///eb60bf94-fc5b-442c-acb8-91df074d20d2).  
  
## See Also  
 [Electronic Banking in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/electronic-banking-in-norway.md)   
 [How to: Set Up KID Numbers on Sales Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-kid-numbers-on-sales-documents.md)   
 [How to: Import and Post OCR Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-import-and-post-ocr-payments.md)   
 [How to: Print the OCR Journal \- Test Report](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-print-the-ocr-journal-test-report.md)   
 [\($ T\_80 Gen. Journal Template $\)](assetId:///eb60bf94-fc5b-442c-acb8-91df074d20d2)   
 [\($ T\_15000100 OCR Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-t_15000100-ocr-setup-$-.md)   
 [\($ N\_15000100 OCR Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-n_15000100-ocr-setup-$-.md)