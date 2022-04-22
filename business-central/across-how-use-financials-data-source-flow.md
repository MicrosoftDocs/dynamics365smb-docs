---
title: Connect Your Data with Power Automate
description: You can make your Business Central data available as a data source and specify an OData URL of your web services to build an automated workflow.

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, OData, Power App, SOAP, Entity set not found, workflowWebhookSubscriptions
ms.date: 04/22/2022
ms.author: edupont
author: jswymer
---

# Use [!INCLUDE[prod_short](includes/prod_short.md)] in an Automated Workflow

You can use your [!INCLUDE[prod_short](includes/prod_short.md)] data as part of a workflow in Microsoft Power Automate.  

For [!INCLUDE [prod_short](includes/prod_short.md)] online, starting in May 2022, an admin can [switch on a feature](admin-feature-management.md) to make it possible to run a Power Automate flow from most pages. For more information, see [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) in the administration content.  

Once the admin has connected [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate, you'll see any flows that your organization has added when they choose the **Automate** action in the relevant pages. You can run the flows without leaving [!INCLUDE [prod_short](includes/prod_short.md)].  

> [!NOTE]  
> You must have a valid account with [!INCLUDE[prod_short](includes/prod_short.md)] and with Power Automate.  

> [!TIP]
> In addition to Power Automate, you can use approval workflow functionality within [!INCLUDE[prod_short](includes/prod_short.md)]. Note that although they are two separate workflow systems, any approval workflow template that you create with Power Automate is added to the list of workflows within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Approval Workflows](across-workflow.md).  

## Automated workflows

Many pages have an **Automate** action. This action gives you access to workflows that your admin, another user, or Microsoft has defined as relevant for that page. These automated workflows open in a pane inside [!INCLUDE [prod_short](includes/prod_short.md)] so that you remain within context of the business process you were in the middle of. Just choose the relevant link to trigger the workflow. The connection to Power Automate is already set up for you.  

Most flows will require you to fill in a field or two before you choose the **Run flow** action.  

> [!TIP]
> If you don't see an **Automate** action, then your [!INCLUDE [prod_short](includes/prod_short.md)] has not yet been set up to use Power Automate. For more information, ask your admin.

## Add workflows

You can create workflows at the [powerautomate.microsoft.com](https://powerautomate.microsoft.com) website. However, if your admin has switched on the capability for running Power Automate flows from inside [!INCLUDE [prod_short](includes/prod_short.md)], you can start the process of building a flow from the **Automate** action on the relevant pages. Just choose the **Power Automate** menu item, and then choose the **Create a flow** action to connect to Power Automate.

With Power Automate, you can create business flows directly in-house and rely on citizen developers​. You can also connect to various cloud services:​

- Dataverse  
- Outlook  
- Teams  
- Approvals  
- Excel  
- SharePoint  
- Connectors to third party services  

Starting in April 2022, the updated Business Central connector for Power Automate​ gives you even more power:

- Filter to a specific page or table  ​
- Pass context or parameters to Power Automate​  

  - Environment name, such as PRODUCTION​  
  - Company ID, such as Contoso​  
  - Table ID, such as the table underlying the current page​  
  - System ID, such as a specific record ID​  
  - Page ID, meaning the page that the flow was triggered from  
  - WebClientURL to open a specific page object
- Enhance user experience with additional input  

## Manage workflows

You can get an overview of all workflows that you have access to by choosing the **Manage workflows** action in the **Power Automate** menu.  

## Troubleshooting

When you connect [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate to create automated workflows, you might run into error messages. For more information, see [Troubleshoot your [!INCLUDE[prod_short](includes/prod_short.md)] Automated Workflows](across-flow-troubleshoot.md).  

## See Also

[Get Ready for Doing Business](ui-get-ready-business.md)  
[Workflow](across-workflow.md)  
[Import Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Manage [!INCLUDE[prod_long](includes/prod_long.md)] Workflows](across-use-workflows.md)  
[Approval User Setup](across-how-to-set-up-approval-users.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]