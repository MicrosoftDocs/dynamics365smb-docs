---
    title: How to: Set Up Payment Line Information | Microsoft Docs
    description: Payment journal line information for the remittance payment is set up in the **Payment Info** window.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up Payment Line Information
Payment journal line information for the remittance payment is set up in the **Payment Info** window.  
  
### To set up payment line information  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  On the **Navigate** tab, choose **Payment Info**.  
  
3.  In the **Payment Info** window, on the **General** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Remittance Account Code**|Select the remittance account code.|  
    |**Remittance Agreement Code**|Specify the agreement code assigned to the account code.|  
    |**Remittance Type**|Specify the remittance type assigned to the account code. Remittance types include **Domestic** and **Foreign**.|  
  
4.  On the **Domestic** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recipient Ref. 1 – 3**|Specify the payment text which is sent to the vendor.|  
    |**KID (Cust. id number)**|Specify the number sent to the vendor during payment.|  
    |**Our Account. No.**|Specify the account number for your company.|  
    |**External Document No.**|Specify the number of the external document.|  
    |**Payment Type Code Domestic**|Specify the payment type code that is assigned to the payment.|  
  
    > [!NOTE]  
    >  The recipient reference and the KID number cannot be entered for the same payment. If the KID is used, this is the only information that the vendor receives.  
  
5.  On the **Foreign** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Recipient Ref. Abroad**|Specify the payment text that is sent to the vendor.|  
    |**Payment Type Code Abroad**|Specify the payment type code that is assigned to the payment.|  
    |**Check**|Specify whether a check must be issued.<br /><br /> * <br />                        **No** - No check is issued.<br /><br /> * **Send to employer** - Check is issued and sent to the employer.<br /><br /> * **Send to beneficiary** - Check is issued and sent to the beneficiary.|  
    |**Urgent**|Select if the payment is urgent and should be treated as an urgent transfer.|  
    |**Agreed Exch. Rate**|Specify the exchange rate which the bank agrees upon.|  
    |**Agreed With**|Specify who the agreement is entered with, if an exchange rate is agreed upon.|  
    |**Futures Contract No.**|Specify the future contract number that is used for this payment.|  
    |**Futures Contract Exch. Rate**|Specify the future contract exchange rate that is used for this payment.|  
  
6.  Choose the **OK** button.  
  
## See Also  
 [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)   
 [How to: Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)   
 [How to: Create Remittance Accounts](how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](recipient-reference-codes.md)   
 [How to: Create Remittance Suggestions](how-to-create-remittance-suggestions.md)   
 [How to: Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)   
 [How to: Test Remittance Payments](how-to-test-remittance-payments.md)   
 [How to: Export Remittance Payments](how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](types-of-payment-returns-files.md)   
 [How to: Import Payment Return Data](how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](remittance-errors.md)   
 [How to: View Remittance Error Codes](how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](how-to-cancel-payments.md)