---
title: Using Dynamics 365 for Financials in Microsoft Flow | Microsoft Docs
description: You can make your Financials data available as a data source in Power Apps.
documentationcenter: ''
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: workflow, Odata, Power App, SOAP 
ms.date: 03/15/2017
ms.author: edupont

---
# Using Dynamics 365 for Financials in Microsoft Flow
You can use your [!INCLUDE[d365fin](includes/d365fin_md.md)] data as part of a workflow in Microsoft Flow.  

**Note**: You must have a valid account with [!INCLUDE[d365fin](includes/d365fin_md.md)] and with Flow.  

## To add [!INCLUDE[d365fin](includes/d365fin_md.md)] as a data source in Flow
1. In your browser, navigate to [flow.microsoft.com](https://flow.microsoft.com/en-us/), and then sign in.
2. Choose **My Flows** from the ribbon at the top of the page.
3. In the **My Flows** window, choose the **Create from blank** option.
4. From the list of available triggers, select one of the two [!INCLUDE[d365fin](includes/d365fin_md.md)] triggers available: *When a record is created*, or *When a record is modified*.
5. Flow will display a connection page that prompts you for the information that is required to connect to your [!INCLUDE[d365fin](includes/d365fin_md.md)] data. To connect, you must specify a name for the connection, an OData URL, username, password, and company name.

   For the *OData URL*, you can copy the OData V4 URL of any of the web services that are listed in the **Web Services** page in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as `https://mycompany.financials.dynamics.com:7048/MS/ODataV4/`.  

   For the *Company Name*, use the name that is shown in the **Name** field in the **Company Information** window in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If your [!INCLUDE[d365fin](includes/d365fin_md.md)] contains multiple companies, choose the relevant company name from the list in the **Companies** window. In both cases, make sure that the name that you specify in the PowerApps wizard matches exactly the text shown in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as `My Company`.

   For the username and password, use the name and web service access key that are specified for your account in the **Users** window in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, your username is *ADMIN*, and the web service access key that serves as your password is *EgzeUFQ9Uv0o5O0lUMyqCzo1ueUW9yRF3SsLU=*. For more information, see [How to: Manage Users and Permissions](ui-how-users-permissions.md).
6. Choose the **Create** button at the bottom of the page to continue.

   Flow will show a list of tables that are available from [!INCLUDE[d365fin](includes/d365fin_md.md)]. These tables, or end points, represent all the web services that you have published from [!INCLUDE[d365fin](includes/d365fin_md.md)].

   Alternatively, create a new web service URL in [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Create Data Set** action in the **Web Services** page, using the **Set Up Reporting** Assisted Setup guide, or by choosing the **Edit in Excel** action in any lists.
7. Choose the data that you want to use for in Flow.

At this point, you have successfully connected to your Dynamics 365 data and are ready to begin building your flow. For more information, see the [Flow documentation](https://flow.microsoft.com/documentation/getting-started/).

## See Also
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Importing Business Data from Other Finance Systems](upload-data.md)  
[How to: Manage Users and Permissions](ui-how-users-permissions.md)    
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  
