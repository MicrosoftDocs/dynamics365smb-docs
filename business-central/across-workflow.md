---
title: Workflows in Dynamics 365 Business Central
description: Use built-in workflow capabilities to set up approval workflows to supplement automated workflows based on Power Automate.
author: jswymer
ms.author: jswymer
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
ms.search.keywords: workflows, approval workflows, approval workflow, automate 
ms.topic: article
ms.date: 10/22/2025
ms.custom: bap-template 
---

# Workflows in Business Central

You can set up and use workflows to connect business-process tasks performed by different users. System tasks, such as automatic posting, can be included as steps in workflows. System tasks can be preceded or followed by user tasks. Requesting and granting approval to create new records are typical workflow steps.

The default version of [!INCLUDE [prod_short](includes/prod_short.md)] supports these types of workflows:
  
* Power Automate flows

  * Automated flows that are triggered by events (such as record or document creation, modification, or deletion) in [!INCLUDE[prod_short](includes/prod_short.md)]. Also included are approval flows created in Power Automate that trigger when an approval is requested in [!INCLUDE[prod_short](includes/prod_short.md)].
  * Instant flows that are manually triggered from the **Automate** action menu on lists, cards, and document pages.

    Create and manually trigger a Power Automate flow on a [!INCLUDE[prod_short](includes/prod_short.md)] record, such as a customer, item, or sales order, with options to manipulate information both internally and externally (using integrated tools).

* Approval workflows based on built-in workflow templates

  On the **Workflow Templates** page, you can see all available workflows. The trial version of [!INCLUDE[prod_short](includes/prod_short.md)] includes many preconfigured workflows represented by workflow templates you can copy to create new ones. When you open a template from the **Workflow Templates** page, and the workflow name starts with *MS-*, then the template was added by Microsoft.

## Power automate flows

With [!INCLUDE [prod_short](includes/prod_short.md)] online, you can sign up for Power Automate to build powerful automated workflows. You run those workflows from inside [!INCLUDE [prod_short](includes/prod_short.md)]. The flows can connect internal and external data sources and tools, without coding knowledge.

|To... |Go to...|
|-------|-------|
|Get started with Power Automate, creating flows, and running instant flows|[Use Power Automate Flows in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-financials-data-source-flow.md)|
|Learn details of how to create, edit, and manage flows|[Set Up Automated Flows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) and [Set Up Instant Flows](/dynamics365/business-central/dev-itpro/powerplatform/instant-flows)|
|Set up Power Automate integration with [!INCLUDE[prod_short](includes/prod_short.md)] for users as an admin|[Set Up Power Automate Integration](/dynamics365/business-central/dev-itpro/powerplatform/power-automate-setup)|

## Approval workflows

Create an approval workflow by defining what starts the workflow and what happens next, as follows:

* A workflow event, which is moderated by event conditions.
* A workflow response, which is moderated by response options.

To define workflow steps, fill in fields on workflow lines using the event and response values that represent supported scenarios.

Examples of approval workflow events include the creation of sales or purchase orders/quotes/invoices, price changes, vendor or customer edits, and more.

[!INCLUDE[workflow](includes/workflow.md)]

| To... | Go to... |
|--|--|
| Set up approval workflow users, specify how users get notified, and create new workflows. (To create new workflows for unsupported scenarios, implement the required workflow elements by customizing the application code.) | [Set Up Approval Workflows](across-set-up-workflows.md) |
| Enable approval workflows, act on workflow notifications, including requesting and approving a workflow step. Archive and delete workflows. | [Use Approval Workflows](across-use-workflows.md) |

<!--
| Integrate company data with Power Automate workflows, using both internal and external sources and events to create and automate tasks or workflows. | [Use Power Automate Flows in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-financials-data-source-flow.md) |-->

## Related information

[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Manage Projects](projects-manage-projects.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Troubleshoot Your [!INCLUDE[prod_short](includes/prod_short.md)] Automated Workflows](across-flow-troubleshoot.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
