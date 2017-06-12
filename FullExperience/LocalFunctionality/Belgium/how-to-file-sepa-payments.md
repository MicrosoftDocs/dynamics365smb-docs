---
title: "How to: File SEPA Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "SEPA, payments"
ms.assetid: d55a93cb-4308-42df-8ed5-870f3ef837d1
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: File SEPA Payments
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can use Single Euro Payments Area \(SEPA\) credit transfers to file SEPA payments with the bank.  
  
 SEPA unifies payment methods in participating European countries\/regions, which makes international payments as easy to process as domestic payments. European citizens and companies can make and receive payments in euros, whether within or across national borders, with the same basic conditions, rights, and obligations, regardless of location.  
  
 Before you can file a SEPA payment you must complete the following administration tasks:  
  
-   Set up a new export protocol. For more information, see [Export Protocol](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_2000005-export-protocol-$-.md).  
  
-   In the **Country\/Region** table, select the **SEPA Allowed** field for each country that belongs to the EEA zone.  
  
-   Verify that the **Currency Euro** field in the **General Ledger Setup** table corresponds with the currency in the payment lines.  
  
-   Verify that the vendor’s **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  
  
### To file a SEPA payment  
  
1.  In the **Search** box, enter **File SEPA Payments**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Specify the general journal template for the SEPA payment report.|  
    |**Journal Batch**|Specify the general journal batch for the SEPA payment report.|  
    |**Post General Journal Lines**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**Include Dimensions**|Enter the dimensions that you want to include in the SEPA payment report. The option is only available if the **Summarize Gen. Jnl. Lines** field in the **Electronic Banking Setup** window is selected.|  
    |**Execution Date**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**File Name**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [File SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-r_2000005-file-sepa-payments-$-.md)   
 [How to: Set Up Export Protocols](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-export-protocols.md)   
 [Export Protocol](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_2000005-export-protocol-$-.md)   
 [How to: File Non\-Euro SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-file-non-euro-sepa-payments.md)   
 [How to: Activate SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-activate-sepa-payments.md)