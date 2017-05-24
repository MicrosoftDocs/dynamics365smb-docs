---
title: "How to: Create Payment Journal Templates and Batches"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment journals, templates"
  - "payment journals, batches"
ms.assetid: c23b6644-eb6b-45e4-90be-25179a56427e
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Create Payment Journal Templates and Batches
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], payment suggestions are generated and posted in payment journals. The structure of the payment journal is similar to the structure of other journal types. However, the payment journal contains some fields that are specific for processing payments. Before you can start generating payment suggestions, you have to set up a payment journal template and a payment journal batch.  
  
 If you assign a bank account to the payment journal template, the bank account will be inserted on all payment journal batches and payment journal lines that are created by using this template. By specifying a bank account for the journal template, you can reduce the time that is required for checking the payment suggestions.  
  
### To create a payment journal template  
  
1.  In the **Search** box, enter **Payment Journal Templates**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **\($ N\_2000000 EB Payment Journal Templates $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_2000000\_1 Name $\)**|Enter the unique name for the payment journal template that you are creating.|  
    |**\($ T\_2000000\_2 Description $\)**|Enter a description of the payment journal template.|  
    |**\($ T\_2000000\_19 Bank Account $\)**|Select the bank account that will be used when you create a payment suggestion.|  
    |**\($ T\_2000000\_11 Reason Code $\)**|Select the reason code that will be used on all the journal batches and lines that are created by using the journal template. If you want to use a different reason code on a journal line, you can manually change it.|  
    |**\($ T\_2000000\_10 Source Code $\)**|Select the source code that will be used on all the journal batches and lines that are created by using the journal template.|  
  
4.  Choose the **OK** button.  
  
### To add payment journal batches to the journal template  
  
1.  In the **Payment Journal Templates** window, on the **Navigate** tab, in the **Template** group, choose **Batches**.  
  
2.  In the **\($ N\_2000002 Paym. Journal Batch $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_2000002\_1 Journal Template Name $\)**|Specify a journal template name for the payment journal batch.|  
    |**\($ T\_2000002\_2 Name $\)**|Enter a unique name for the journal batch.<br /><br /> **NOTE:** To have the journal name update numerically, include a number in the journal batch name. For example, the name KBC1 will increment by one number with every posting to KBC2, KBC3, and so on.|  
    |**\($ T\_2000002\_3 Description $\)**|Enter a description for the journal batch.|  
    |**\($ T\_2000002\_4 Reason Code $\)**|Specifies the reason code that is linked to this journal batch.|  
    |**\($ T\_2000002\_5 Status $\)**|Specifies the status of the batch.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Belgian Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-payments.md)   
 [How to: Set Up Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-electronic-banking.md)   
 [How to: Set Up IBLC\-BLWI Transaction Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-iblc-blwi-transaction-codes.md)