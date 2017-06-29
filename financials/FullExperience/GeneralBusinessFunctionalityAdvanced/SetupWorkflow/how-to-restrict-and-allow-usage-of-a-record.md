---
title: "How to: Restrict and Allow Usage of a Record"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: b1319169-ccd7-4cfb-80ff-0644f2156777
caps.latest.revision: 5
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Restrict and Allow Usage of a Record
If you want to restrict a record from being used in certain activities, for example, until the record has been approved, you can incorporate two workflow responses in a workflow that controls the usage of the record. One workflow response will restrict usage of the record as defined by the workflow event and conditions. Another workflow response will allow usage of the record as defined by the workflow event and conditions. Two responses exist in the generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] for this purpose: **Restrict usage of a record.** and **Allow usage of a record.**. For more information, see Workflow Templates.  
  
> [!NOTE]  
>  The generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] offers support for restricting a record from being posted, from being exported as a payment, and from being printed as a check. To support other restrictions, a Microsoft partner must customize the application code.  
  
> [!NOTE]  
>  The workflow functionality to restrict and allow records from being used is not related to the functionality to block item, customer, and vendor records from being posted. For more information, see Blocked.  
  
 The following procedure describes how to restrict purchase orders from being posted until they have been approved. The new workflow will be based on the existing Purchase Invoice Approval Workflow workflow template.  
  
### To create a workflow step that restricts posting of unapproved purchase orders  
  
1.  In the **Search** box, enter **Workflows**, and then choose the related link.  
  
2.  In the **Workflows** window, create a new workflow named Purchase Order Approval Workflow. For more information, see [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md).  
  
3.  On the **Home** tab, in the **Process** group, choose **Copy From Workflow Template**.  
  
4.  Choose the **Source Workflow Code** field, and then, in the **Workflow Templates** window, choose the Purchase Invoice Approval Workflow workflow template.  
  
     Notice that the first two workflow steps are about restricting and then allowing usage of purchase invoices. Proceed to change the event condition on the first step of the new workflow to specify that it applies to purchase orders.  
  
5.  On the **Workflow Steps** FastTab, choose the **Event Conditions** field, and then, for the **Document Type** filter, select **Order**.  
  
6.  Proceed to edit, delete, or add other workflow steps to fit a business process that begins by restricting unapproved purchase orders from being posted.  
  
## See Also  
 Workflow Templates   
 [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [How to: Block Inventory Items for Sales or Purchases](../../LocalFunctionalityForMicrosoftDynamicsNav2016/how-to-block-inventory-items-for-sales-or-purchases.md)