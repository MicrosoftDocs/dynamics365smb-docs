---
title: "How to: Export Payments Using EZAG"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "DTA payments, EZAG files"
  - "EZAG files"
  - "DTA payments, exporting"
ms.assetid: b10a032a-114d-4a7b-8288-eb67ebf30531
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Export Payments Using EZAG
You can generate a file for electronic payment using the Elektronischer Zahlungsauftrag \(EZAG\) method, and export it for the bank to use for the payments.  
  
### To export payments using EZAG  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the journal batch name.  
  
3.  On the **Home** tab, in the **Process** group, choose **Generate EZAG File**.  
  
4.  In the **EZAG File** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_3010542\_F\_1\_5 Debit to bank $\)**|Specify the code of the bank to be charged.|  
    |**\($ B\_3010542\_F\_1\_1 Combined payment for vendor $\)**|Specify if the payment lines that have the same vendor, currency, bank, and debit bank in the generated EZAG file will be combined.|  
    |**\($ B\_3010542\_F\_1\_1150000 Shipment with disk $\)**|Specify if the EZAG file will be saved to a disk so that you can deliver it to the bank.|  
  
5.  Choose the **OK** button. The EZAG file is generated.  
  
## See Also  
 [Swiss Electronic Payments Using DTA](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-dta.md)   
 [How to: Suggest DTA Payment for Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-suggest-dta-payment-for-vendors.md)   
 [How to: Verify a List of Vendors for DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-verify-a-list-of-vendors-for-dta-payments.md)   
 [How to: Submit DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-submit-dta-payments.md)   
 DTA Setup   
 Payment Journal