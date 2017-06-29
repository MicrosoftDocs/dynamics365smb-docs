---
title: "How to: Export and Import Workflows"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: b5b2c75c-fb36-44d8-86c4-5fe6c1decc8c
caps.latest.revision: 2
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
# How to: Export and Import Workflows
To transfer workflows to other FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] --> databases, for example to save time when creating new workflows, you can export and import workflows.  
  
 Another way to quickly create workflows is to create workflows from workflow templates. For more information, see [How to: Create Workflows from Workflow Templates](../../BusinessFunctionality/Workflow/how-to-create-workflows-from-workflow-templates.md).  
  
 In the **Workflow** window, you create a workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code. For more information, see [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md).  
  
### To export a workflow  
  
1.  In the **Search** box, enter **Workflows**, and then choose the related link.  
  
2.  Select a workflow, and then, on the **Actions** tab, in the **General** group, choose **Export to File**.  
  
3.  In the **Export File** window, choose the **Save** button.  
  
4.  In the **Export** window, select a file location, and then choose the **Save** button.  
  
### To import a workflow  
  
1.  In the **Search** box, enter **Workflows**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **General** group, choose **Import from File**.  
  
3.  In the **Import** window, choose the XML file that contains the workflow, and then choose the **Open** button.  
  
    > [!CAUTION]  
    >  If the workflow code already exists in the database, the workflow steps will be overwritten with the steps in the imported workflow.  
  
## See Also  
 Workflow   
 Workflow Templates   
 Workflow Response Options   
 Notification Entries   
 [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)   
 [How to: Create Workflows from Workflow Templates](../../BusinessFunctionality/Workflow/how-to-create-workflows-from-workflow-templates.md)   
 [How to: View Archived Workflow Step Instances](../../BusinessFunctionality/Workflow/how-to-view-archived-workflow-step-instances.md)   
 [How to: Delete Workflows](../../BusinessFunctionality/Workflow/how-to-delete-workflows.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Set Up Workflows](../../BusinessFunctionality/Workflow/set-up-workflows.md)   
 [Use Workflows](../../BusinessFunctionality/Workflow/use-workflows.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)