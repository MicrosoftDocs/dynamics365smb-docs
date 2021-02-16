---
title: Building Reports in Power BI Desktop to Display Business Central Data | Microsoft Docs
description: Make your data available as a data source in Power BI and build powerful reports of the state of your business.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 10/01/2020
ms.author: jswymer
---

# Building Power BI Reports to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data

You can make your [!INCLUDE[prod_long](includes/prod_long.md)] data available as a data source in Power BI Desktop and build powerful reports of the state of your business.

This article describes how to get started using Power BI Desktop to create reports that display [!INCLUDE[prod_long](includes/prod_long.md)] data.  After you create reports, you can publish them to your Power BI service, or share them with all users in your organization. Once these reports are in the Power BI service, users that are set up for it, can then view the reports in [!INCLUDE[prod_long](includes/prod_long.md)].

## Get ready

- Sign up for the Power BI service.

    If you haven't already signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use your work email address and password.

- Download [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

   Power BI Desktop is a free application you install on your local computer. For more information, see [Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

- Make sure the data you want in the report is published as a web service.
    
    There are many web services published by default. An easy way to find the web services is to search for *web services* in [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Web Services** page, make sure the **Publish** field is selected. This task is typically an administrative task.
    
    For more information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

- For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, get the following information:

    - The OData URL for [!INCLUDE[prod_short](includes/prod_short.md)]. Typically, this URL has the format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, for example, `https://localhost:7048/BC160/ODataV4`. If you have a multi-tenant deployment, include the tenant in the URL, for example, `https://localhost:7048/BC160/ODataV4?tenant=tenant1`.
    - A user name and web service access key of a [!INCLUDE[prod_short](includes/prod_short.md)] account.

      To get data from [!INCLUDE[prod_short](includes/prod_short.md)], Power BI uses basic authentication. So, you'll need a user name and web service access key to connect. The account might be your own user account, or your organization may have specific account for this purpose.

- Download the [!INCLUDE [prod_short](includes/prod_short.md)] report theme (optional).

    For more information, see [Using the [!INCLUDE [prod_short](includes/prod_short.md)] report theme](#theme) in this article.

## Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop

The first task in creating reports is to add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop. Once connected, you can start to build the report.

1. Start Power BI Desktop.
2. Select **Get Data**.

    If you don't see **Get Data**, select the **File** menu, then **Get Data**.
2. On the **Get Data** page, select **Online Services**.
3. In the **Online Services** pane, do one of the following steps:

    1. If you're connecting to [!INCLUDE [prod_short](includes/prod_short.md)] online, choose **Dynamics 365 Business Central**, then **Connect**.
    2. If you're connecting to [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, choose **Dynamics 365 Business Central (on-premises)**, then **Connect**.

4. Power BI displays a wizard that will guide you through the connection process, including signing into [!INCLUDE [prod_short](includes/prod_short.md)].

    For online, choose **Sign in**, and then choose the relevant account. Use the same account that you use to sign into [!INCLUDE [prod_short](includes/prod_short.md)].
    
    For on-premises, enter the OData URL for [!INCLUDE[prod_short](includes/prod_short.md)], and optionally the company name. Then, when prompted, enter the user name and password of the account to use for connecting to [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Password** box, enter the web service access key.

    > [!NOTE]  
    > Once you have successfully connected to [!INCLUDE[prod_short](includes/prod_short.md)], you won't be prompted again to sign in.
    
5. Choose **Connect** to continue.

    The Power BI wizard shows a list of Microsoft [!INCLUDE[prod_short](includes/prod_short.md)] environments, companies, and data sources. These data sources represent all the web services that you've published from [!INCLUDE [prod_short](includes/prod_short.md)].
6. Specify the data you want to add to your data model, and then choose the **Load** button.
7. Repeat the previous steps to add additional [!INCLUDE [prod_short](includes/prod_short.md)], or other data, to your Power BI data model.

Once the data is loaded, you can see it in the right navigation on the page. At this point, you've successfully connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data, and you can begin building your Power BI report.  

> [!TIP]
> For more information about using Power BI Desktop, see [Get started with Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## Creating reports to display data associated with a list

You can create reports that display in a FactBox of a [!INCLUDE [prod_short](includes/prod_short.md)] list page. The reports can contain data about the record selected in the list. Creating these reports is similar to other reports, except there are a few things you'll have to do to make sure the reports display as expected. For more information, see [Creating Power BI Reports for Displaying List Data in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="theme"></a>Using the [!INCLUDE [prod_short](includes/prod_short.md)] report theme (optional)

Before building your report, we recommend that you download and import the [!INCLUDE [prod_short](includes/prod_short.md)] theme file. The theme file creates a color palette so you can build reports with the same color styling as the [!INCLUDE [prod_short](includes/prod_short.md)] apps, without requiring you to define custom colors for each visual.

> [!NOTE]
> This task is optional. You can always create your reports, and then download and apply the style template later.

### Download the theme

The theme file is available as a json file on Microsoft Power BI Community Themes Gallery. To download the theme file, do the following steps:

1. Go to [Microsoft Power BI Community Themes Gallery for Microsoft Dynamics 365 Business Central](https://community.powerbi.com/t5/Themes-Gallery/Microsoft-Dynamics-365-Business-Central/m-p/385875).
2. Select the download attachment **Microsoft Dynamics Business Central.json**.

### Import the theme on a report

After you've downloaded the [!INCLUDE [prod_short](includes/prod_short.md)] report theme, you can import it to your reports. To import the theme, Select the **View** > **Themes** > **Browse for themes**. For more information, see [Power BI Desktop - Import custom report themes](/power-bi/create-reports/desktop-report-themes#import-custom-report-theme-files).

## Publish reports

After you've created or modified a report, you can publish the report to your Power BI service and also share it with others in your organization. Once published, you'll see the report in Power BI. The report also becomes available for selection in [!INCLUDE[prod_short](includes/prod_short.md)].

To publish a report, select **Publish** on the **Home** tab of the ribbon or from the **File** menu. If you're signed into Power BI service, the report is published to this service. Otherwise, you're prompted to sign in. 

## Distribute or share a report

There are a couple ways to get reports to your coworkers and others:

- Distribute reports as .pbix files.

    Reports are stored on your computer as .pbix files. You can distribute the report .pbix file to users, like any other file. Then, users can upload the file to their Power BI Service. See [Upload reports from files](across-working-with-business-central-in-powerbi.md#upload).

    > [!NOTE]
    > Distributing reports in this manner means that refreshing data for reports will be done individually by each user. This situation might impact [!INCLUDE[prod_short](includes/prod_short.md)] performance.

- Share report from your Power BI service

    If you have a Power BI Pro license, you can share the report to others, directly from your Power BI service. For more information, see [Power BI - Share a dashboard or report](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

## See Related Training at [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## See Also

[Enabling Your Business Data for Power BI](admin-powerbi.md)  
[Business Intelligence](bi.md)  
[Getting Started](product-get-started.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  


[!INCLUDE[footer-include](includes/footer-banner.md)]