---
title: "How to: Transmit Electronic Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "transmitting, electronic payments"
  - "electronic payments, transmitting"
ms.assetid: 213be76f-0290-4fc8-baee-50da356a89f4
caps.latest.revision: 7
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Transmit Electronic Payments
After you have exported payment journal entries to a file using the Export Electronic Payments report, you can use the Void\-Transmit Elec. Payments process to transmit the electronic payments file to your bank for processing.  
  
### To transmit payments  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  On the **Navigate** FastTab, choose **Electronic Payments**, and then choose **Transmit** or **Void**.  
  
3.  In the **Void\/Transmit Elec. Payments** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10084\_N\_2\_1 Bank Account No. $\)**|Select the bank account for the electronic payment operation.|  
    |**\($ B\_10084\_N\_2\_3 E\-Pay Operation $\)**|Specifies if you want to transmit or void the electronic payment file. The **Transmit** option produces an electronic payment file to be transmitted to your bank for processing. The **Void** option voids the exported file. Confirm that the correct selection has been made before you process the electronic payment file.|  
  
4.  To transmit the payments, choose the **OK** button.  
  
     After transmitting the electronic payments, post the payment journal.  
  
    > [!NOTE]  
    >  If you want to void a check after the journal has been transmitted and posted, you must contact your bank. You can then void the individual pieces of remittance advice from the **Check Ledger Entries** table. For more information, see [How to: Void Posted Checks](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-void-posted-checks.md).  
  
## See Also  
 [Electronic Payments for United States, Canada, and Mexico](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/electronic-payments-for-united-states-canada-and-mexico.md)   
 [How to: Set Up Electronic Payments for Bank Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-electronic-payments-for-bank-accounts.md)   
 [How to: Void Posted Checks](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-void-posted-checks.md)   
 Export Electronic Payments   
 Void\-Transmit Elec. Payments   
 [How to: Export Electronic Payments\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-export-electronic-payments-duplicate.md)   
 [How to: Generate Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-generate-electronic-payments.md)