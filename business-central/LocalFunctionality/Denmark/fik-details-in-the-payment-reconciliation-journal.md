---
    title: FIK details in the payment reconciliation journal
    description: The Transaction Text field shows information about the automatic application of payments using the Danish FIK standard.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 12/12/2023
    ms.author: bholtorf
---
# FIK details in the payment reconciliation journal
The **Transaction Text** field on the **Payment Reconciliation Journal** page shows information about the automatic application of payments using the Danish FIK standard. For more information, see [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md).  

 The following table describes the six values that might be shown in the **Transaction Text** field.  

|Transaction Text|Description|  
|-----------------------------------------|---------------------------------------|  
|**Matching Amount**|The amount paid covers exactly the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**Partial Amount**|The amount paid is less than the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**Excess Amount**|The amount paid is more than the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**No Matching FIK Number**|The system has not found any unpaid or paid sales invoices with a FIK number that matches the FIK number on the payment.|  
|**Duplicate FIK Number**|The system has discovered that there are payments that have similar FIK numbers.|  
|**Invoice Already Paid**|The system has discovered that a FIK number on a payment matches a sales invoice that is fully applied and closed.|  

## See also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]