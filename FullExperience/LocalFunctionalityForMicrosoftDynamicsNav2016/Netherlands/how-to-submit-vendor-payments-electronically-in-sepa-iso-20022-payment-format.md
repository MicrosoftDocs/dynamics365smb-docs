---
title: "How to: Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "SEPA, submitting payments"
  - "vendor payments, submitting electronically"
ms.assetid: 128a86ad-23b6-49f9-a049-bb4d36091759
caps.latest.revision: 43
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can create and submit Single Euro Payments Area \(SEPA\) ISO 20022 vendor payments electronically.  
  
 Before you can create and submit SEPA vendor payments, you must enable SEPA payments. For more information, see [How to: Activate SEPA Payments\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-activate-sepa-payments-duplicate.md).  
  
### To submit vendor payments electronically in SEPA ISO 20022 payment format  
  
1.  In the **Search** box, enter **\($ N\_11000000 Telebank\-Bank Overview $\)**, and then choose the related link.  
  
2.  Select the relevant bank account, and then, on the **Navigate** tab, in the **Telebank** group, choose **Proposal**.  
  
3.  Select the relevant vendor bank account, and then, on the **Navigate** tab, in the **Proposal** group, choose **Get Entries**.  
  
4.  In the **\($ B\_11000000 Get Proposal Entries $\)** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Currency Date**|Specify the currency date.|  
    |**Pmt. Discount Date**|Specify the payment discount date.|  
  
5.  On the **Transaction Mode** FastTab, select the appropriate filters.  
  
6.  On the **Cust. Ledger Entry** FastTab, select the appropriate filters.  
  
7.  On the **Vendor Ledger Entry** FastTab, select the **Vendor No.** filter, and then select a vendor number.  
  
    > [!NOTE]  
    >  Select other appropriate filters if required.  
  
8.  Choose the **OK** button.  
  
     The proposal lines populate in the **\($ N\_11000001 Telebank Proposal $\)** window.  
  
## See Also  
 [How to: Activate SEPA Payments\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-activate-sepa-payments-duplicate.md)   
 [Single EURO Payments Area \(SEPA\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/single-euro-payments-area-sepa-.md)   
 [\($ N\_11000000 Telebank \- Bank Overview Window $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_11000000-telebank-bank-overview-window-$-.md)   
 [\($ N\_11000001 Telebank Proposal Window $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_11000001-telebank-proposal-window-$-.md)