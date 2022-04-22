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

For [!INCLUDE [prod_short](includes/prod_short.md)] online, starting in April 2022, an admin can [switch on a feature](admin-feature-management.md) to make it possible to run a Power Automate flow from most pages. For more information, see [Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows) in the administration content.  

Once the admin has connected [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate, you'll see any flows that your organization has added when they choose the **Automate** action in the relevant pages. You can run the flows without leaving [!INCLUDE [prod_short](includes/prod_short.md)].  

> [!NOTE]  
> You must have a valid account with [!INCLUDE[prod_short](includes/prod_short.md)] and with Power Automate.  

> [!TIP]
> In addition to Power Automate, you can use approval workflow functionality within [!INCLUDE[prod_short](includes/prod_short.md)]. Note that although they are two separate workflow systems, any approval workflow template that you create with Power Automate is added to the list of workflows within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Approval Workflows](across-workflow.md).  

You can create workflows at the [powerautomate.microsoft.com](https://powerautomate.microsoft.com) website. However, if your admin has switched on the capability for running Power Automate flows from inside [!INCLUDE [prod_short](includes/prod_short.md)], you can start the process of building a flow from the **Automate** action on the relevant pages. In that case, the connection is already set up for you.  

Microsoft provides a number of predefined triggers, including the following:  

- *When a vendor approval is requested*  
- *When a general journal line approval is requested*  
- *When a record is deleted*
- *When a record is changed*
- *When a record is created*
- *When a record is modified*
- *When a general journal batch approval is requested*  
- *When a customer approval is requested*
- *When an item approval is requested*
- *When a purchase document approval is requested*
- *When a sales document approval is requested*

Microsoft also provides predefined templates, including the following:

- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] sales order*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] sales quote*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] sales invoice*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] sales credit memo*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] customer*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] purchase order*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] purchase invoice*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] purchase credit memo*  
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] item*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] vendor*
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] general journal batch*  
- *Request Approval for Microsoft [!INCLUDE[prod_long](includes/prod_long.md)] general journal lines*

Power Automate shows a list of services used in the flow template and will attempt to connect automatically to those services. If you haven't previously connected to a service, you'll be prompted to sign in to each of the services you need to connect to. A green checkmark will appear next to each service once a connection has been successfully made. Select **Continue**.

Power Automate will prompt you to select an environment and company within your [!INCLUDE[prod_short](includes/prod_short.md)] tenant. Because each step in the flow is independent of the next, you may be required to define the environment and company multiple times when using a [!INCLUDE[prod_short](includes/prod_short.md)] Power Automate template.

For more information, see the [Power Automate Documentation](/power-automate/getting-started).

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