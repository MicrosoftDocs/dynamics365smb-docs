---
title: FIK details in the payment reconciliation journal
description: The Transaction Text field shows information about the automatic application of payments using the Danish FIK standard.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: transaction text, automatic application, payment reconciliation journal, FIK number, Denmark
ms.date: 03/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# FIK details in the payment reconciliation journal

The **Transaction Text** field on the **Payment Reconciliation Journal** page shows information about the automatic application of payments using the Danish FIK standard. Learn more in [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md).  

The following table describes the six values that might be shown in the **Transaction Text** field.

|Transaction Text|Description|  
|-----------------------------------------|---------------------------------------|  
|**Matching Amount**|The amount paid covers exactly the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**Partial Amount**|The amount paid is less than the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**Excess Amount**|The amount paid is more than the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**No Matching FIK Number**|The system has not found any unpaid or paid sales invoices with a FIK number that matches the FIK number on the payment.|  
|**Duplicate FIK Number**|The system has discovered that there are payments that have similar FIK numbers.|  
|**Invoice Already Paid**|The system has discovered that a FIK number on a payment matches a sales invoice that is fully applied and closed.|  

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
