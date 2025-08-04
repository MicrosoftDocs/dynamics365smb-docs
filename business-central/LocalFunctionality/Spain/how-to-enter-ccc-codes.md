---
title: How to enter CCC codes [ES]
description: Learn how to enter the Código Cuenta Cliente (CCC) unique bank account identification code using the Spanish version of Business Central.
services: project-madeira 
author: brentholtorf
ms.topic: how-to
ms.search.keywords: CCC codes, bank account identification code, Spanish version
ms.date: 05/27/2025
ms.author: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Enter CCC codes in the Spanish version

Código Cuenta Cliente (CCC) is a unique bank account identification code. The following component fields make up the 20-digit (Spain) or 21-digit (Portugal) bank CCC code structure.  

If you change the CCC code structure, the **CCC No.** field updates automatically. Similarly, if you change the **CCC No.** field, the CCC code structure updates.  

## Enter CCC codes  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. On the **Payments** FastTab, fill in the fields as described in the following table.  

    |Field|Position|Description|  
    |---------------------------------|--------------|---------------------------------------|  
    |**CCC Bank No.**|1-4|Identifies the bank where the account is opened.|  
    |**CCC Bank Branch No.**|5-8|Identifies the branch code. If the bank doesn't use this reference, these can be zeros.|  
    |**CCC Control Digits**|9-10|Identifies the control digits.|  
    |**CCC Bank Account No.**|11-20 (Spain)<br> 11-21 (Portugal)|Identifies the account number, which might be adjusted with preceding zeros.|  

## Related information  

[Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
