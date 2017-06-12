---
title: "How to: Set Up Payment Classes"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment management, setting up classes"
  - "payment classes"
ms.assetid: 979c90ff-ec64-4665-b7a4-fcc78dee4ce3
caps.latest.revision: 29
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# How to: Set Up Payment Classes
To use payment management, you must set up payment classes to define operation types, such as bills of exchange, electronic payments, or checks.  
  
### To set up a payment class  
  
1.  In the **Search** box, enter **Payment Slip Setup**, and then choose the relevant link.  
  
2.  In the **Payment Class** window, on the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Enable**|Select to enable usage of the payment class.|  
    |**Code**|The unique identification code for the payment class.|  
    |**Name**|The payment class description.|  
    |**Header No. Series**|The number series code for the payment slip header.|  
    |**Line No. Series**|The number series code for the payment slip lines. If you leave this field blank, the number for each payment line is created based on the payment header number.|  
    |**Suggestions**|The type of payment proposals that can be created automatically on a payment slip.|  
    |**Unrealized VAT Reversal**|Specify the method to handle unrealized VAT.<br /><br /> If you select **Application**, VAT will be realized when you post the invoice application and payment application.<br /><br /> If you select **Delayed**, you must define the payment step during which VAT must be realized, by selecting the **Realize VAT** field in the **Payment Step Card** window. For more information, see [Realize VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10862_19-realize-vat-$-.md) and [Payment Step](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10862-payment-step-$-.md).|  
    |**SEPA Transfer Type**|Specify the SEPA export format, either **Credit Transfer** or **Direct Debit**.|  
  
     For more information, see [Payment Class](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10860-payment-class-$-.md).  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Payment Management](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/payment-management.md)   
 [How to: Set Up Payment Statuses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-statuses.md)   
 [How to: Set Up Payment Steps](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-steps.md)   
 [How to: Set Up Payment Addresses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-addresses.md)   
 [How to: Export or Import Payment Management Setup Parameters](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-export-or-import-payment-management-setup-parameters.md)   
 [How to: Create Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-create-payment-slips.md)   
 [How to: Post Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-post-payment-slips.md)   
 [How to: Archive Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-archive-payment-slips.md)   
 [Payment Class](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-n_10864-payment-class-$-.md)   
 [Payment Class](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10860-payment-class-$-.md)   
 [Realize VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10862_19-realize-vat-$-.md)   
 [Payment Step](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10862-payment-step-$-.md)