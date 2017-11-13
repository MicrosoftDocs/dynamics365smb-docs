---
    title: How to Pay Vendors Using Electronic Payments
    description: In [!INCLUDE[navnow](../../includes/navnow_md.md)], you can pay a vendor using electronic payments. Payments will be exported to a file, which will then be transmitted to your bank. The bank then electronically transfers the payments from your bank account to the payee’s (vendor) bank account.

    documentationcenter: ''
    author: SorenGP

    ms.prod: "dynamics-nav-2017"
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/26/2017
    ms.author: sgroespe

---
# How to: Pay Vendors Using Electronic Payments
In [!INCLUDE[navnow](../../includes/navnow_md.md)], you can pay a vendor using electronic payments. Payments will be exported to a file, which will then be transmitted to your bank. The bank then electronically transfers the payments from your bank account to the payee’s (vendor) bank account.  

This process is similar to how computer checks are processed.  

## To pay a vendor electronically  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Payment Type**|Specify **Electronic Payment** to create a corresponding check ledger entry for the amount.|  
    |**Payment Type**|Specify the payment type for the special transfer payment, if applicable. Select **Blank** if you do not want to use the special transfer payment type. Select **01** to create a special payment for “goods” on the journal line. Select **02** to create a special payment for “non-goods” on this journal line.|  
    |**Statistical Code**|Specify the statistical code for the special transfer payment, if applicable. The statistical code must be used at the same time as the payment type. Select **01** to create a special payment for “goods” on the journal line. Select **02** to create a special payment for “non-goods” on this journal line.|  

## See Also  
[How to: Set Up Bank Accounts for Electronic Payments](how-to-set-up-bank-accounts-for-electronic-payments.md)
