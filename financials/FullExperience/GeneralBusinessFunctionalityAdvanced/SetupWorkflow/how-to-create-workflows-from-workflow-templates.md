---
title: "How to: Cancel Requests for Approval"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "document approvals, canceling"
  - "approvals, canceling"
ms.assetid: 88e6cad8-af45-4ae5-a4e0-631924b41aa0
caps.latest.revision: 15
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
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
# How to: Cancel Requests for Approval
A customer may want to change an order after it has been submitted for approval. In this case, you can cancel the approval process and make the necessary changes to the order before you request approval again.  
  
 If you just want to make a minor change to an approved document, you can reopen it temporarily, and then release it again, without requesting approval again. For more information, see [How to: Make Minor Changes to Approved Records](../../BusinessFunctionality/Workflow/how-to-make-minor-changes-to-approved-records.md).  
  
 Approval of records must be set up as workflows, one workflow for each scenario, such as the Purchase Invoice Approval Workflow. The generic version of FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] --> includes workflow templates for approval of all types of sales and purchase documents and for other records, such as customer cards. For more information, see the list of workflow templates in the Workflow Templates window.  
  
### To cancel an approval request  
  
-   In the window that displays the record, on the **Actions** tab, in the **Request Approval** group, choose **Cancel Approval Request**.  
  
    > [!NOTE]  
    >  If the record is a journal line, then choose either **Selected Journal lines** or **Journal Batch** from the drop\-down list.  
    >   
    >  If you choose **Journal Batch**, then approval requests for all journal lines are canceled, also those that you may not see because of filters.  
  
 When the approval request has been canceled, the status of the related approval entry is changed to **Canceled**. The status of the record is updated from **Pending Approval** to **Open**. The approval process can then start again. For more information, see [How to: Request Approval](../../BusinessFunctionality/Workflow/how-to-request-approval.md).  
  
## See Also  
 Requests to Approve   
 [How to: Approve or Reject Requests for Approval](../../BusinessFunctionality/Workflow/how-to-approve-or-reject-requests-for-approval.md)   
 [How to: Make Minor Changes to Approved Records](../../BusinessFunctionality/Workflow/how-to-make-minor-changes-to-approved-records.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Set Up Workflows](../../BusinessFunctionality/Workflow/set-up-workflows.md)   
 [Use Workflows](../../BusinessFunctionality/Workflow/use-workflows.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)