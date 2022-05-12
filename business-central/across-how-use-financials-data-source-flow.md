---
title: Use Business Central in Power Automate Flows
description: Set up and use Power Automate flows that creates or modifies Business Central data.

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, OData, Power App, SOAP, Entity set not found, workflowWebhookSubscriptions
ms.date: 05/12/2022
ms.author: edupont
author: jswymer
---

# Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate Flows

You can use your [!INCLUDE[prod_short](includes/prod_short.md)] data as part of a workflow in Microsoft Power Automate. Create your own flows and connect to your data with the [!INCLUDE [prod_short](includes/prod_short.md)] connector.  

> [!NOTE]  
> You must have a valid account with [!INCLUDE[prod_short](includes/prod_short.md)] and with Power Automate.  

> [!TIP]
> In addition to Power Automate, you can use approval workflow templates in [!INCLUDE[prod_short](includes/prod_short.md)]. Although they are two separate workflow systems, any approval workflow template that you create with Power Automate is added to the list of workflows within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Workflows](across-workflow.md).  

## Automated workflows

With Power Automate, you can create business flows directly in-house and rely on citizen developers​. For more information, see [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) in the administration content.  

## Manual instant flows

Starting in May 2022, an admin of [!INCLUDE [prod_short](includes/prod_short.md)] online can [switch on a feature](admin-feature-management.md) to make it possible to run a Power Automate flow from most pages. For more information, see [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) in the administration content.  

Once the admin has connected [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate, you'll see any flows that your organization has added when you choose the **Automate** action in the relevant pages. You run the flows without leaving [!INCLUDE [prod_short](includes/prod_short.md)].  

These automated workflows open in a pane inside [!INCLUDE [prod_short](includes/prod_short.md)] online so that you remain within context of the business process you were in the middle of. In some pages, the **Automate** action hides under the **More Options** menu, but find it, choose the **Power Automate** menu item, and then choose the relevant link to trigger the workflow. The connection to Power Automate is already set up for you.  

Most flows will require you to fill in a field or two before you choose the **Run flow** action.  

> [!TIP]
> If you don't see an **Automate** action, then your [!INCLUDE [prod_short](includes/prod_short.md)] probably hasn't yet been set up to use Power Automate. For more information, ask your admin.

## Add more automated flows and manual instant flows

You can create flows at the [powerautomate.microsoft.com](https://powerautomate.microsoft.com) website. However, if your admin has switched on the capability to run Power Automate flows from inside [!INCLUDE [prod_short](includes/prod_short.md)] online, you can start the process of building a flow from the **Automate** action on the relevant pages. In some pages, the **Automate** action hides under the **More Options** menu, but find it, choose the **Power Automate** menu item, and then choose the **Create a flow** action. Power Automate then opens in a new browser tab, and you're signed in automatically.

## Manage workflows

You can get an overview of all workflows that you have access to by choosing the **Manage workflows** action in the **Power Automate** menu. The list opens in a new browser tab, and you signed in to Power Automate automatically. There, you can see when each flow ran most recently.  

## See Also

[Troubleshoot Your [!INCLUDE[prod_short](includes/prod_short.md)] Automated Workflows](across-flow-troubleshoot.md)  
[Get Ready for Doing Business](ui-get-ready-business.md)  
[Workflows](across-workflow.md)  
[Import Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  
[Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows)  

[!INCLUDE[footer-include](includes/footer-banner.md)]