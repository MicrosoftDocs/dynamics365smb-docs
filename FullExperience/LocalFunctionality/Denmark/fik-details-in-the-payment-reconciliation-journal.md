---
title: "FIK Details in the Payment Reconciliation Journal"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 68c221de-292a-4ae4-b636-c515db01e0b3
caps.latest.revision: 2
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
---
# FIK Details in the Payment Reconciliation Journal
The **\($ T\_274\_23 Transaction Text $\)** field in the **\($ N\_1290 Payment Reconciliation Journal $\)** window shows information about the automatic application of payments using the Danish FIK standard. For more information, see [How to: Reconcile Payments Using Automatic Application](../../Finance/how-to-reconcile-payments-using-automatic-application.md).  
  
 The following table describes the six values that may be shown in the **\($ T\_274\_23 Transaction Text $\)** field.  
  
|\($ T\_274\_23 Transaction Text $\)|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|-----------------------------------------|---------------------------------------|  
|**Matching Amount**|The amount paid covers exactly the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**Partial Amount**|The amount paid is less than the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**Excess Amount**|The amount paid is more than the remaining amount on an unpaid sales invoice that is identified by the FIK number.|  
|**No Matching FIK Number**|The system has not found any unpaid or paid sales invoices with a FIK number that matches the FIK number on the payment.|  
|**Duplicate FIK Number**|The system has discovered that there are payments that have similar FIK numbers.|  
|**Invoice Already Paid**|The system has discovered that a FIK number on a payment matches a sales invoice that is fully applied and closed.|  
  
## See Also  
 [\($ N\_1290 Payment Reconciliation Journal $\)](assetId:///f4e11659-b474-4de0-bfae-2ae0116d0665)   
 [Reconcile Payments Automatically](../../Finance/reconcile-payments-automatically.md)   
 [What's New](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/what-s-new.md)