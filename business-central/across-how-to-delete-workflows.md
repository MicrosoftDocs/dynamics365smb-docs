---
title: How to Delete Approval Workflows
description: If you're certain that a workflow is no longer being used, you can delete it. All workflow step instances defined in the workflow must be status **Completed**.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 1500, 
ms.date: 09/08/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Delete Approval Workflows

If you're certain a workflow is no longer being used, you can delete it. All workflow step instances defined in the workflow must have a **Completed** status.

> [!CAUTION]
> When you delete a workflow, all information in the workflow is lost.

On the **Workflow** page, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines using fixed lists of event and response values representing scenarios supported by the application code. Learn more at [Create Approval Workflows](across-how-to-create-workflows.md).

## Delete a workflow

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, then choose the related link.
2. Select the workflow you want to delete.
3. Choose the **Delete** action.
4. Alternatively, open the workflow you want to delete.
5. On the **Workflow** page, choose the **Delete** action.

> [!NOTE]
> Deleting a workflow requires it to be disabled. To disable a workflow, open it in the **Workflows** page, then turn off the **Enabled** toggle.

## Related information

[Create Approval Workflows](across-how-to-create-workflows.md)  
[Enable Approval Workflows](across-how-to-enable-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Setting Up Approval Workflows](across-set-up-workflows.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
