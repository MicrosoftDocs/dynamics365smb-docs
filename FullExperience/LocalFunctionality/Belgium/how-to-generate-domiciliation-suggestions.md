---
title: "How to: Generate Domiciliation Suggestions"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "domiciliations, suggestions"
  - "suggestions, for domiciliations"
ms.assetid: 14717cc0-e368-438b-a979-79d7ad979ab2
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Generate Domiciliation Suggestions
After you have set up domiciliations, you can start generating domiciliation suggestions. In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can only create domiciliation suggestions for domestic customers.  
  
### To generate domiciliation suggestions  
  
1.  In the **Search** box, enter **Domiciliation Journal**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch, and on the **Home** tab, in the **Progress** group, choose **Suggest Domiciliations**.  
  
3.  On the **Options** FastTab, fill in the fields as displayed in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Due Date**|Enter the due date to be included in the batch job. Only entries that have a due date before or on this date will be included.|  
    |**Take Payment Discounts**|Select if you want the batch job to include customer ledger entries for which you can receive a payment discount.|  
    |**Payment Discount Date**|Enter the date that will be used to calculate the payment discount.|  
    |**Select Possible Refunds**|Select if you want the batch job to include refunds.|  
    |**Posting Date**|Enter the date that will appear as the posting date on the lines that the batch job inserts in the domiciliation journal.|  
  
4.  On the **Customer** FastTab, enter any additional filter criteria.  
  
5.  Choose the **OK** button.  
  
     When the batch job is finished, the domiciliation journal contains all open customer ledger entries that match the filters.  
  
> [!NOTE]  
>  The domiciliation suggestions will only include customers who have a Domiciliation number set up. For more information, see [How to: Set Up Domiciliations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-domiciliations.md).  
  
## See Also  
 [Belgian Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-banking.md)   
 [Direct Debit Using Domiciliation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/direct-debit-using-domiciliation.md)   
 [How to: Set Up Domiciliations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-domiciliations.md)   
 [How to: Test Domiciliations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-test-domiciliations.md)   
 [How to: Edit and Delete Domiciliation Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-edit-and-delete-domiciliation-lines.md)   
 [How to: Export and Post Domiciliations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-export-and-post-domiciliations.md)