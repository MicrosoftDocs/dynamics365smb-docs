---
title: Connect Your Data with Power Automate| Microsoft Docs
description: You can make your Business Central data available as a data source and specify an OData URL of your web services to build an automated workflow.
author: bmeier90

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.keywords: workflow, OData, Power App, SOAP
ms.date: 04/01/2020
ms.author: bmeier
---

# Using [!INCLUDE[prodshort](includes/prodshort.md)] in an Automated Workflow

You can use your [!INCLUDE[prodshort](includes/prodshort.md)] data as part of a workflow in Microsoft Power Automate.

> [!NOTE]
> In addition to Power Automate, you can use the Workflow functionality within [!INCLUDE[prodshort](includes/prodshort.md)]. Note that although they are two separate workflow systems, any workflow template that you create with Power Automate is added to the list of workflows  within [!INCLUDE[prodshort](includes/prodshort.md)]. For more information, see [Workflow](across-workflow.md).  

> [!NOTE]  
> You must have a valid account with [!INCLUDE[prodshort](includes/prodshort.md)] and with Power Automate.  

## To add [!INCLUDE[prodshort](includes/prodshort.md)] as a data source in Power Automate

1. In your browser, navigate to [flow.microsoft.com](https://flow.microsoft.com), and then sign in.
2. Choose **My flows** from the ribbon at the top of the page.
3. There are 3 ways to create a flow; **Start from template**, **Start from blank**, and **Start from a connector**. A template is a predefined flow that has been created for you. To use a template, simply select it and create a connection for each service the template uses. With the **Start from blank** and **Start from a connector** options, you can create a new flow completely from scratch.
4. To create from blank, on the **My flows** page, choose the **Start from blank** and **Automated flow** options.
5. Search for **Microsoft [!INCLUDE[prodlong](includes/prodlong.md)]** connector.
6. Define a name and choose the trigger you want to use for your flow.
7. From the list of available triggers, select one of the [!INCLUDE[prodshort](includes/prodshort.md)] triggers available:  

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

8. Power Automate will prompt you to select an environment and company within your [!INCLUDE[prodshort](includes/prodshort.md)] tenant, as well as any conditions in your data that you want to listen for.

    > [!NOTE]
    > The [!INCLUDE[prodshort](includes/prodshort.md)] connector for Power Automate supports multiple production and sandbox environments. If you have not created multiple production or sandbox environments, **Production** is the only available option that you can choose.  

    At this point, you have successfully connected to your Business Central[!INCLUDE [prodshort](includes/prodshort.md)] data and are ready to begin building your flow.

9. To create from a template, choose the **Start from template** option.
10. Search for **Microsoft [!INCLUDE[prodlong](includes/prodlong.md)]** templates.
11. From the list of available templates, select one of the templates, and then choose **Create**.  

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
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] general journal batch*, or    
    *Request Approval for Microsoft [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] general journal lines*.  
12. Power Automate will display a list of services used in the flow template and will attempt to connect automatically to those services. If you have not previously connected to a service, you will be prompted to sign in to each of the services you need to connect to. A green checkmark will appear next to each service once a connection has been successfully made. Select **Continue**.
13. Power Automate will prompt you to select an environment and company within your [!INCLUDE[prodshort](includes/prodshort.md)] tenant. Because each step in the flow is independent of the next, you may be required to define the environment and company multiple times when using a [!INCLUDE[prodshort](includes/prodshort.md)] Power Automate template.

For more information, see the [Power Automate Documentation](/power-automate/getting-started).

## See Also

[Getting Started](product-get-started.md)  
[Workflow](across-workflow.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Manage [!INCLUDE[prodlong](includes/prodlong.md)] Workflows](across-use-workflows.md)  
[Approval User Setup](across-how-to-set-up-approval-users.md)  
[Setting Up [!INCLUDE[prodshort](includes/prodshort.md)]](setup.md)  
[Finance](finance.md)  
