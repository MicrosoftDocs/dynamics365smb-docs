---
title: How to Create Workflows from Workflow Templates | Microsoft Docs
description: To save time when creating new workflows, you can create workflows from workflow templates.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Create Workflows from Workflow Templates
To save time when creating new workflows, you can create workflows from workflow templates.  

 Workflow templates are non-editable workflows that exist in the generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)]. The codes for workflow templates that are added by Microsoft are prefixed with “MS-“.  

 Another way to quickly create a workflow is to import an existing workflow that you have on a file outside of [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Export and Import Workflows](across-how-to-export-and-import-workflows.md).  

On the **Workflow** page, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code. For more information, see [Create Workflows](across-how-to-create-workflows.md).  

## To create a workflow from workflow template  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.  
2.  Choose the **Create Workflow from Template** action. The **Workflow Templates** page opens.  
3.  Select a workflow template, and then choose the **OK** button.  

     The **Workflow** page opens for a new workflow containing all the information of the selected template. The value in the **Code** field is extended with, for example, “-01” to indicate that this is the first workflow that is created from the workflow template.  
4.  Proceed to create the workflow by editing the workflow steps or add new steps. For more information, see [Create Workflows](across-how-to-create-workflows.md).  

## See Also  
 [Create Workflows](across-how-to-create-workflows.md)   
 [Export and Import Workflows](across-how-to-export-and-import-workflows.md)   
 [View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)   
 [Delete Workflows](across-how-to-delete-workflows.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Setting Up Workflows](across-set-up-workflows.md)   
 [Using Workflows](across-use-workflows.md)   
 [Workflow](across-workflow.md)   
