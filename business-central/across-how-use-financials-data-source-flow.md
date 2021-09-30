---
title: Connect Your Data with Power Automate| Microsoft Docs
description: You can make your Business Central data available as a data source and specify an OData URL of your web services to build an automated workflow.
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, OData, Power App, SOAP, Entity set not found, workflowWebhookSubscriptions
ms.date: 07/27/2021
ms.author: edupont
author: jswymer
---

# Using [!INCLUDE[prod_short](includes/prod_short.md)] in an Automated Workflow

You can use your [!INCLUDE[prod_short](includes/prod_short.md)] data as part of a workflow in Microsoft Power Automate.

> [!NOTE]
> In addition to Power Automate, you can use the Workflow functionality within [!INCLUDE[prod_short](includes/prod_short.md)]. Note that although they are two separate workflow systems, any workflow template that you create with Power Automate is added to the list of workflows  within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Workflow](across-workflow.md).  

> [!NOTE]  
> You must have a valid account with [!INCLUDE[prod_short](includes/prod_short.md)] and with Power Automate.  

## Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power Automate

1. In your browser, navigate to [flow.microsoft.com](https://flow.microsoft.com), and then sign in.
2. Choose **My flows** from the ribbon at the top of the page.
3. There are 3 ways to create a flow; **Start from template**, **Start from blank**, and **Start from a connector**. A template is a predefined flow that has been created for you. To use a template, select it and create a connection for each service the template uses. With the **Start from blank** and **Start from a connector** options, you can create a new flow completely from scratch.
4. To create from blank, on the **My flows** page, choose the **Start from blank** and **Automated flow** options.
5. Search for **Microsoft [!INCLUDE[prod_long](includes/prod_long.md)]** connector.
6. Define a name and choose the trigger you want to use for your flow.
7. From the list of available triggers, select one of the [!INCLUDE[prod_short](includes/prod_short.md)] triggers available:  

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

8. Power Automate will prompt you to select an environment and company within your [!INCLUDE[prod_short](includes/prod_short.md)] tenant, plus any conditions in your data that you want to listen for.

    > [!NOTE]
    > The [!INCLUDE[prod_short](includes/prod_short.md)] connector for Power Automate supports multiple production and sandbox environments. If you haven't created multiple production or sandbox environments, **Production** is the only available option that you can choose.  

    At this point, you've successfully connected to your Business Central[!INCLUDE[prod_short](includes/prod_short.md)] data and are ready to begin building your flow.

9. To create from a template, choose the **Start from template** option.
10. Search for **Microsoft [!INCLUDE[prod_long](includes/prod_long.md)]** templates.
11. From the list of available templates, select one of the templates, and then choose **Create**.  

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
12. Power Automate will display a list of services used in the flow template and will attempt to connect automatically to those services. If you haven't previously connected to a service, you'll be prompted to sign in to each of the services you need to connect to. A green checkmark will appear next to each service once a connection has been successfully made. Select **Continue**.
13. Power Automate will prompt you to select an environment and company within your [!INCLUDE[prod_short](includes/prod_short.md)] tenant. Because each step in the flow is independent of the next, you may be required to define the environment and company multiple times when using a [!INCLUDE[prod_short](includes/prod_short.md)] Power Automate template.

For more information, see the [Power Automate Documentation](/power-automate/getting-started).

## Troubleshooting

### "Entity set not found” error

#### Problem

When creating a new Power Automate Flow using a [!INCLUDE[prod_short](includes/prod_short.md)] approval trigger, like *When a purchase document approval is requested*, you get an error message similar to:

**Entity set not found: \<name\>**

where **\<name\>** is the service name of the missing web service, like **workflowWebhookSubscriptions** or **workflowPurchaseDocumentLines**.

#### Possible cause

Using Power Automate to integrate with your [!INCLUDE[prod_short](includes/prod_short.md)] approvals requires that certain page and codeunit objects are published as web services. By default, most of the required objects are published as web services for you. But in some cases, your environment may have been customized so that these objects are no longer published.

#### Fix

Go to the **Web Services** page and make sure that the following objects are published as web services. There should be an entry in the list for each object, with the **Published** check box selected. 

|Object Type|Object ID|Object Name|Service Name|
|-----------|---------|-----------|------------|
|Codeunit|	1544	|WorkflowWebhookSubscription|WorkflowActionResponse|
|Page|	6408|	workflowCustomers|	workflowCustomers|
|Page	|6406	|workflowGenJournalBatches|	workflowGenJournalBatches|
|Page	|6407	|workflowGenJournalLines|workflowGenJournalLines|
|Page	|6409	|workflowItems|	workflowItems|
|Page	|6405	|Purchase Document Line Entity|workflowPurchaseDocumentLines|
|Page|	6404	|workflowPurchaseDocuments|	workflowPurchaseDocuments|
|Page|	6403	|Sales Document Line Entity	|workflowSalesDocumentLines|
|Page|	6402|	workflowSalesDocuments|	workflowSalesDocuments|
|Page|	6410	|workflowVendors|	workflowVendors|
|Page|	831	|workflowWebhookSubscriptions|	workflowWebhookSubscriptions|

> [!NOTE]
> The **Service Name** value must be exactly as shown in the table. Don't change or translate the service name.

For more information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

## See Also

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Workflow](across-workflow.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Manage [!INCLUDE[prod_long](includes/prod_long.md)] Workflows](across-use-workflows.md)  
[Approval User Setup](across-how-to-set-up-approval-users.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]