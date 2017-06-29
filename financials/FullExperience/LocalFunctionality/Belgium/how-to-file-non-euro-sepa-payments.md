---
title: "How to: File Non-Euro SEPA Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "SEPA, non-euro payments"
ms.assetid: 6aed5ee3-d7e8-4aba-859a-c2e0bc14d1e2
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: File Non-Euro SEPA Payments
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can file non\-euro SEPA payments with the bank. This is useful when you make payments to other countries that do not use SEPA and for currencies other than the euro.  
  
 Before you can file a non\-euro SEPA payment you must complete the following administration tasks:  
  
-   Set up a new export protocol for a non\-euro SEPA. For more information, see [\($ T\_2000005 Export Protocol $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_2000005-export-protocol-$-.md).  
  
-   In the **\($ T\_9 Country\/Region $\)** table, clear the **\($ T\_9\_2000005 SEPA Allowed $\)** field for each country that belongs to the EEA zone.  
  
-   Verify that the **\($ T\_98\_2000000 Currency Euro $\)** field in the **\($ T\_98 General Ledger Setup $\)** table is not in euro currency.  
  
-   Verify that the vendor’s **\($ T\_23\_288 Preferred Bank Account $\)** field in the **\($ T\_23 Vendor $\)** table contains the IBAN and SWIFT code.  
  
### To file a non\-euro SEPA payment  
  
1.  In the **Search** box, enter **File Non Euro SEPA Payments**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_2000006\_N\_2\_1 Journal Template Name $\)**|Specify the general journal template for the non\-euro SEPA payment report.|  
    |**\($ B\_2000006\_N\_2\_7 Journal Batch $\)**|Specify the general journal batch for the non\-euro SEPA payment report.|  
    |**\($ B\_2000006\_N\_2\_3 Post General Journal Lines $\)**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**\($ B\_2000006\_N\_2\_13 Include Dimensions $\)**|Enter the dimensions that you want to include in the non\-euro SEPA payment report. The option is only available if the **\($ T\_11306\_2 Summarize Gen. Jnl. Lines $\)** field in the **\($ N\_11308 Electronic Banking Setup $\)** window is selected.|  
    |**\($ B\_2000006\_N\_2\_5 Execution Date $\)**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**\($ B\_2000006\_N\_2\_1 File Name $\)**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [\($ B\_2000006 File Non Euro SEPA Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-b_2000006-file-non-euro-sepa-payments-$-.md)   
 [\($ R\_2000005 File SEPA Payments $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-r_2000005-file-sepa-payments-$-.md)   
 [How to: File SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-file-sepa-payments.md)   
 [How to: Activate SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-activate-sepa-payments.md)   
 [SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/sepa-payments.md)