---
title: "How to: Set Up Customers for EHF"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: f6c457bd-1dbb-472c-9f96-87ad6452d953
caps.latest.revision: 5
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# How to: Set Up Customers for EHF
To create Elektronisk Handelsformat \(EHF\) documents for customers in the public sector, you must add EHF information to the relevant customers.  
  
 This topic only describes fields that apply to EHF. For more information on setting up customers, in general, see [How to: Register New Customers](../../Sales/how-to-register-new-customers.md).  
  
### To set up a customer that uses Elektronisk Handelsformat  
  
1.  In the **Search** box, enter **Customers**, and then choose the related link.  
  
2.  Open the customer that you want to enable for EHF.  
  
3.  On the **Invoicing** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_18\_90 GLN $\)**|Required. Enter the Global Location Number \(GLN\) for the customer.|  
    |**\($ T\_18\_10601 Account Code $\)**|Enter the account code for the customer.<br /><br /> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the EHF documents that you create in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]. For more information, see [\($ T\_18\_10601 Account Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/-$-t_18_10601-account-code-$-.md).|  
    |**\($ T\_18\_10602 E\-Invoice $\)**|Select the check box to use electronic invoicing with this customer.|  
    |**\($ T\_18\_5700 Responsibility Center $\)**|Make sure that the Responsibility Center that you have selected has a Country\/Region Code specified.|  
  
 These fields are specific to EHF. The values are used in all EHF documents that you create for this customer. For more information, see [EHF Electronic Invoicing in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/ehf-electronic-invoicing-in-norway.md).  
  
## See Also  
 [How to: Create Electronic Documents for EHF](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-electronic-documents-for-ehf.md)   
 [How to: Set Up EHF](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-ehf.md)