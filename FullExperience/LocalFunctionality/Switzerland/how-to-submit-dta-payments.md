---
title: "How to: Submit DTA Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "DTA payments, submitting"
ms.assetid: 01ece1ef-3094-43d8-9670-7a3709354113
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Submit DTA Payments
To submit DatenTrägerAustausch \(DTA\) payments to your bank for payment, you must do the following:  
  
-   Generate a DTA file for electronic payment after printing the payment advice.  
  
-   Print the DTA payment order.  
  
 Before you submit DTA payments, you must verify the list of vendors for DTA payment. For more information, see [How to: Verify a List of Vendors for DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-verify-a-list-of-vendors-for-dta-payments.md).  
  
 You can post the payment journal after the bank payments are complete. In the payment journal, you can have the DTA payments suggested based on posted invoices. The suggested payments contain vendor and external document number information, and can be modified. For more information, see [How to: Suggest DTA Payment for Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-suggest-dta-payment-for-vendors.md).  
  
### To generate a DTA file  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch.  
  
3.  Select the payment entry that you want to generate as a DTA file, and on the **Home** tab, in the **Process** group, select **Generate DTA File**.  
  
4.  In the **DTA File** batch job, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**DTA Bank for File**|Select the DTA bank code from which the information for the file name and backup copy is to be transferred. This field uses the main bank name as the default, but you can modify this information if you want.|  
    |**Combined payment for vendor**|Specify if the payment lines that have the same vendor, currency, bank, and debit bank will be combined in the generated DTA file.|  
  
5.  Choose the **OK** button. The DTA file is generated in the predetermined folder.  
  
 After you have generated the DTA file, you can print the DTA payment order and transfer both the file and the payment order to your bank. The DTA payment order lists all suggested vendor payments in a **Payment Journal** window based on currency code. This order is sent to the bank to release the DTA file for payment.  
  
### To print a DTA payment order  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch.  
  
3.  Select the required payment entry, and on the **Home** tab, in the **Process** group, select **DTA Payment Order**.  
  
4.  In the **Message** field, enter a message for the bank, to be printed at the bottom of the payment order.  
  
5.  Choose the **Print** button to print the DTA payment order or choose the **Preview** button to view it on the screen.  
  
     You must submit the DTA payment order and the DTA file to the bank, where payments to the vendors are released in a few hours. After the payments have been processed by the bank, you can post the payment journal.  
  
## See Also  
 [Swiss Electronic Payments Using DTA](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-dta.md)   
 [How to: Suggest DTA Payment for Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-suggest-dta-payment-for-vendors.md)   
 [How to: Verify a List of Vendors for DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-verify-a-list-of-vendors-for-dta-payments.md)   
 [How to: Export Payments Using EZAG](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-export-payments-using-ezag.md)   
 [Payment Journal](../../Finance/-$-n_256-payment-journal-$-.md)   
 [General Journal](assetId:///a60a346f-f336-47bb-b046-55a1595e1555)   
 [DTA Setup](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-t_3010541-dta-setup-$-.md)