---
title: Use Your Data to Create an App| Microsoft Docs
description: You can make your Financials data available as a data source and specify an OData URL of your web services to build a business app using PowerApps.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Odata, Power App, SOAP
ms.date: 06/02/2017
ms.author: edupont

---
# Connecting to Your Financials Data to Build a Business App Using PowerApps
You can make your [!INCLUDE[d365fin](includes/d365fin_md.md)] data available as a data source in PowerApps.  

> [!NOTE]  
>   You must have a valid account with [!INCLUDE[d365fin](includes/d365fin_md.md)] and with PowerApps.  

## To add [!INCLUDE[d365fin](includes/d365fin_md.md)] as a data source in PowerApps
1. In your browser, navigate to [powerapps.microsoft.com](https://powerapps.microsoft.com/en-us/), and then sign in.
2. In the left navigation pane, choose **New App**.
3. Choose your editor, PowerApps Studio for Windows or PowerApps Studio for Web.

   PowerApps Studio for Windows is a desktop application used to create and publish PowerApps. The PowerApps Studio for Web is the online solution used to create and publish PowerApps.
4. The next step to create a PowerApp is to select your data. Choose the Arrow icon then choose the **New connection** option in the upper left side of the page.
5. In the list of available connections, choose **Dynamics 365 Business Central**.
6. PowerApps will display a connection page that prompts you for the information that is required to connect to your [!INCLUDE[d365fin](includes/d365fin_md.md)] data. To connect, you must specify an OData URL, username, password, and company name.

   For the *OData URL*, you can copy the OData V4 URL of any of the web services that are listed in the **Web Services** page in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as `https://mycompany.financials.dynamics.com:7048/MS/ODataV4/`.  

   For the *Company Name*, use the name that is shown in the **Name** field in the **Company Information** window in [!INCLUDE[d365fin](includes/d365fin_md.md)]. If your [!INCLUDE[d365fin](includes/d365fin_md.md)] contains multiple companies, choose the relevant company name from the list in the **Companies** window. In both cases, make sure that the name that you specify in the PowerApps wizard matches exactly the text shown in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as `My Company`.

   For the username and password, use the name and web service access key that are specified for your account in the **Users** window in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, your username is *ADMIN*, and the web service access key that serves as your password is *EgzeUFQ9Uv0o5O0lUMyqCzo1ueUW9yRF3SsLU=*.
7. Choose the **Connection** button to continue. PowerApps will display a default dataset for [!INCLUDE[d365fin](includes/d365fin_md.md)]. Choose the **Default** dataset.

   PowerApps will display a list of tables that are available from [!INCLUDE[d365fin](includes/d365fin_md.md)]. These tables, or end points,  represent all the web services you have published from [!INCLUDE[d365fin](includes/d365fin_md.md)].

   Alternatively, create a new web service URL in [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Create Data Set** action in the **Web Services** page, using the **Set Up Reporting** Assisted Setup guide, or by choosing the **Edit in Excel** action in any lists.
8. Choose the table that you want to use for your PowerApp, and then choose the **Connect** button.
9. Repeat the previous steps to add additional [!INCLUDE[d365fin](includes/d365fin_md.md)] data to your Power BI data model.

   > [!NOTE]  
   >    Once you have successfully connected to [!INCLUDE[d365fin](includes/d365fin_md.md)], you will not be prompted again for the OData URL, username, or password.

At this point, you have successfully connected to your Business Central data and are ready to begin building your PowerApp. For more information, see the [PowerApps documentation](https://powerapps.microsoft.com/tutorials/getting-started/).

## See Also
[Getting Started](product-get-started.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  
