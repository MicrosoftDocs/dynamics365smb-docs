---
title: How to create workflows from workflow templates
description: Create new approval workflows quickly by using workflow templates as a starting point.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: workflows, workflow templates, create workflow
ms.date: 10/15/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Create workflows from workflow templates

On the **Workflow** page, you create a workflow by creating a series of workflow steps on the lines. Each step consists of a workflow event (When Event), moderated by event conditions (On Condition), and a workflow response (Then Response), moderated by response options. The fields on workflow lines provide fixed lists of event and response values that represent the scenarios that [!INCLUDE [prod_short](includes/prod_short.md)] supports. Learn more at [Create Workflows](across-how-to-create-workflows.md).

To save you time when you create approval workflows, [!INCLUDE [prod_short](includes/prod_short.md)] provides workflow templates. The templates are available on the **Workflow Templates** page. You can use the templates as they are, or customize them to meet your needs. The codes for the workflow templates from Microsoft are prefixed with **MS-**.

[!INCLUDE [workflow-next-step](includes/workflow-next-step.md)]

If you change a workflow template, but later regret the change, use the **Reset Microsoft Templates** action to revert to the original setting for the workflow.

> [!CAUTION]
> The **Reset Microsoft Templates** action resets all of the Microsoft workflow templates. You can't reset a single template.  

Another way to quickly create a workflow is to import it, for example, if you exported it from another instance of [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Export and Import Workflows](across-how-to-export-and-import-workflows.md).  

## To create a workflow from a workflow template

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, then choose the related link.  
2. Choose the **New Workflow from Template** action. The **Workflow Templates** page opens.  
3. Select a workflow template, then choose **OK**.  

   The **Workflow** page opens for a new workflow containing all the information of the selected template. The value in the **Code** field is extended with, for example, "-01" to indicate that this is the first workflow created from the workflow template.  
4. To customize the workflow, edit the workflow steps or add new steps. Learn more at [Create Workflows](across-how-to-create-workflows.md).  

## Related information

[Create Approval Workflows](across-how-to-create-workflows.md)  
[Export and Import Approval Workflows](across-how-to-export-and-import-workflows.md)  
[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)  
[Delete Approval Workflows](across-how-to-delete-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Set Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
