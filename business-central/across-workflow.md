---
title: Workflows in Dynamic 365 Business Central
description: Use the built-in workflow capabilities to set up approval workflows to supplement automated workflows based on Power Automate. You can set up steps to assign tasks to different people as part of the different business-process tasks. 
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 05/12/2022
ms.author: edupont

---
# Workflows in Dynamics 365 Business Central

You can set up and use workflows that connect business-process tasks performed by different users. System tasks, such as automatic posting, can be included as steps in workflows, preceded or followed by user tasks. Requesting and granting approval to create new records are typical workflow steps.  

The default version of [!INCLUDE [prod_short](includes/prod_short.md)] supports three types of workflows:

* Automated approval workflows based on built-in workflow templates  

  On the **Workflow Templates** page, you can see all available workflows. The trial version of [!INCLUDE[prod_short](includes/prod_short.md)] includes a number of pre-configured workflows represented by workflow templates that you can copy to create workflows. When you open a workflow template from the **Workflow Templates** page, and the workflow's name starts with *MS-*, then the workflow template is added by Microsoft.  
* Automated flows that you set up yourself  

  Any workflow template that you create with Power Automate is added to the list of workflow templates within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Use Business Central in Power Automate Flows](across-how-use-financials-data-source-flow.md).  
* Manually triggered flows from the **Automate** action ([!INCLUDE [prod_short](includes/prod_short.md)] online only). For more information, see [Manual instant flows](across-how-use-financials-data-source-flow.md#manual-instant-flows).  

## Power Automate flows

For [!INCLUDE [prod_short](includes/prod_short.md)] online, you can sign up for Power Automate and then build powerful automated flows that you can run from inside [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate Flows](across-how-use-financials-data-source-flow.md).  

## Automated approval workflows

You create an approval workflow by listing the involved steps on the lines. Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options. You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code.  

If a business scenario requires a workflow event or response that is not supported in the default version, sign up for Power Automate. For more information, see [Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate Flows](across-how-use-financials-data-source-flow.md). Alternatively, get an app or work with a Microsoft partner to customize the application code.  

To set up and use workflows that are not defined in Power Automate, check the following articles:  

|**To**|**See**|  
|------------|-------------|  
|Set up workflow users, specify how users get notified, and create new workflows. For new workflows for unsupported scenarios, implement the required workflow elements by customizing the application code.|[Set Up Workflows](across-set-up-workflows.md)|  
|Enable workflows, act on workflow notifications, including request approvals and approve requests to perform a workflow step. Archive and delete workflows.|[Use Workflows](across-use-workflows.md)|  

## See Also

[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Managing Projects](projects-manage-projects.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate Flows](across-how-use-financials-data-source-flow.md)  
[Troubleshoot Your [!INCLUDE[prod_short](includes/prod_short.md)] Automated Workflows](across-flow-troubleshoot.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]