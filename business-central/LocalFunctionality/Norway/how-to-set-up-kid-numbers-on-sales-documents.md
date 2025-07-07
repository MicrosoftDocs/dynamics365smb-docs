---
title: How to set up KID numbers on sales documents
description: Learn how to set up KID (Kunde ID), a customer identification number used as a payment reference to ensure accurate payment posting by vendors.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: KID numbers setup, KID number, customer identification number, payment reference, Norwegian version
ms.search.form: 456
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up KID numbers on sales documents

Kunde ID (KID) is a customer identification number that provides a payment reference to the vendor and ensures that the vendor is posting the payment correctly. You can set up KID numbers on sales documents to identify document and customer information on electronic banking transactions.  

## Steps to set up KID numbers on sales documents  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Documents** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**KID Setup**|Specifies a KID number format.|  
    |**Document No. length**|Enter the number of digits used for the document number.|  
    |**Customer No. length**|Enter the number of digits used for the customer number.|  
    |**Use KID on Fin. Charge Memo**|Select to print KID numbers on finance charge memos. **Note:**  If selected, then you must also select the **Document Type + Document No.** format in the **KID Setup** field.|  
    |**Use KID on Reminder**|Select to print KID numbers on reminders. **Note**:  If selected, then you must also select the **Document Type + Document No.** format in the **KID Setup** field.|

1. Choose the **OK** button.  

## Related information

[Electronic Banking in Norway](electronic-banking-in-norway.md) 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
