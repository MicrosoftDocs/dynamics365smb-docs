---
title: "How to: Print Checks"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "checks, printing"
ms.assetid: 31a7658a-4da5-49e8-97a4-2209d460f02d
caps.latest.revision: 7
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Print Checks
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can use the print check option to manage check payments to vendors or refunds to customers. This option lets you generate electronic payments.  
  
 For more information about check layouts, see [How to: Define Check Layouts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-define-check-layouts.md).  
  
### To print checks  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Payment Journal** window, fill in the payment journal lines. Either enter the lines manually or on the **Navigate** tab, in the **Payments** groups, choose **Suggest Vendor Payments**. For more information, see [How to: Generate Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-generate-electronic-payments.md).  
  
3.  In the payment journal line, select the **Bank Payment Type**. Use the following table to determine the bank payment type that you want to use to manage check payments.  
  
    |[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |-------------------------------------|---------------------------------------|  
    |**\<Blank\>**|Select this option if you do not want to create a check. This is the default option.|  
    |**Computer Check**|Select this option if you want to print a check for the amount on the payment journal line. You must print the checks before you can post the journal lines. You can only select **Computer Check** if the **Bal. Account Type** or the **Account Type** is **Bank Account**.|  
    |**Manual Check**|Select this option if you have created a check manually and want to create a corresponding check ledger entry for this amount. By using this option, you cannot print checks from [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]. You can only select **Manual Check** if the **Bal. Account Type** or the **Account Type** is **Bank Account**.|  
    |**Electronic Payment**|Select this option if you want to export this payment, together with other payments, to a file and then transmit that file to your bank. This will allow your bank to electronically transfer the payments from your bank account to the payee's bank account. By using this option, you must export and then transmit the journal lines before you can post. You can only select **Electronic Payment** if the **Bal. Account Type** or the **Account Type** is **Bank Account**, **Vendor**, or **Customer**.|  
    |**Electronic Payment\-IAT**|Select this option to export electronic payments using the International ACH Transaction \(IAT\) file format. This file format is required if a payment transaction includes financial agencies outside the United States. By using this option, you must export and then transmit the journal lines before you can post. You can only select **Electronic Payment\-IAT** if the **Bal. Account Type** or the **Account Type** is **Bank Account**, **Vendor**, or **Customer**.|  
  
4.  Depending on the **Bank Payment Type** selection, do one the following:  
  
    -   If you selected **Computer Check**, to print checks, on the **Navigate** tab, in the **Payments** group, choose **Print Checks**. On the **Options** FastTab, select the bank account that matches the bank account on the lines of the payment journal.  
  
    -   If you selected **Electronic Payment** or **Electronic Payment\-IAT**, to print checks, on the **Navigate** tab, in the **Payments** group, select **Electronic Payments**, and then choose **Export**. You can also use this function to print the remittance advice.  
  
5.  After the checks have been printed successfully, you can post the payment journal.  
  
6.  In the **Payment Journal** window, on the **Actions** tab, in the **Posting** group, choose **Post** or choose **Post and Print**. For more information, see [Payment Journal](../../Finance/-$-n_256-payment-journal-$-.md).  
  
### To transfer payment information to the bank  
  
1.  If you selected a payment type of **Electronic Payment** or **Electronic Payment\-IAT**, in the **Payment Journal** window, on the **Navigate** tab, in the **Payments** group, select **Electronic Payments**, and then choose **Transmit**.  
  
2.  After the electronic payments have transmitted successfully, you can post the payment journal. On the **Actions** tab, in the **Posting** group, choose **Post** or choose **Post and Print**. For more information, see [Payment Journal](../../Finance/-$-n_256-payment-journal-$-.md).  
  
### To cancel printed checks  
  
1.  If you need to cancel the checks after they have been printed, in the **Payment Journal** window, on the **Navigate** tab, in the **Payments** group, choose **Void Check** or choose **Void All Checks**. This lets you void one check or void all checks.  
  
2.  After the journal lines have been printed, exported, transmitted, or posted, check ledger entries are created in the [Check Ledger Entry](assetId:///a1177877-5f92-4c69-8288-51ea0a031843) table.  
  
## See Also  
 [Electronic Payments for United States, Canada, and Mexico](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/electronic-payments-for-united-states-canada-and-mexico.md)   
 [Export Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10083-export-electronic-payments-$-.md)   
 [How to: Define Check Layouts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-define-check-layouts.md)   
 [How to: Generate Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-generate-electronic-payments.md)