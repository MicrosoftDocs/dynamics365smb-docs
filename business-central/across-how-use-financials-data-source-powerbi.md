---
title: Use Business Central in Power BI reports | Microsoft Docs
description: Make your data available as a data source in Power BI and build powerful reports of the state of your business.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 10/01/2019
ms.author: edupont

---
# Using [!INCLUDE [prodlong](includes/prodlong.md)] as Power BI Data Source for Building Reports

You can make your [!INCLUDE[prodlong](includes/prodlong.md)] data available as a data source in Power BI and build powerful reports of the state of your business.  

You must have a valid account with [!INCLUDE[prodshort](includes/prodshort.md)] and with Power BI. Also, you must download [Power BI Desktop](https://powerbi.microsoft.com/desktop/). For more information, see [Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).  

## To add [!INCLUDE[prodshort](includes/prodshort.md)] as a data source in Power BI Desktop

1. In Power BI Desktop, in the left navigation pane, choose **Get Data**.
2. On the **Get Data** page, choose **Online Services**, choose **Microsoft Dynamics 365 Business Central**, and then choose the **Connect** button.
3. Power BI displays a wizard that will guide you through the connection process. You will be prompted to sign into [!INCLUDE [prodshort](includes/prodshort.md)]. Select **Sign in** and choose the account you would like to sign in as. This should be the same account you sign into [!INCLUDE [prodshort](includes/prodshort.md)] with.
4. Choose the **Connect** button to continue. The Power BI wizard shows a list of Microsoft [!INCLUDE[d365fin](includes/d365fin_md.md)] environments, companies and data sources. These data source represent all the web services that you have published from each tenant/company in [!INCLUDE [prodshort](includes/prodshort.md)].
5. Alternatively, create a new web service URL in [!INCLUDE [prodshort](includes/prodshort.md)] by using the **Create Data Set** action on the **Web Services** page, using the **Set Up Reporting** Assisted Setup guide, or by choosing the **Edit in Excel** action in any lists.
6. Specify the data you want to add to your data model, and then choose the **Load** button.
7. Repeat the previous steps to add additional [!INCLUDE [prodshort](includes/prodshort.md)], or other data, to your Power BI data model.

> [!NOTE]  
> Once you have successfully connected to [!INCLUDE [prodshort](includes/prodshort.md)], you will not be prompted again to sign in.

Once the data is loaded it will appear in the right navigation on the page. At this point, you have successfully connected to your [!INCLUDE [prodshort](includes/prodshort.md)] data and are ready to begin building your Power BI report.  

Before building your report, we recommend that you import the [!INCLUDE [prodshort](includes/prodshort.md)] theme file.  The theme file will create a color palette so that you can build reports with the same color styling as the [!INCLUDE [prodshort](includes/prodshort.md)] apps without requiring you to define custom colors for each visual.

For more information, see the [Power BI documentation](/power-bi/consumer/power-bi-consumer-landing/).

## See Also

[Enabling Your Business Data for Power BI](admin-powerbi.md)  
[Business Intelligence](bi.md)  
[Getting Started](product-get-started.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Finance](finance.md)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
