---
title: "Payment Management"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment management, about"
  - "payment slips, about"
ms.assetid: df5a13ce-5276-4d6f-a17b-bce6a04f46c3
caps.latest.revision: 32
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# Payment Management
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] allows you to manage bills of exchange, electronic payments, and vendor payments using the payment management function.  
  
 You can manage customer and vendor payments using payment slips. Before you create a payment slip, you must set up the following prerequisites:  
  
-   Payment class – The type of payment that you want to perform, for example, bill of exchange, electronic payment, or check. For more information, see [How to: Set Up Payment Classes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-classes.md).  
  
-   Payment status – The progress level of a payment document. You must define a set of statuses for each payment class. For more information, see [How to: Set Up Payment Statuses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-statuses.md).  
  
-   Payment steps – A payment that is executed at a specified time. After a payment step is completed, you can move the payment document from one status to another. If a step involves posting debit or credit entries, you must define additional actions in the **Payment Step Ledger** table. For more information, see [How to: Set Up Payment Steps](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-steps.md).  
  
-   Payment address for vendors and customers – The address that is used for a vendor or a customer at the time of settlement. The payment address can be different from the vendor’s or customer's default address. For more information, see [How to: Set Up Payment Addresses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-addresses.md).  
  
 You can also transfer your payment management setup information to an external disk so that you can use the same parameters for another company with similar requirements. You can export the payment data in the following formats:  
  
-   ETEBAC – To create a bill of exchange remittance.  
  
-   Withdraw – To create a customer payment withdrawal \(direct debit\).  
  
-   Transfer – To create a vendor payment transfer \(credit transfer\).  
  
## Managing Payment Slips and Files  
 You can create payment slips to manage customer payments and vendor payments. After creating the payment slip, you must post it.  
  
 These payment slips can then be converted into payment files, which can be sent to the bank electronically.  
  
 For more information, see [How to: Create Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-create-payment-slips.md).  
  
### Archiving Payment Slips  
 You can separate a fully processed payment slip from the active payment slips by archiving it. You can manually archive an individual payment slip or you can automatically archive a batch of payment slips. For more information, see [How to: Archive Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-archive-payment-slips.md).  
  
## See Also  
 [How to: Set Up Payment Classes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-classes.md)   
 [How to: Set Up Payment Statuses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-statuses.md)   
 [How to: Set Up Payment Steps](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-steps.md)   
 [How to: Set Up Payment Addresses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-addresses.md)   
 [How to: Create Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-create-payment-slips.md)   
 [How to: Post Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-post-payment-slips.md)   
 [How to: Archive Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-archive-payment-slips.md)   
 [How to: Export or Import Payment Management Setup Parameters](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-export-or-import-payment-management-setup-parameters.md)   
 [Payment Slip](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-n_10868-payment-slip-$-.md)   
 [Payment Class](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10860-payment-class-$-.md)   
 [Bank Account](assetId:///859a3a4a-835d-4443-9715-a8d79d986654)   
 [France Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/france-local-functionality.md)