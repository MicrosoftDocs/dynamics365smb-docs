---
title: How to Export Electronic Payments
description: In Business Central, you can export payment journal entries into a file format according to four different payment standards. You must use the following pages to export according to the different payment standards.

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

# Export Electronic Payments
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can export payment journal entries into a file format according to four different payment standards. You must use the following pages to export according to the different payment standards.  

|Payment standard|Page to export from|  
|----------------------|---------------------------|  
|AEB N34|**Payment Orders**|  
|AEB N34.1|**Payment Orders**|  
|E-PAY|**Payment Journal**|  
|SEPA|**Payment Journal** or **Payment Orders**|  

> [!IMPORTANT]  
>  Before you can export a payment, you must select a payment format in the **Payment Export Format** field on the **Bank Account Card** page.  

## To export electronic payments using the Payment Orders page  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Orders**, and then choose the related link.  
2.  Select the documents that you want to pay.  
3.  Choose THE **Export to File** action.  

    Payments of type SEPA will be exported to a file immediately.  

    Payments of type N34 or N34.1 will be exported when you run the **Payment order - Export N34** or **PO - Export N34.1** report, which automatically opens when you choose **Export** in step 3.  

4.  On the **PO - Export N34.1** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account No.**|Select the bank account from which the payments will be exported.|  
    |**Settle Date**|Specify the date that the export will be transmitted to the bank. This date will be the posting date for the payment journal entries that are exported.|  
    |**If Posting Date does not match Delivery Date**|Specify if you want to match the settle date, or if you want to skip any payment journal lines where the entered posting date does not match the settle date.|  
    |**Expenses Code**|Specify who is responsible for the payment expenses.|  
    |**Shared (Only International Transf.**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
    |**Payment Order Concept.)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**Relation**|Specify if you want the bank to send you a detailed list of all transfer charges. If you do not select this field, the bank will send the total of all charges for all the transfers made.|  
    |**Number Of Copies**|Specify the number of additional copies of the remittance advice that will be printed by this process. One document is always printed so that it can be mailed to the payee.|  

5.  Choose the **Print** or the **Preview** action to see the created payment file.  

    The payment journal entries which have the **Bank Payment Type** field set to **Electronic Payment** will be exported. The data will be exported to a file that is formatted according the N34 or N34.1 standard format. In addition, remittance advice will be printed, which is suitable for mailing to each payee.  

    > [!NOTE]  
    >  You can only post the payment order after you have successfully exported the electronic payments.  

## To export electronic payments using the Payment Journal page  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  Select the documents that you want to pay.  
3.  On the **Navigate** tab, choose **Electronic Payments**, and then choose **Export**.  

    Payments of type SEPA will be exported to a file immediately.  

    Payments of type E-PAY will be exported when you run the **Export Electronic Payments** report, which automatically opens when you choose **Export** in step 3.  

4.  On the **Export Electronic Payments** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account No.**|Select the bank account from which the payments will be exported.|  
    |**Settle Date**|Specify the date that the export will be transmitted to the bank. This date will be the posting date for the payment journal entries that are exported.|  
    |**If Posting Date does not match Delivery Date**|Specify if you want to match the settle date, or if you want to skip any payment journal lines where the entered posting date does not match the settle date.|  
    |**Expenses Code**|Specify who is responsible for the payment expenses.|  
    |**Shared (Only International Transf.**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
    |**Payment Order Concept.)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**Relation**|Specify if you want the bank to send you a detailed list of all transfer charges. If you do not select this field, the bank will send the total of all charges for all the transfers made.|  
    |**Number Of Copies**|Specify the number of additional copies of the remittance advice that will be printed by this process. One document is always printed so that it can be mailed to the payee.|  

5.  Choose the **Print** or the **Preview** action to see the created payment file.  

    The payment journal entries which have the **Bank Payment Type** field set to **Electronic Payment** will be exported. The data will be exported to a file that is formatted according to the selected payment standard. In addition, remittance advice will be printed, which is suitable for mailing to each payee.  

    > [!NOTE]  
    >  You can only post the payment order after you have successfully exported the electronic payments.  

    > [!NOTE]  
    >  In the generic version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)], the **Payment Journal** page is used in a similar way to export electronic payments in the SEPA Credit Transfer format. For more information, see [Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).  

## To export electronic payments from the Cartera module  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **PO - Export N34.1**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Delivery Date**|Specify the delivery date of the electronic payment.|  
    |**Expenses Code**|Specify who is responsible for the payment expenses.|  
    |**Payment Order Concept**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**Relation**|Specify if you want the bank to send you a detailed list of all transfer charges. If you do not select this field, the bank will send the total of all charges for all the transfers made.|  
    |**Number Of Copies**|Specify the number of additional copies of the remittance advice that will be printed by this process. One document is always printed so that it can be mailed to the payee.|  
    |**Shared (Only Internation Transf.)**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  

> [!NOTE]  
>  You can only post the payment order after you have successfully exported the electronic payments.  

## See Also  
[Electronic Payments – AEB N34.1](electronic-payments-aeb-n341.md)  
[Set Up Bank Accounts for Electronic Payments](how-to-set-up-bank-accounts-for-electronic-payments.md)  
[Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  
