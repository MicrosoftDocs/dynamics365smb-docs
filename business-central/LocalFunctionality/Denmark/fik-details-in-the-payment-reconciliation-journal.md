---
title: FIK details in the payment reconciliation journal
description: The Transaction Text field shows information about the automatic application of payments using the Danish FIK standard.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: transaction text, automatic application, payment reconciliation journal, FIK number, Denmark
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# FIK details in the payment reconciliation journal

The **Transaction Text** field on the **Payment Reconciliation Journal** page shows information about the automatic application of payments using the Danish FIK standard. Learn more in [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md).  

The following table describes the six values that might be shown in the **Transaction Text** field.

|Transaction Text|Description|  
|-----------------------------------------|---------------------------------------|  
|**Matching Amount**|The amount paid covers exactly the remaining amount on an unpaid sales invoice that's identified by the FIK number.|  
|**Partial Amount**|The amount paid is less than the remaining amount on an unpaid sales invoice that's identified by the FIK number.|  
|**Excess Amount**|The amount paid is more than the remaining amount on an unpaid sales invoice that's identified by the FIK number.|  
|**No Matching FIK Number**|No unpaid or paid sales invoices have a FIK number that matches the FIK number on the payment.|  
|**Duplicate FIK Number**|Multiple payments have similar FIK numbers.|  
|**Invoice Already Paid**|A FIK number on a payment matches a sales invoice that's fully applied and closed.|  

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
