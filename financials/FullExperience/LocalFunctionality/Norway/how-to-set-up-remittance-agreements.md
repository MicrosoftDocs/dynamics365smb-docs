---
title: "How to: Set Up Remittance Agreements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "remittance, agreements"
ms.assetid: e7e7c248-b6f6-403d-a88b-01eacc843a2f
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Set Up Remittance Agreements
You must sign an agreement of remittance with the bank when you set up electronic payments. You can create more than one remittance agreement if you have an agreement with two or more banks. For each agreement, you must specify one or more accounts from which the payment should be made. For each account, you must create a remittance account. For more information, see [How to: Create Remittance Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-accounts.md).  
  
### To set up a remittance agreement  
  
1.  In the **Search** box, enter **Remittance Agreement Overview**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the agreement code from the bank.|  
    |**Description**|Specify a name for the agreement, such as the name of the bank.|  
    |**Payment System**|Select the payment system that will be used. Payment systems include **DnB Telebank**, **K\-LINK**, **SparNett**, **Fokus Bank**, **Postbanken**, **Other bank**, and **BBS**.|  
  
4.  On the **Bank** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Operator No.**|Specify the operator information given by the bank.|  
    |**Company\/Agreement No.**|Specify the company information given by the bank.|  
    |**Division**|Specify the division information given by the bank.|  
    |**Latest Sequence No.**|Specify the latest sequence number.|  
    |**Latest Daily Sequence No.**|Specify the latest daily sequence number.|  
    |**Latest Export**|Specify the date of the latest export.|  
  
5.  On the **BBS** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**BBS Customer Unit ID**|Specify the identification of the agreement for Bankernes Betalingssentral \(BBS\). This code is provided by BBS.|  
    |**Latest BBS Payment Order No.**|Specify the entry number that was used when payment was sent to BBS.|  
  
6.  On the **Send** FastTab, fill in the field as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Payment File Name**|Specify the path and the name of the file that contains the electronic payment order that was sent to the bank.|  
  
7.  On the **Receive** FastTab, fill in the fields as described in the following table.  
  
    |Field|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |-----------|---------------------------------------|  
    |**Save Return File**|Select to automatically name the return file after it is imported without errors.|  
    |**Receipt Return Required**|Select to verify that the first\-time return report is imported.|  
    |**Return File Is Not In Use**|Select if you do not want to use return files for approval and settlement of payment. You can use this feature if you do not want to update payments with return information from the bank.|  
    |**On Hold Rejection Code**|Enter the code to update a rejected vendor ledger entry. The ledger entry will be marked as **On Hold**, which means that after rejection, it is not added to the remittance proposal again.<br /><br /> If the code is blank, the entry is not marked as **On Hold**, which means that after rejection it can be added to a remittance proposal again.|  
  
8.  On the **Finance** FastTab, fill in the field as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**New Document Per Field**|Specify how documents are numbered when payments are posted. Options include **Date**, **Vendor**, and **Specified for account**.|  
  
9. On the **Navigate** tab, in the **Receive** group, choose **Return File Setup List**.  
  
10. In the **Return File Setup List** window, on the **Home** tab, in the **New** group, choose **New**.  
  
11. Enter the return file name in the **Return File Name** field.  
  
    > [!NOTE]  
    >  At a minimum, you must set up one file name for each receipt return, rejected return, and settlement return. Contact your bank about the naming conventions that it uses.  
  
12. Choose the **OK** button.  
  
## See Also  
 [Electronic Payments to Vendors in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/electronic-payments-to-vendors-in-norway.md)   
 [How to: Create Remittance Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/recipient-reference-codes.md)   
 [How to: Create Remittance Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-suggestions.md)   
 [How to: Create Manual Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-manual-remittance-payments.md)   
 [How to: Set Up Payment Line Information](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-payment-line-information.md)   
 [How to: Test Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-test-remittance-payments.md)   
 [How to: Export Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/types-of-payment-returns-files.md)   
 [How to: Import Payment Return Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/remittance-errors.md)   
 [How to: View Remittance Error Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-cancel-payments.md)