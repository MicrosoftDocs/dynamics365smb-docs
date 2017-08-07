---
    title: How to: Delegate Requests for Approval | Microsoft Docs
    description: To prevent documents from piling up or otherwise block the workflow, the approver and the approval administrator can delegate an approval request to a substitute approver. The substitute can either be a designated substitute, the direct approver, or the approval administrator, in that order of priority. You typically use this feature if an approver is out of office and is unable to approve requests before the due date.
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
# How to: Delegate Requests for Approval
To prevent documents from piling up or otherwise block the workflow, the approver and the approval administrator can delegate an approval request to a substitute approver. The substitute can either be a designated substitute, the direct approver, or the approval administrator, in that order of priority. You typically use this feature if an approver is out of office and is unable to approve requests before the due date.  

 Before you can delegate an approval request, you must set up a substitute approver, an approver, or an approval administrator. For more information, see [How to: Set Up Approval Users](across-how-to-set-up-approval-users.md).  

> [!NOTE]  
>  In addition to manually delegating approval requets, as described in the following procedures, you can wait for the delegation to happen automatically by the preconfigured job queue entry, Delegate Approval Requests.  

 Approval of records must be set up as workflows, one workflow for each scenario, such as the Purchase Invoice Approval Workflow. The generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)] includes workflow templates for approval of all types of sales and purchase documents and for other records, such as customer cards. For more information, see the list of workflow templates in the Workflow Templates window.  

### To delegate approval requests in the Requests to Approve window  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Requests to Approve**, and then choose the related link.  

2.  Select one or more lines for the approval requests that you want to delegate to a substitute approver.  

3.  On the **Home** tab, in the **Process** group, choose **Delegate**.  

 A notification to approve the request is sent to the substitute approver.  

### To delegate approval requests in the Approval Request Entries window  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Approval Entries**, and then choose the related link.  

2.  Select one or more lines for the approval requests that you want to delegate to a substitute approver.  

3.  On the **Home** tab, in the **Process** group, choose **Delegate**.  

 A notification to approve the request is sent to the substitute approver.  

## See Also  
 Requests to Approve   
 [How to: Set Up Approval Users](across-how-to-set-up-approval-users.md)   
 [How to: Approve or Reject Requests for Approval](across-how-to-approve-or-reject-requests-for-approval.md)   
 [How to: Make Minor Changes to Approved Records](across-how-to-make-minor-changes-to-approved-records.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Setting Up Workflows](across-set-up-workflows.md)   
 [Using Workflows](across-use-workflows.md)   
 [Workflow](across-workflow.md)
