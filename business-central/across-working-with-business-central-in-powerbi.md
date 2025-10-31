---
title: Connect to Power BI from Business Central on-premises| Microsoft Docs
description: Get insight, business intelligence, and KPIs from your Business Central data on-premises using Power BI.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 10/23/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Connect to Power BI from Business Central on-premises

## Get started

[!INCLUDE [prod_short](includes/prod_short.md)] on-premises must be enabled for Power BI integration. This task is typically done by an administrator. Learn more about enabling Power BI integration with Business Central online in [Set up Business Central on-premises for Power BI integration](admin-powerbi-setup.md).

Some features are only available with Business Central online, not on-premises. Learn more in [Introduction to Business Central and Power BI](admin-powerbi.md#get-ready-to-use-power-bi)

## <a name="setup"></a>Set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for Power BI integration

This section explains the requirements for a [!INCLUDE[prod_short](includes/prod_short.md)] on-premises deployment to integrate with Power BI.

1. Configure either [NavUserPassword](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-navuserpassword) or [Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-ad-overview) as the authentication method for the deployment.  

   > [!NOTE]
   > Power BI integration doesn't support Windows authentication.

1. Enable OData web services and the ODataV4 endpoint.

   Enable OData web service on the [!INCLUDE[server](includes/server.md)] and open the OData port in the firewall. Learn more in [Configuring Business Central Server - OData Web Services](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#ODataServices).

   The local server must be accessible from the Internet.

1. Give [!INCLUDE[prod_short](includes/prod_short.md)] user accounts a web service access key.

   A web service access key is only needed to view [!INCLUDE[prod_short](includes/prod_short.md)] data in Power BI. You can assign a web service access key to each user account. Or instead, create a specific account with a web service access key for use by all users. Learn more in [Web Services Authentication](/dynamics365/business-central/dev-itpro/webservices/web-services-authentication#generate-a-web-service-access-key).

1. Create an application registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure.

   To view Power BI reports embedded in [!INCLUDE[prod_short](includes/prod_short.md)] pages, register an application for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Entra ID. The registered application needs permission to Power BI services. At a minimum, the app requires **User.ReadWrite.All** permission. For users to view reports from shared Power BI workspaces, the app requires **Workspace.Read.All** permission. Learn more in [Registering [!INCLUDE[prod_short](includes/prod_short.md)] on-premises in Microsoft Entra ID for Integrating with Other Services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

   > [!NOTE]
   > If your deployment uses NavUserPassword authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the same Power BI service for all users. You specify this service account as part of registering the application. With Microsoft Entra authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Power BI service associated with the individual user accounts.

1. Make the initial connection from Business Central to Power BI.

   Before users can use Power BI in [!INCLUDE[prod_short](includes/prod_short.md)], an Azure application administrator must give consent to the Power BI service.

   To make the initial connection, open [!INCLUDE[prod_short](includes/prod_short.md)], and run **Get Started with Power BI** from the Home page. This action leads you through the consent process and checks your Power BI license. When you're prompted, sign in using a Microsoft Entra admin account. Learn more in [Connect to Power BI - one time only](across-working-with-powerbi.md#connect).

## Build Power BI reports displaying [!INCLUDE [prod_long](includes/prod_long.md)] data

You can make your Dynamics 365 Business Central data available as a data source in Power BI Desktop and build powerful reports of the state of your business.

Use Power BI Desktop to create reports that display Dynamics 365 Business Central data. After creating reports, you can publish them to your Power BI service or share them with all users in your organization. Once these reports are in the Power BI service, users set up for it can view the reports in  Business Central.

- For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, get the following information:

  - The OData URL for [!INCLUDE[prod_short](includes/prod_short.md)].
  
    Typically, this URL has the format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, for example, `https://localhost:7048/BC190/ODataV4`. If you have a multitenant deployment, include the tenant in the URL, for example, `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
  - A user name and web service access key of a [!INCLUDE[prod_short](includes/prod_short.md)] account.

    To get data from [!INCLUDE[prod_short](includes/prod_short.md)], Power BI uses basic authentication. So, you need a user name and web service access key to connect. The account might be your own user account, or your organization might have specific account for this purpose.

## <a name="getdata"></a>Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop

The first task in creating reports is to add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop. Once connected, you can start to build the report.

1. Start Power BI Desktop.
1. Select **Get Data**.

   If you don't see **Get Data**, select the **File** menu, then **Get Data**.
1. On the **Get Data** page, select **Online Services**.
1. In the **Online Services** pane, connect to  [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, select **Dynamics 365 Business Central (on-premises)**, then **Connect**.
1. Sign-in to [!INCLUDE [prod_short](includes/prod_short.md)] (one-time only).

   If you're not signed in to [!INCLUDE [prod_short](includes/prod_short.md)] from Power BI desktop before, you're prompted to sign in.

   For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, enter the OData URL for [!INCLUDE[prod_short](includes/prod_short.md)] and select **OK**. When prompted, enter the user name and password for the account for connecting to [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Password** box, enter the web service access key. Select **Connect** when done.

   > [!NOTE]  
   > After you connect to [!INCLUDE[prod_short](includes/prod_short.md)], you aren't prompted again to sign in. [How do I change or clear the account I'm currently using to connect to Business Central from Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)

1. Once connected, Power BI contacts the Business Central service. The **Navigator** windows appears and displays available data sources for building reports. Select a folder to expand it and see the available data sources.

   These data sources represent all the web services and API pages published for [!INCLUDE [prod_short](includes/prod_short.md)]. The data sources are grouped by Business Central environments and companies.

   > [!NOTE]
   > The structure for Business Central on-premises is different because it doesn't support API pages.

1. Select the data source or sources that you want to add to your data model, and then select the **Load** button.
1. To add more Business Central data later, repeat the previous steps.

Once the data is loaded, view it in the right navigation on the page. At this point, you're successfully connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data and can begin building your Power BI report.

> [!TIP]
> Learn more about Power BI Desktop in [Get started with Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## Manage and modify reports

> [!NOTE]
> You can't manage and modify reports.

## Upload reports

For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, there are no demo reports available, so you have to start from scratch by using Power BI Desktop. Alternatively, Power BI reports can be distributed as files that you can upload directly from Power BI online service. Learn more in [Upload the report to the service](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

## Related information

[Business Central and Power BI](admin-powerbi.md)  
[Upload reports](across-working-with-business-central-in-powerbi.md#upload-reports)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
