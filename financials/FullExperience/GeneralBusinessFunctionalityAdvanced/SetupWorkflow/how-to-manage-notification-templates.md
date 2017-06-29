---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Make Minor Changes to Approved Records
If you want to make a minor change to a record after it has been approved, you can reopen the record, make the change, and then release it. For minor changes, you do this with the **Reopen** and **Release** buttons.  
  
 If you want to make significant changes to a record, such as the item number or quantity on a purchase invoice, you must cancel the approval request, make the change, and then request approval again. For more information, see [How to: Cancel Requests for Approval](../how-to-approve-or-reject-requests-for-approval.md).  
  
 Approval of records must be set up as workflows, one workflow for each scenario, such as the Purchase Invoice Approval Workflow. The generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]--> includes workflow templates for approval of all types of sales and purchase documents and for other records, such as customer cards. For more information, see the list of workflow templates in the Workflow Templates window.  
  
### To make minor changes to an approved record  
  
1.  Open the window that displays the record, such as a purchase invoice.  
  
2.  On the **Home** tab, in the **Process** group, choose **Reopen**. The **Document Status** field is changed to **Open**.  
  
3.  Make the necessary changes on the record, such as the vendor’s address.  
  
4.  On the **Home** tab, in the **Process** group, choose **Release**.  
  
 When you reopen the source record, the status of the related approval entry remains **Approved** in the **Approval Entries** window.  
  
## See Also  
 Approval Entries   
 [How to: Cancel Requests for Approval](../how-to-cancel-requests-for-approval.md)   
 [How to: Approve or Reject Requests for Approval](../how-to-approve-or-reject-requests-for-approval.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Set Up Workflows](../set-up-workflows.md)   
 [Use Workflows](../use-workflows.md)   
 [Business Functionality](../Business%20Functionality.md)