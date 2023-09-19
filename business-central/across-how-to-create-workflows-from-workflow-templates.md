---
title: How to Create Workflows from Workflow Templates
description: To save time when creating new approval workflows, you can create non-editable workflows from the workflow templates prefixed with "MS".
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 09/08/2022
ms.author: bholtorf
---
# Create Workflows from Workflow Templates

To save time when creating new approval workflows, you can use workflow templates.  

Workflow templates are non-editable workflows that exist in the default version of [!INCLUDE[prod_short](includes/prod_short.md)]. The codes for workflow templates created by Microsoft are prefixed with "MS-".  

Another way to quickly create a workflow is to import an existing workflow you have on a file outside of [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Export and Import Workflows](across-how-to-export-and-import-workflows.md).  

On the **Workflow** page, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code. Learn more at [Create Workflows](across-how-to-create-workflows.md).  

## To create a workflow from a workflow template

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, then choose the related link.  
2. Choose the **New Workflow from Template** action. The **Workflow Templates** page opens.  
3. Select a workflow template, then choose **OK**.  

   The **Workflow** page opens for a new workflow containing all the information of the selected template. The value in the **Code** field is extended with, for example, "-01" to indicate this is the first workflow created from the workflow template.  
4. Proceed to create the workflow by editing the workflow steps or adding new steps. Learn more at [Create Workflows](across-how-to-create-workflows.md).  

## See also

[Create Approval Workflows](across-how-to-create-workflows.md)  
[Export and Import Approval Workflows](across-how-to-export-and-import-workflows.md)  
[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)  
[Delete Approval Workflows](across-how-to-delete-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Setting Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Workflow](across-workflow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
