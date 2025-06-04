---
title: Pay vendors using electronic payments [ES]
description: In Business Central, you can pay a vendor using electronic payments. Payments are exported to a file, which are then transmitted to your bank. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 12/12/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Pay vendors using electronic payments in the Spanish version
In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can pay a vendor using electronic payments. Payments are exported to a file, which are then transmitted to your bank. The bank then electronically transfers the payments from your bank account to the payee’s (vendor) bank account.  

This process is similar to how computer checks are processed.  

## To pay a vendor electronically  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
2. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Payment Type**|Specify **Electronic Payment** to create a corresponding check ledger entry for the amount.|  
    |**Payment Type**|Specify the payment type for the special transfer payment, if applicable. Select **Blank** if you don't want to use the special transfer payment type. Select **01** to create a special payment for “goods” on the journal line. Select **02** to create a special payment for “non-goods” on this journal line.|  
    |**Statistical Code**|Specify the statistical code for the special transfer payment, if applicable. The statistical code must be used at the same time as the payment type. Select **01** to create a special payment for “goods” on the journal line. Select **02** to create a special payment for “non-goods” on this journal line.|  

## Related information  
[Set Up Bank Accounts for Electronic Payments](how-to-set-up-bank-accounts-for-electronic-payments.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
