---
title: Use Business Central Apps in Power BI
description: Easily gain insights, business intelligence, and KPIs from your Business Central data using the Business Central apps for Power BI.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.search.form: 36951,
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Use the [!INCLUDE [prod_short](includes/prod_short.md)] apps in Power BI

> **APPLIES TO:** [!INCLUDE [prod_long](includes/prod_long.md)] online

[!INCLUDE [prod_long](includes/prod_long.md)] publishes the following Power BI apps, which provide detailed dashboards for viewing data:

- [!INCLUDE [prod_long](includes/prod_long.md)] - CRM  
- [!INCLUDE [prod_long](includes/prod_long.md)] - Finance  
- [!INCLUDE [prod_long](includes/prod_long.md)] - Sales

## Explore the apps and dashboards

Each app includes several reports that you can drill into for data, including the following features:

- Choose any visual on the dashboard to bring up one of the underlying reports.  
- Filter the report or add fields that you want to monitor.  
- Pin a customized view to the dashboard to continue tracking.  
  You can refresh data manually, and you can set up a refresh schedule. Learn more in [Configuring scheduled refresh](/power-bi/refresh-scheduled-refresh).  

The apps are designed to work with data from any company in [!INCLUDE[prod_short](includes/prod_short.md)]. When you install the Power BI app, you specify one or more parameters to connect to your [!INCLUDE [prod_short](includes/prod_short.md)].  

> [!NOTE]
> You can also build your own reports and dashboards in Power BI based on your [!INCLUDE[prod_short](includes/prod_short.md)] data. Learn more in [Connecting Your Business Data to Power BI](across-how-use-financials-data-source-powerbi.md).

## Prerequisites

Power BI apps require permissions to the tables where data is retrieved and the web services used to retrieve data. The following table lists the web services required for each Power BI app:

|App|Web services |
|--|-------------|
|[!INCLUDE[prod_short](includes/prod_short.md)] – CRM| <ul><li>Sales Opportunities</li><li>Excel Template View Company Information</li><li>Power BI Report Labels</li></ul>|
|[!INCLUDE[prod_short](includes/prod_short.md)] – Finance| <ul><li>PowerBIFinance</li><li>Excel Template View Company Information</li><li>Power BI Report Labels</li></ul>|
|[!INCLUDE[prod_short](includes/prod_short.md)] – Sales| <ul><li>Item Sales by Customer</li><li>Sales Dashboard</li><li>Excel Template View Company Information</li><li>Power BI Report Labels</li></ul>|

> [!TIP]
> To find the web services, search for *web services* in [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Web Services** page, ensure the **Published** field is selected for the web services listed earlier. To learn more, see [Publishing a Web Service](across-how-publish-web-service.md).

## Sign up for Power BI

Sign up for the Power BI service. If you haven't already signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use your work email address and password.

## Install a [!INCLUDE[prod_short](includes/prod_short.md)] app in Power BI

1. Open your browser, navigate to [https://powerbi.microsoft.com](https://powerbi.microsoft.com), and sign in to your account.
1. Select **Apps** on the navigation pane.

    The **Apps** page appears.

1. On the **Apps** page, select **Get apps** from the upper right corner of the page.

    The **Power BI apps** page opens, where you can browse for the apps that are available for [!INCLUDE[prod_short](includes/prod_short.md)].

    :::image type="content" source="./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-get-data.png" alt-text="Screenshot of the Power BI service showing where to get apps.":::

    > [!TIP]
    > You can also open the app galleries from [!INCLUDE [prod_short](includes/prod_short.md)]. In the **Power BI Reports** part on your Home page, select **Select reports**. Under **Get Reports**, select **Organizational Apps** or **Marketplace Apps**.

1. In the **Search** box, enter **Dynamics 365 Business Central**.
1. Select the app that you want to use, select **Get it now**, and then **Install**.

    When completed, the app is available from **Apps** on the navigation menu in Power BI.

## Connect the [!INCLUDE[prod_short](includes/prod_short.md)] app to your data

1. Under **Apps**, open the Business Central app, and then select **Connect your data** in the banner.
1. When prompted, fill in the **Company Name** and **Environment** with information about the [!INCLUDE[prod_short](includes/prod_short.md)] instance that you want to connect to.

    - For **Company Name**, make sure to use the full name, not the display name. You can find the company name in the **Companies** page in [!INCLUDE[prod_short](includes/prod_short.md)].
    - For **Environment**, if you haven't created multiple environments, enter **Production**.

1. Select **Next**.
1. Follow the authentication prompts to sign in with your [!INCLUDE[prod_short](includes/prod_short.md)] account.
1. Once connected, a dashboard and reports are added to your Power BI workspace. When completed, the tiles show data from your [!INCLUDE[prod_short](includes/prod_short.md)] company.

    :::image type="content" source="./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-workspace-dashboard-report-dataset.png" alt-text="Screenshot of a Power BI workspace with a Business Central dashboard, report, and semantic model.":::

## Troubleshoot app connections and data

The Power BI dashboard relies on the published web services that are listed above. It shows data from the demonstration company or your own company if you import data from your current finance solution. However, if something goes wrong, this section provides a workaround for the most typical issues.  

### You don't have a Power BI account

A Power BI account hasn't been set up. You must have a license to get a valid Power BI account. Also, you must have previously signed into Power BI to create your Power BI workspace.  

### Message: There are no enabled reports. Select report to see a list of reports that you can display

This message appears when no report is enabled for the current page. Open **Select reports** and enable a report on the **Power BI Reports Selection** page. If the report failed to deploy or refresh, open its semantic model's **Settings** in the Power BI workspace and update the data source credentials. After the semantic model refreshes successfully, return to [!INCLUDE[prod_short](includes/prod_short.md)] and select the report.

### You need a Power BI Pro or PPU license to install the app

You need a Power BI Pro or Premium Per User (PPU) license to install and share template apps. Premium capacity isn't required. Recipients need Pro or PPU unless the content is hosted in Premium capacity or Fabric F64 or larger capacity. Content in a PPU workspace requires PPU licenses for recipients. Learn more in [Power BI license types](/power-bi/fundamentals/service-features-license-type) and [Share Power BI reports and dashboards](/power-bi/collaborate-share/service-share-dashboards).

### "Parameter validation failed, please make sure all parameters are valid"

This error indicates that one more of the parameters aren't valid.

- The specified environment parameter doesn't match any existing [!INCLUDE[prod_short](includes/prod_short.md)] production or sandbox environment.
- The specified company parameter doesn't match any existing [!INCLUDE[prod_short](includes/prod_short.md)] companies. Verify the company name in the **Companies** page in [!INCLUDE[prod_short](includes/prod_short.md)].
- If connecting to [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you entered a URL that isn't valid. You can verify the URL in the **Web Services** page in [!INCLUDE[prod_short](includes/prod_short.md)]  
- A port isn't open to allow the request through your firewall.

### Can't sign in

If you get a "login failed" error after using your [!INCLUDE[prod_short](includes/prod_short.md)] user credentials to sign in, then you're probably experiencing one of the following issues:

- The account that you're using doesn't have permissions to retrieve the [!INCLUDE[prod_short](includes/prod_short.md)] data from your account. Verify that you have permissions to the required data in [!INCLUDE[prod_short](includes/prod_short.md)] and try again.
- You've selected an authentication type other than Basic, if connecting to [!INCLUDE[prod_short](includes/prod_short.md)] on-premises.
- You haven't entered a valid user name or password.

### Message: Your data source can't be refreshed because the credentials are invalid. Please update your credentials and try again

For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the problem might be that the OData URL is only exposed to the local network.

### Incorrect company name

A common mistake is to enter the company display name instead of the company name. To find the company name search for **Companies**. Then use the **Name** field when entering your company name.

### The key didn't match any rows in the table

If you enter a non-valid company name during the connection process, you may get the error message "The key didn't match any rows in the table". Provide the correct company name and try connecting again.

### Historical data appears to be missing

Once the Power BI app installs and your data show in Power BI, you notice that not all your data displays. The datasets are filtered to only return the previous 365 days of data. This default is in place to help make the reports faster.  

### I only see data for a single company

The Power BI app will only display data from the [!INCLUDE[prod_short](includes/prod_short.md)] company that was defined when the Power BI app was installed. Data from additional companies can be added to the reports by adding new queries that use different companies as the data source.  

### What now?

- Try [asking a question in the Q&A box](/power-bi/service-q-and-a-tips) at the top of the dashboard.
- [Change the tiles](/power-bi/service-dashboard-edit-tile) in the dashboard.  
- [Select a tile](/power-bi/service-dashboard-tiles) to open the underlying report.  
- By default, your dataset isn't scheduled to refresh. You can change the refresh schedule or try refreshing it on demand using **Refresh Now**. Learn more in [Configuring scheduled refresh](/power-bi/refresh-scheduled-refresh).

## Related information

[Business Central and Power BI](admin-powerbi.md)  
[Power BI Integration Component and Architecture Overview for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Connect to Power BI from [!INCLUDE [prod_short](includes/prod_short.md)] on-premises](across-working-with-business-central-in-powerbi.md)  
[Build Power BI Reports to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md)  
[Business Intelligence](bi.md)  
[Get Ready for Doing Business](ui-get-ready-business.md)  
[Import Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power Apps Data Source](across-how-use-financials-data-source-powerapps.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate](across-how-use-financials-data-source-flow.md)  
[Power BI documentation](/power-bi/)  
[What is Power BI?](/power-bi/fundamentals/power-bi-overview)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Introduction to dataflows and self-service data prep](/power-bi/transform-model/dataflows/dataflows-introduction-self-service)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
