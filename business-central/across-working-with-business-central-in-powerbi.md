---
title: Connect to Power BI from Business Central on-premises| Microsoft Docs
description: Getting insight, business intelligence, and KPIs from your Business Central data using Power BI.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 01/22/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Connect to Power BI from Business Central on-premises

<!--In this article, you learn some of the basics about working with reports and dashboards in Power BI that use [!INCLUDE [prod_short](includes/prod_short.md)] as a data source. The article discusses some aspects that will help you get started as a [!INCLUDE[prod_short](includes/prod_short.md)] user. For general guidelines and instructions about using Power BI, see [Power BI documentation for consumers](/power-bi/consumer).

## Get ready

Sign up for the Power BI service. If you haven't already signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use a work email address and password.-->

## Get started

For using [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, it must be enabled for Power BI integration. This task is typically done by an administrator. For more information about enabling Power BI integration with Business Central online, see [Set up Business Central on-premises for Power BI integration](admin-powerbi-setup.md).

Some features are only available with Business Central online, not on-premises. For more information, see [Introduction to Business Central and Power BI](admin-powerbi.md#get-ready-to-use-powerbi)

## <a name="setup"></a>Set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for Power BI integration

This section explains the requirements for a [!INCLUDE[prod_short](includes/prod_short.md)] on-premises deployment to integrate with Power BI.

1. Configure either [NavUserPassword](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-navuserpassword) or [Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-ad-overview) as the authentication method for the deployment.  
    
    > [!NOTE]
    > Power BI integration doesn't support Windows authentication and is not supported on Windows Client.

2. Enable OData web services and the ODataV4 endpoint.

    OData web service must be enabled on the [!INCLUDE[server](includes/server.md)], and OData port opened in firewall. For more information, see [Configuring Business Central Server - OData Web Services](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#ODataServices).

    The local server must be accessible from the Internet.

3. Give [!INCLUDE[prod_short](includes/prod_short.md)] user accounts a web service access key.

    A web service access key is only needed to view [!INCLUDE[prod_short](includes/prod_short.md)] data in Power BI. You can assign a web service access key to each user account. Or instead, create a specific account with a web service access key for use by all users. For more information, see [Web Services Authentication](/dynamics365/business-central/dev-itpro/webservices/web-services-authentication#generate-a-web-service-access-key).

4. Create an application registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure.

    To view Power BI reports embedded in [!INCLUDE[prod_short](includes/prod_short.md)] pages, an application must be registered for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure. The registered application needs permission to Power BI services. At a minimum, the app requires  **User.ReadWrite.All** permission. For users to view reports from shared Power BI workspaces, the app requires **Workspace.Read.All** permission. For more information, see [Registering [!INCLUDE[prod_short](includes/prod_short.md)] on-premises in Microsoft Entra ID for Integrating with Other Services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

    > [!NOTE]
    > If your deployment uses NavUserPassword authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the same Power BI service for all users. You'll specify this service account as part of registering the application. With Microsoft Entra authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Power BI service associated with the individual user accounts.

    <!-- Windows authentication can also be used but you can't get data from BC in Power BI -->
5. Make the initial connection from Business Central to Power BI.

    Before end-users can use Power BI in [!INCLUDE[prod_short](includes/prod_short.md)], an Azure application administrator will have to give consent to the Power BI service.

    To make the initial connection, open [!INCLUDE[prod_short](includes/prod_short.md)], and run **Get Started with Power BI** from the Home page. This action will lead you through the consent process, and check your Power BI license. When prompted sign in using a Microsoft Entra admin account. For more information, see [Connect to Power BI - one time only](across-working-with-powerbi.md#connect).

## Build Power BI reports to display [!INCLUDE [prod_long](includes/prod_long.md)] data

You can make your Dynamics 365 Business Central data available as a data source in Power BI Desktop and build powerful reports of the state of your business.

Use Power BI Desktop to create reports that display Dynamics 365 Business Central data. After you create reports, you can publish them to your Power BI service, or share them with all users in your organization. Once these reports are in the Power BI service, users that are set up for it, can then view the reports in Dynamics 365 Business Central.

- For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, get the following information:

  - The OData URL for [!INCLUDE[prod_short](includes/prod_short.md)].
  
    Typically, this URL has the format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, for example, `https://localhost:7048/BC190/ODataV4`. If you have a multi-tenant deployment, include the tenant in the URL, for example, `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
  - A user name and web service access key of a [!INCLUDE[prod_short](includes/prod_short.md)] account.

    To get data from [!INCLUDE[prod_short](includes/prod_short.md)], Power BI uses basic authentication. So, you'll need a user name and web service access key to connect. The account might be your own user account, or your organization may have specific account for this purpose.

## <a name="getdata"></a>Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop

The first task in creating reports is to add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop. Once connected, you can start to build the report.

1. Start Power BI Desktop.
2. Select **Get Data**.

    If you don't see **Get Data**, select the **File** menu, then **Get Data**.
3. On the **Get Data** page, select **Online Services**.
4. In the **Online Services** pane, connect to  [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, select **Dynamics 365 Business Central (on-premises)**, then **Connect**.
5. Sign-in to [!INCLUDE [prod_short](includes/prod_short.md)] (one-time only).

    If you haven't signed in to [!INCLUDE [prod_short](includes/prod_short.md)] from Power BI desktop before, you're prompted to sign in.

   - For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, first enter the OData URL for [!INCLUDE[prod_short](includes/prod_short.md)], then select **OK**. When prompted, enter the user name and password of the account to use for connecting to [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Password** box, enter the web service access key. When done, select **Connect**.
   
    > [!NOTE]  
    > Once you have successfully connected to [!INCLUDE[prod_short](includes/prod_short.md)], you won't be prompted again to sign in. [How do I change or clear the account I'm currently using to connect to Business Central from Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)

6. Once connected, Power BI contacts to the Business Central service. The **Navigator** windows appears and displays available data sources for building reports. Select a folder to expand it and see the available data sources. 

   These data sources represent all the web services and API pages that are published for [!INCLUDE [prod_short](includes/prod_short.md)]. The data sources are grouped by the Business Central environments and companies.

   > [!NOTE]
    > The structure for Business Central on-premises is different because it doesn't support API pages.

7. Select the data source or sources that you want to add to your data model, and then select the **Load** button.
8. If later you want to add more Business Central data, you can repeat the previous steps.

Once the data is loaded, you can see it in the right navigation on the page. At this point, you've successfully connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data, and you can begin building your Power BI report.  

> [!TIP]
> For more information about using Power BI Desktop, see [Get started with Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## Manage and modify reports

> [!NOTE]
> You can’t manage and modify reports. 

## Upload reports

For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, there are no demo reports available, so you'll have to start from scratch by using Power BI Desktop. Alternatively, Power BI reports can be distributed as files that you can upload directly from Power BI online service. For more information, see [Upload the report to the service](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

<!--
> [!NOTE]
> Uploading a report requires that you have SUPER user permissions in [!INCLUDE[prod_short](includes/prod_short.md)]. Also, you can't upload reports with [!INCLUDE [prod_short](includes/prod_short.md)] on-premises. With on-premises, you upload reports directly to your Power BI workspace. For more information, see [Connect to Power BI from [!INCLUDE [prod_short](includes/prod_short.md)] on-premises](across-working-with-business-central-in-powerbi.md).

<!--Once you have a Power BI account, you can sign in at [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/).

The Power BI service hosts all the reports available to you. To see the report, select **My Workspace** > **Reports**. Then just select the report that you want to view.

With [!INCLUDE[prod_short](includes/prod_short.md)] online, you'll automatically have a set of default reports on your workspace. If you want to create your own reports, you can use Power BI Desktop to create reports, and then publish them to your workspace. For more information, see [Getting Started Building Reports in Power BI Desktop to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md).

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

If you're using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you'll have to start from scratch by using Power BI Desktop. Optionally, Power BI reports can be distributed as files, that you can upload.

<!--## Get the latest data

Each Power BI report is based on a dataset that gets data from the [!INCLUDE[prod_short](includes/prod_short.md)] sources. You want to make sure that the data in your Power BI reports is up to date with the data in [!INCLUDE[prod_short](includes/prod_short.md)]. This concept is referred to as *refreshing*.  Depending on how your organization has set up Power BI, refreshing might not happen automatically. There are two ways to refresh data: manually or by scheduling a refresh. Manual refreshing is done on-demand, as needed. Scheduled refreshing lets you refresh automatically at defined time intervals.

### Refresh manually

In the navigation pane, under **Datasets**, select **More options (...)** next to the dataset, then select **Refresh now**.

### Schedule a refresh

In the navigation pane, under Datasets, select More options (...) next to the dataset, then select **Schedule refresh**. Fill in the information under the **Schedule refresh** section, and select **Apply**.

For more information, see [Configure scheduled refresh](/power-bi/connect-data/refresh-scheduled-refresh)-->

<!--## <a name="upload"></a>Upload reports from files

Power BI Reports can be distributed among users as .pbix files. If you have a .pbix file, you can upload the file to a workspace. To upload a report, do the following steps:

1. In your new workspace, select **Get Data**.

2. In the Files box, select **Get**.

3. Select **Local File**, navigate to where you saved the file, and select **Open**.

For more information, see [Upload the report to the service](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

> [!NOTE]
> Uploading a report requires that you have a [Premium capacity](/power-bi/service-premium-what-is) work space. For more information, see [Managing Premium capacities](/power-bi/admin/service-premium-capacity-manage). 

> [!TIP]
> If you're using [!INCLUDE[prod_short](includes/prod_short.md)] online, you can also upload a report from within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Work with Power BI Reports in [!INCLUDE [prod_short](includes/prod_short.md)] - Upload Reports](across-working-with-powerbi.md#upload).

## <a name="share"></a>Share reports with others

Once a report is in your workspace, you can share it with others in your organization.

To share a report, in a list reports, or in an open report, select **Share**. In the **Share report** pane, enter the full email addresses for individuals or distribution groups you want to share with. Follow the instructions on screen to complete the sharing. For more information, see [Share a dashboard or report](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

> [!NOTE]
> You must have  [Power BI Pro license](/power-bi/service-features-license-type), and the people you share with do too. The content must be in a workspace in a [Premium capacity](/power-bi/service-premium-what-is). For more information, see [Ways to share your work in Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).-->

## See also

[Business Central and Power BI](admin-powerbi.md)  
[Upload reports](across-working-with-business-central-in-powerbi.md#upload-reports)
 
[!INCLUDE[footer-include](includes/footer-banner.md)]
