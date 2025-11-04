---
title: How to export and import approval workflows
description: Export and import workflows to easily transfer them between Business Central databases and streamline the creation of new workflows.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export approval workflow, import approval workflow, export workflow, import workflow, 
ms.date: 10/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export and import approval workflows

To transfer workflows to other [!INCLUDE[prod_short](includes/prod_short.md)] databases, for example to save time when creating new workflows, you can export and import workflows.  

Another way to quickly create workflows is to use workflow templates. Learn more at [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).  

On the **Workflow** page, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines using fixed lists of event and response values representing scenarios supported by the application code. Learn more at [Create Workflows](across-how-to-create-workflows.md).  

## Export a workflow

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, then choose the related link.  
2. Select a workflow, then choose the **Export to File** action.  

## Import a workflow

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, then choose the related link.  
2. Choose the **Import from File** action.  
3. On the **Import** page, select **Choose**, choose the XML file containing the workflow, then select **Open**.  

> [!CAUTION]  
> If the workflow code already exists in the database, the workflow steps are overwritten with the steps in the imported workflow.  

## Related information

[Create Approval Workflows](across-how-to-create-workflows.md)  
[Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md)  
[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md)  
[Delete Approval Workflows](across-how-to-delete-workflows.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Set Up Approval Workflows](across-set-up-workflows.md)  
[Use Approval Workflows](across-use-workflows.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
