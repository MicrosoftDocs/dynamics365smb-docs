---
title: How to Export Electronic Payments [ES]
description: In Business Central, you can export payment journal entries to files using four different payment standards, each supported by specific pages.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export payment journal entries, export electronic payments, payment standards, cartera module, payment journal, payment orders, Spanish version
ms.date: 05/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export electronic payments in the Spanish version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can export payment journal entries into a file format according to four different payment standards. You must use the following pages to export according to the different payment standards.  

|Payment standard|Page to export from|  
|----------------------|---------------------------|  
|AEB N34|**Payment Orders**|  
|AEB N34.1|**Payment Orders**|  
|E-PAY|**Payment Journal**|  
|SEPA|**Payment Journal** or **Payment Orders**|  

> [!IMPORTANT]  
> Before you can export a payment, you must select a payment format in the **Payment Export Format** field on the **Bank Account Card** page.  

## Export electronic payments using the Payment Orders page  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Orders**, and then choose the related link.  
1. Select the documents that you want to pay.  
1. Choose THE **Export to File** action.  

   Payments of type SEPA are exported to a file immediately.  

   Payments of type N34 or N34.1 are exported when you run the **Payment order - Export N34** or **PO - Export N34.1** report, which automatically opens when you choose **Export** in step 3.  

1. On the **PO - Export N34.1** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account No.**|Select the bank account from which the payments are exported.|  
    |**Settle Date**|Specify the date when the export is transmitted to the bank. This date is the posting date for the payment journal entries that are exported.|  
    |**If Posting Date does not match Delivery Date**|Specify if you want to match the settle date, or if you want to skip any payment journal lines where the entered posting date doesn't match the settle date.|  
    |**Expenses Code**|Specify who is responsible for the payment expenses.|  
    |**Shared (Only International Transf.**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
    |**Payment Order Concept.)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**Relation**|Specify if you want the bank to send you a detailed list of all transfer charges. If you don't select this field, the bank sends the total of all charges for all the transfers made.|  
    |**Number Of Copies**|Specify the number of additional copies of the remittance advice that are printed by this process. One document is always printed so that it can be mailed to the payee.|  

1. Choose the **Print** or the **Preview** action to see the created payment file.  

   The payment journal entries which have the **Bank Payment Type** field set to **Electronic Payment** are exported. The data is exported to a file that is formatted according to the N34 or N34.1 standard format. In addition, remittance advice is printed, which is suitable for mailing to each payee.  

    > [!NOTE]  
    > You can only post the payment order after you successfully export the electronic payments.  

## Export electronic payments using the Payment Journal page  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
1. Select the documents that you want to pay.  
1. Choose the **Related** > **Payments** > **Electronic Payments** > **Export**.  

   Payments of type SEPA are exported to a file immediately.  
   Payments of type E-PAY are exported when you run the **Export Electronic Payments** report, which automatically opens when you choose **Export** in step 3.  

1. On the **Export Electronic Payments** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account No.**|Select the bank account from which the payments are exported.|  
    |**Settle Date**|Specify the date when the export is transmitted to the bank. This date is the posting date for the payment journal entries that are exported.|  
    |**If Posting Date does not match Delivery Date**|Specify if you want to match the settle date, or if you want to skip any payment journal lines where the entered posting date doesn't match the settle date.|  
    |**Expenses Code**|Specify who is responsible for the payment expenses.|  
    |**Shared (Only International Transf.**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  
    |**Payment Order Concept.)**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**Relation**|Specify if you want the bank to send you a detailed list of all transfer charges. If you don't select this field, the bank sends the total of all charges for all the transfers made.|  
    |**Number Of Copies**|Specify the number of additional copies of the remittance advice that is printed by this process. One document is always printed so that it can be mailed to the payee.|  

1. Choose the **Print** or the **Preview** action to see the created payment file.  

   The payment journal entries which have the **Bank Payment Type** field set to **Electronic Payment** is exported. The data is exported to a file that is formatted according to the selected payment standard. In addition, remittance advice is printed, which is suitable for mailing to each payee.  

    > [!NOTE]  
    > You can only post the payment order after you successfully export the electronic payments.  
    > [!NOTE]  
    > In the generic version of [!INCLUDE[prod_short](../../includes/prod_short.md)], the **Payment Journal** page is used in a similar way to export electronic payments in the SEPA Credit Transfer format. Learn more in [Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).  

## Export electronic payments from the Cartera module  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **PO - Export N34.1**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Delivery Date**|Specify the delivery date of the electronic payment.|  
    |**Expenses Code**|Specify who is responsible for the payment expenses.|  
    |**Payment Order Concept**|Specify the payment order concept, either **Payroll**, **Retirement Payroll**, or **Others**.|  
    |**Relation**|Specify if you want the bank to send you a detailed list of all transfer charges. If you don't select this field, the bank sends the total of all charges for all the transfers made.|  
    |**Number Of Copies**|Specify the number of additional copies of the remittance advice that are printed by this process. One document is always printed so that it can be mailed to the payee.|  
    |**Shared (Only Internation Transf.)**|Specify if you want to share the expenses between the payer and the payee. This is only applicable for international transfers.|  

> [!NOTE]  
> You can only post the payment order after you successfully export the electronic payments.  

## Related information

- [Electronic Payments – AEB N34.1](electronic-payments-aeb-n341.md)  
- [Set Up Bank Accounts for Electronic Payments](how-to-set-up-bank-accounts-for-electronic-payments.md)  
- [Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
