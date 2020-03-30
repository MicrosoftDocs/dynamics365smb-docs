---
    title: How to Set Up Remittance Agreements
    description: You must sign an agreement of remittance with the bank when you set up electronic payments. You can create more than one remittance agreement if you have an agreement with two or more banks.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Remittance Agreements
You must sign an agreement of remittance with the bank when you set up electronic payments. You can create more than one remittance agreement if you have an agreement with two or more banks. For each agreement, you must specify one or more accounts from which the payment should be made. For each account, you must create a remittance account. For more information, see [Create Remittance Accounts](how-to-create-remittance-accounts.md).  

## To set up a remittance agreement  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Remittance Agreement Overview**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the agreement code from the bank.|  
    |**Description**|Specify a name for the agreement, such as the name of the bank.|  
    |**Payment System**|Select the payment system that will be used. Payment systems include **DnB Telebank**, **K-LINK**, **SparNett**, **Fokus Bank**, **Postbanken**, **Other bank**, and **BBS**.|  

4.  On the **Bank** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Operator No.**|Specify the operator information given by the bank.|  
    |**Company/Agreement No.**|Specify the company information given by the bank.|  
    |**Division**|Specify the division information given by the bank.|  
    |**Latest Sequence No.**|Specify the latest sequence number.|  
    |**Latest Daily Sequence No.**|Specify the latest daily sequence number.|  
    |**Latest Export**|Specify the date of the latest export.|  

5.  On the **BBS** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**BBS Customer Unit ID**|Specify the identification of the agreement for Bankernes Betalingssentral (BBS). This code is provided by BBS.|  
    |**Latest BBS Payment Order No.**|Specify the entry number that was used when payment was sent to BBS.|  

6.  On the **Send** FastTab, fill in the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Payment File Name**|Specify the path and the name of the file that contains the electronic payment order that was sent to the bank.|  

7.  On the **Receive** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----------|---------------------------------------|  
    |**Save Return File**|Select to automatically name the return file after it is imported without errors.|  
    |**Receipt Return Required**|Select to verify that the first-time return report is imported.|  
    |**Return File Is Not In Use**|Select if you do not want to use return files for approval and settlement of payment. You can use this feature if you do not want to update payments with return information from the bank.|  
    |**On Hold Rejection Code**|Enter the code to update a rejected vendor ledger entry. The ledger entry will be marked as **On Hold**, which means that after rejection, it is not added to the remittance proposal again.<br /><br /> If the code is blank, the entry is not marked as **On Hold**, which means that after rejection it can be added to a remittance proposal again.|  

8.  On the **Finance** FastTab, fill in the field as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**New Document Per Field**|Specify how documents are numbered when payments are posted. Options include **Date**, **Vendor**, and **Specified for account**.|  

9. Choose the **Return File Setup List** action.  
10. On the **Return File Setup List** page, choose the **New** action.  
11. Enter the return file name in the **Return File Name** field.  

    > [!NOTE]  
    >  At a minimum, you must set up one file name for each receipt return, rejected return, and settlement return. Contact your bank about the naming conventions that it uses.  

12. Choose the **OK** button.  

## See Also  
 [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)   
 [Create Remittance Accounts](how-to-create-remittance-accounts.md)   
 [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](recipient-reference-codes.md)   
 [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)   
 [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)   
 [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)   
 [Test Remittance Payments](how-to-test-remittance-payments.md)   
 [Export Remittance Payments](how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](types-of-payment-returns-files.md)   
 [Import Payment Return Data](how-to-import-payment-return-data.md)   
 [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](remittance-errors.md)   
 [View Remittance Error Codes](how-to-view-remittance-error-codes.md)   
 [Cancel Payments](how-to-cancel-payments.md)
