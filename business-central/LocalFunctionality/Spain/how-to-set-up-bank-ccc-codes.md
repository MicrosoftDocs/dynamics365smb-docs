---
title: Set up bank CCC codes [ES]
description: The Código Cuenta Cliente (CCC) is a unique account code assigned by Spanish banks to customer accounts, appearing on documents, such as checks and statements.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: CCC, unique account code, set up ccc, enter ccc, set up bank codes, bank codes, Spanish version
ms.date: 05/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up bank CCC codes in the Spanish version

Código Cuenta Cliente (CCC) is a unique account code used by Spanish banks to identify their customers. The CCC code is printed on bank documents such as checks and statements.  

You can set up CCC codes in the following locations:  

- **Bank Account Card** page  
- **Company Information** page  
- **Customer Bank Account Card** page  
- **Vendor Bank Account Card** page  

The following procedure describes how to set up bank CCC codes for your company.  

## Enter CCC codes  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. On the **Payments** FastTab, fill in the fields as described in the following table.  

    |Field           |Position |Description                            |  
    |----------------|---------|---------------------------------------|  
    |**CCC Bank No.**|1-4|Identifies the bank that opened the account.|  
    |**CCC Bank Branch No.**|5-8|Identifies the branch code. If the bank doesn't use this reference, the branch code can be zeros.|  
    |**CCC Control Digits**|9-10|Identifies the control digits.|  
    |**CCC Bank Account No.**|11-20 (Spain)<br><br/> 11-21 (Portugal)|Identifies the account number, which might be adjusted with preceding zeros.|  

The following procedure describes how to set up bank CCC codes for existing customer bank accounts, but the same steps apply to vendors, bank accounts, and company information.  

## Set up bank CCC codes for a customer bank account  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Bank Account Card**, and then choose the related link.  
1. On the **Transfer** FastTab, enter information into the relevant CCC fields.  

    > [!NOTE]  
    > You must set up the company information on the **Payments** FastTab.  

1. Choose the **OK** button.  

## Related information

[Set Up Bank Accounts](../../bank-how-setup-bank-accounts.md) 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
