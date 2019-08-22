---
title: Connect Your Data with Flow| Microsoft Docs
description: You can make your Business Central data available as a data source and specify an OData URL of your web services to build an automated workflow.
documentationcenter: ''
author: bmeier90

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.keywords: workflow, Odata, Power App, SOAP
ms.date: 08/22/2019
ms.author: bmeier
---

# Using [!INCLUDE[d365fin](includes/d365fin_md.md)] in an Automated Workflow
You can use your [!INCLUDE[d365fin](includes/d365fin_md.md)] data as part of a workflow in Microsoft Flow.

> [!NOTE]
> In addition to Microsoft Flow, you can use the Workflow functionality within [!INCLUDE[d365fin](includes/d365fin_md.md)]. Note that although they are two separate workflow systems, any Flow template that you create with Microsoft Flow is added to the list of workflow templates within [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Workflow](across-workflow.md).  

> [!NOTE]  
> You must have a valid account with [!INCLUDE[d365fin](includes/d365fin_md.md)] and with Flow.  

## To add [!INCLUDE[d365fin](includes/d365fin_md.md)] as a data source in Flow
1. In your browser, navigate to [flow.microsoft.com](https://flow.microsoft.com/en-us/), and then sign in.
2. Choose **My Flows** from the ribbon at the top of the page.
3. There are 3 ways to create a Flow; **Start from template**, **Start from blank**, and **Start from a Connector**. A template is a predefined Flow that has been created for you. To use a template, simply select it and create a connection for each service the template uses. With the **Start from blank** and **Start from a connector** options, you can create a new Flow completely from scratch.
4. To create from blank, on the **My Flows** page, choose the **Start from blank** and **Automated flow** options.
5. Search for **Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]** connector.
6. Define a name and choose the trigger you want to use for your Flow.
6. From the list of available triggers, select one of the [!INCLUDE[d365fin](includes/d365fin_md.md)] triggers available:  
    
    *When a vendor approval is requested*,  
    *When a general journal line approval is requested*, 
    *When a record is deleted*,
    *When a record is changed*,
    *When a record is created*,
    *When a record is modified*,
    *When a general journal batch approval is requested*,
    *When a customer approval is requested*,
    *When an item approval is requested*,
    *When a purchase document approval is requested*, or  
    *When a sales document approval is requested*.
7. Flow will prompt you to select an environment and company within your [!INCLUDE[d365fin](includes/d365fin_md.md)] tenant, as well as any conditions in your data that you want to listen for.

> [!NOTE]  
>   The [!INCLUDE[d365fin](includes/d365fin_md.md)]connector for Microsfot Flow supports multile production and sandbox environments. If you have not created multiple production or sandbox environments, **Production** will be the only available option to select. 

At this point, you have successfully connected to your Business Central data and are ready to begin building your flow.

8. To create from a template, choose the **Start from template** option.
9. Search for **Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]** templates.
10. From the list of available templates, select one of the templates, and then choose **Create**.  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] sales order*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] sales quote*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] sales invoice*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] sales credit memo*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] customer*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] purchase order*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] purchase invoice*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] purchase credit memo*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] item*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] vendor*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] general journal batch*,  
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] general journal lines*.  
11. Flow will display a list of services used in the Flow temmplate and will attempt to connect automatically to those services. If you have not previously connected to a service, you will be prompted to sign in to each of the services you need to connect to. A green checkmark will appear next to each service once a connection has been successfully made. Select **Continue**.
12. Flow will prompt you to select an environment and company within your [!INCLUDE[d365fin_md](includes/d365fin_md.md)] tenant. Because each step in the flow is independent of the next, you may be required to define the environment and company multiple times when using a [!INCLUDE[d365fin_md](includes/d365fin_md.md)] Flow template.

For more information, see the [Flow Documentation](https://docs.microsoft.com/en-us/flow/getting-started).

For troubleshooting your Microsoft Flow, see [Troubleshooting Integration with Microsoft Flow](across-troubleshooting-how-use-financials-data-source-flow.md).

## See Also
[Getting Started](product-get-started.md)  
[Workflow](across-workflow.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Managing Users and Permissions](ui-how-users-permissions.md)   
[Manage [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] Workflows](across-use-workflows.md)  
[Approval User Setup](across-how-to-set-up-approval-users.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  
