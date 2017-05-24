---
title: "How to: Export Remittance Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "remittance, exporting payments"
ms.assetid: 507327c8-fb2e-49fc-8575-346dcf1d0e2a
caps.latest.revision: 7
ms.author: "sgroespe"
translation.priority.ht: 
  - "nb-no"
---
# How to: Export Remittance Payments
You can use the export remittance payments process to export the payments file to your computer. You can then transfer the remittance payments to the bank.  
  
> [!IMPORTANT]  
>  Before you can export a remittance payment, you must select a payment format in the **\($ T\_270\_1210 Payment Export Format $\)** field in the **\($ N\_370 Bank Account Card $\)** window.  
  
 You export payments to a bank file by choosing the **Export Payments** button in the **\($ N\_256 Payment Journal $\)** window. The process may be different, depending on the export format that you select:  
  
-   Payments using the SEPA payment standard are directly exported to a file when you choose the **Export Payments** button. For more information, see [How to: Export Payments to a Bank File](../../BusinessFunctionality/DataExchange/how-to-export-payments-to-a-bank-file.md).  
  
-   Payments using local payment standards, such as **Telepay**, are exported with either the **\($ B\_15000050 Remittance \- export \(bank\) $\)** or the **\($ B\_15000060 Remittance \- export \(BBS\) $\)** report, which automatically opens when you choose the **Export Payments** button.  
  
 The procedure for exporting payments using the **Remittance – Export** batch job is described in this topic.  
  
### To export remittance payments using the Remittance \- Export batch jobs  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  Prepare to export the payments from the journal. For more information, see [How to: Export Payments to a Bank File](../../BusinessFunctionality/DataExchange/how-to-export-payments-to-a-bank-file.md).  
  
3.  On the **Home** tab, in the **Bank** group, choose **Export Payments**.  
  
4.  In the report window that opens, choose the **Options** FastTab, and fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_15000050\_F\_1\_13 Remittance agreement code $\)**|Specify the code for the agreement.|  
    |**\($ R\_15000050\_F\_1\_3 Operator $\)**|Specify the operator number.|  
    |**\($ R\_15000050\_F\_1\_5 Password $\)**|Specify the password for the payments.|  
    |**\($ R\_15000050\_F\_1\_9 Division $\)**|Specify the division that is paying remittance.|  
    |**\($ R\_15000050\_F\_1\_1 Current note $\)**|Specify a note for the payment.|  
    |**\($ R\_15000050\_F\_1\_8 Filename $\)**|Specify the name and directory of the payment file.|  
  
5.  Choose the **OK** button.  
  
     The payment information is exported to the file that is set up in the remittance agreement.  
  
     The payment journal is deleted and the transactions are transferred to the waiting journal.  
  
## See Also  
 [\($ B\_15000050 Remittance \- export \(bank\) $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-b_15000050-remittance-export-bank-$-.md)   
 [\($ B\_15000060 Remittance \- export \(BBS\) $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-b_15000060-remittance-export-bbs-$-.md)   
 [Electronic Payments to Vendors in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/electronic-payments-to-vendors-in-norway.md)   
 [How to: Set Up Remittance Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-remittance-agreements.md)   
 [How to: Create Remittance Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/recipient-reference-codes.md)   
 [How to: Create Remittance Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-suggestions.md)   
 [How to: Create Manual Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-manual-remittance-payments.md)   
 [How to: Set Up Payment Line Information](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-payment-line-information.md)   
 [How to: Test Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-test-remittance-payments.md)   
 [Types of Payment Returns Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/types-of-payment-returns-files.md)   
 [How to: Import Payment Return Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/remittance-errors.md)   
 [How to: View Remittance Error Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-cancel-payments.md)