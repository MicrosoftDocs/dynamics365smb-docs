---
title: Set up Reporting for Dynamics 365 in Power BI | Microsoft Docs
description: You can make your Financials data available as a data source in Power BI and build powerful reports of the state of your business.
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 12/19/2017
ms.author: edupont

---
# Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as Power BI Data Source for Building Reports
You can make your [!INCLUDE[d365fin](includes/d365fin_md.md)] data available as a data source in Power BI and build powerful reports of the state of your business.  

To set up a connection to Power BI, you must have the following:  

* Access to [!INCLUDE[d365fin](includes/d365fin_md.md)].  
* The OData endpoint for your [!INCLUDE[d365fin](includes/d365fin_md.md)] data. You can get this by copying the value of the **OData V4 URL** field in the **Web Services** window in [!INCLUDE[d365fin](includes/d365fin_md.md)].  
* The username and web service key for the account that you want to use for this connection. This can be your own account or that of another user. You can get this data from the **User** card in [!INCLUDE[d365fin](includes/d365fin_md.md)].  
* Access to Power BI. For more information, see [Power BI](https://powerbi.microsoft.com).  
* Power BI Desktop installed. For more information, see [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).  

## To connect to your [!INCLUDE[d365fin](includes/d365fin_md.md)] in Power BI Desktop
1. In Power BI Desktop, in the left navigation pane, choose **Get Data**.
2. In the **Get Data** window, choose **Online Services**, choose **Dynamics 365 for Financials**, and then choose the **Connect** button.

   Power BI displays a wizard that will guide you through the [connection process](across-how-to-connect-powerbi-dynamics-365-content-packs-help.md). The first step will be to sign into the service. Select **Sign in** and choose the account you would like to sign in as. This should be the same account you sign into [!INCLUDE[d365fin](includes/d365fin_md.md)] with. 

3. Choose the **Connect** button to continue. The Power BI wizard shows a list of [!INCLUDE[d365fin](includes/d365fin_md.md)] companies and data sources. These data source represent all the web services that you have published from each company in [!INCLUDE[d365fin](includes/d365fin_md.md)].

## To build your Power BI report
1. In the **Navigator** window, choose your data set.  
2. Specify the data you want to add to your data model, and then choose the **Load** button.
3. Repeat the previous steps to add additional [!INCLUDE[d365fin](includes/d365fin_md.md)] data to your Power BI data model.

   > [!NOTE]  
>    Once you have successfully connected to [!INCLUDE[d365fin](includes/d365fin_md.md)], you will not be prompted again to sign in.

When the file has been published, you will get a link to open the report in Power BI. Optionally, return to Power BI Desktop and enhance your first report. For more information, see the [Power BI documentation](https://powerbi.microsoft.com/documentation/powerbi-landing-page/).

## See Also
[Business Intelligence](bi.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Importing Business Data from Other Finance Systems](upload-data.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)   
[Finance](finance.md)  
[Connecting Power BI to [!INCLUDE[d365fin](includes/d365fin_md.md)]](across-how-to-connect-powerbi-dynamics-365-content-packs-help.md)  
