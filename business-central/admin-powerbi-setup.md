---
title: Enabling Power BI Integration With Business Central
description: Learn how to set up the connection to Power BI. With Power BI reports, you can get insights, business intelligence, and KPIs from your Business Central data.
author: jswymer
ms.topic: get-started
ms.search.keywords: Power BI, setup, analysis, reporting, financial report, business intelligence, KPI
ms.date: 09/28/2023
ms.author: jswymer
---
# Enabling Power BI Integration With [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

This article describes how to get [!INCLUDE[prod_short](includes/prod_short.md)] ready for integration with Power BI. [!INCLUDE[prod_short](includes/prod_short.md)] online is already enabled for integration, although there's some information about licensing that you might want to read. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you'll have set up your environment to connect to Power BI before users can work with it.

## <a name="license"></a>Power BI Licensing

With [!INCLUDE[prod_short](includes/prod_short.md)], users get a free Power BI license that provides access to the most common features in [!INCLUDE[prod_short](includes/prod_short.md)] and Power BI. You can also purchase a Power BI Pro license that provides access to additional features. The following table provides an overview of the features available with each license.

|Power License|View reports|Create reports|Share reports|Refresh reports| [!INCLUDE[prod_short](includes/prod_short.md)] Apps|
|-------------|--------||
|Power BI free|![a checkmark.](media/check.png)|![another checkmark](media/check.png)|(limited)|(limited)||
|Power BI Pro|![yet another checkmark.](media/check.png)|![it's a checkmark](media/check.png)|![again a checkmark](media/check.png)|(extensive)|![last checkmark](media/check.png)|

For more information, see [Licensing the Power BI service for users in your organization](/power-bi/admin/service-admin-licensing-organization) or [Sign up for the Power BI service as an individual](/power-bi/fundamentals/service-self-service-signup-for-power-bi).

## <a name="exposedata"></a>Expose data through API or OData web services

Business Central offers two ways to expose data that can be consumed by Power BI reports: API pages or queries, and Open Data Protocol (OData) web services.

### API pages and queries

> **APPLIES TO:** Business Central online only

Developers can define page objects and query objects that are of the type *API*. This way, they can expose data from database tables through a webhook-supported, OData v4-enabled, REST service. This type of data can't be displayed in the user interface, but is intended for building reliable integration services.

Business Central online comes available with a set of built-in APIs, which you can use to get data for the most common business entities, like customers, items, sales orders, and more. No extra work or setup is required to use these APIs as a data source for Power BI reports. For more information about these APIs, see [Business Central API V2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/).

Business Central online also supports custom APIs. Application developers of Business Central solutions can create their own API pages and queries and package them into apps. You then install the apps on your tenant. Once installed, you use the API pages for your Power BI reports, like you'd do with the built-in APIs (v2.0). For more information about how to create an API by exposing pages or queries, see [Developing a Custom API](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api).

> [!IMPORTANT]
> Starting in February 2022, Power BI reports for [!INCLUDE[prod_short](includes/prod_short.md)] online are sourced from a secondary, read-only database replica for performance reasons. As a consequence, AL developers should avoid designing API pages that make database modifications while the pages are opening or loading records. In particular, consider the code on the AL triggers: OnInit, OnOpenPage, OnFindRecord, OnNextRecord, OnAfterGetRecord, and OnAfterGetCurrRecord. These database modifications, in some cases, may cause performance problems and prevent the report from refreshing data. For more information, see [Performance Articles For Developers](/dynamics365/business-central/dev-itpro/performance/performance-developer?branch=main#writing-efficient-web-services) in the Business Central development content.
>
> In rare cases, the behavior will cause an error when a user tries get data from the API for a report in Power BI Desktop. However, if database modifications are necessary in the custom API, Power BI Desktop users can force the behavior. For more information, see [Building Power BI Reports to Display Business Central Data](across-how-use-financials-data-source-powerbi.md#fixing-problems).

### OData web services

You can publish Business Central application objects, like codeunits, page, and queries, as [OData web services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services). With Business Central online, there are many web services published by default. An easy way to find the web services is to search for *web services* in [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Web Services** page, make sure the **Publish** field is selected for the web services listed above. For more information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

To learn about what you can do to ensure the best performance of web services, as seen from the Business Central server (the endpoint) and from the consumer (the client), read [Writing efficient Web Services](/dynamics365/business-central/dev-itpro/performance/performance-developer#writing-efficient-web-services).

### Choosing whether to use API pages or OData web services

Whenever possible, you're encouraged to use API pages instead of OData web service. API pages are generally faster at loading data in Power BI reports than OData web services. Plus, they're more flexible because they let you get data from table fields that aren't defined in a page object.

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

    <!--
    > [!IMPORTANT]
    > With [!INCLUDE[prod_short](../developer/includes/prod_short.md)] online, the use of access keys (Basic Auth) for web service authentication is [deprecated](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#accesskeys). We recommend that you use OAuth2 instead. For more information, see [Use OAuth to Authorize Business Central Web Services](/dynamics365/business-central/dev-itpro/webservices/authenticate-web-services-using-oauth).-->

4. Create an application registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure.

    To view Power BI reports embedded in [!INCLUDE[prod_short](includes/prod_short.md)] pages, an application must be registered for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure. The registered application needs permission to Power BI services. At a minimum, the app requires  **User.ReadWrite.All** permission. For users to view reports from shared Power BI workspaces, the app requires **Workspace.Read.All** permission. For more information, see [Registering [!INCLUDE[prod_short](includes/prod_short.md)] On-Premises in Microsoft Entra ID for Integrating with Other Services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

    > [!NOTE]
    > If your deployment uses NavUserPassword authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the same Power BI service for all users. You'll specify this service account as part of registering the application. With Microsoft Entra authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Power BI service associated with the individual user accounts.

    <!-- Windows authentication can also be used but you can't get data from BC in Power BI -->
5. Make the initial connection from Business Central to Power BI.

    Before end-users can use Power BI in [!INCLUDE[prod_short](includes/prod_short.md)], an Azure application administrator will have to give consent to the Power BI service.

    To make the initial connection, open [!INCLUDE[prod_short](includes/prod_short.md)], and run **Get Started with Power BI** from the Home page. This action will lead you through the consent process, and check your Power BI license. When prompted sign in using an Microsoft Entra admin account. For more information, see [Connect to Power BI - one time only](across-working-with-powerbi.md#connect).

## See Also

[Business Central and Power BI](admin-powerbi.md)  
[Power BI Integration Component and Architecture Overview for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Power BI for consumers](/power-bi/consumer/end-user-consumer)  
[The 'new look' of the Power BI service](/power-bi/service-new-look)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Power BI documentation](/power-bi/)  
[Business Intelligence](bi.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power Apps Data Source](across-how-use-financials-data-source-powerapps.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate](across-how-use-financials-data-source-flow.md)  




[!INCLUDE[footer-include](includes/footer-banner.md)]
