---
title: Build Power BI Reports with Business Central Data
description: Connect Power BI Desktop to Business Central data, build accessible reports, publish and share them, and configure advanced connection options.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Build [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports for displaying [!INCLUDE [prod_long](includes/prod_long.md)] data

You can make your [!INCLUDE[prod_long](includes/prod_long.md)] data available as a data source in [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)] and build powerful reports about the state of your business.

This article describes how to start using [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)] to create reports that display [!INCLUDE[prod_long](includes/prod_long.md)] data. After you create reports, you can publish them to your [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)] or share them with all users in your organization. When the reports are in the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)], users with access can view the reports in [!INCLUDE[prod_long](includes/prod_long.md)].

## Prepare to build Power BI reports

- Sign up for the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)].

  If you aren't signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use your work email address and password.

- Download [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

  [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)] is a free application you install on your local computer. Learn more at [Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

- Make sure the data you want in the report is available as an API (recommended) or published as a web service. Learn more in [Expose data through API pages or OData web services](admin-powerbi-setup.md#exposedata).

<!--- For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, get the following information:

  - The OData URL for [!INCLUDE[prod_short](includes/prod_short.md)].
  
    Typically, this URL has the format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, for example, `https://localhost:7048/BC190/ODataV4`. If you have a multi-tenant deployment, include the tenant in the URL, for example, `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
  - A username and web service access key of a [!INCLUDE[prod_short](includes/prod_short.md)] account.

    To get data from [!INCLUDE[prod_short](includes/prod_short.md)], Power BI uses basic authentication. So, you'll need a username and web service access key to connect. The account might be your own user account, or your organization may have a specific account for this purpose.-->

- Download the [!INCLUDE [prod_short](includes/prod_short.md)] report theme (optional).

  Learn more in [Use the [!INCLUDE [prod_short](includes/prod_short.md)] report theme](#theme) in this article.

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

## <a name="getdata"></a>Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop

The first task in creating reports is to add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)]. Once connected, you can start to build the report. The following steps use the new Get Data experience in [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)]. Learn more about the new experience in [Get data in Power BI Desktop](/power-bi/connect-data/desktop-data-sources?tabs=new-experience).

1. Start [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)].
1. Select **Get data** or **Get data from other sources**. If you don't see **Get data**, select the **File** menu, then **Get data**.

   If you're prompted to sign in, sign in using the same work account that you use to sign in to [!INCLUDE [prod_short](includes/prod_short.md)].

   > [!NOTE]
   > The first time you connect to [!INCLUDE[prod_short](includes/prod_short.md)], you might be prompted to sign in. After you connect, you won't be prompted again unless you change or clear the account used for the connection. [How do I change or clear the account I'm currently using to connect to Business Central from Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms).

1. On the **Choose data source** page, search for *Business Central*, and then select **Dynamics 365 Business Central**.
1. On the **Connect to data source** page, select **Next** to connect to [!INCLUDE [prod_short](includes/prod_short.md)].

1. On the **Choose data** page, expand the environment and company that contain the data you want to use in your report.

   The available data sources are grouped by environment and company as follows:

   - **Environment name**
     - **Company name**
       - **Advanced APIs**

         Lists advanced APIs published by Microsoft, such as the [Business Central automation APIs](/dynamics365/business-central/dev-itpro/administration/itpro-introduction-to-automation-apis), and APIs published by other organizations, also known as custom APIs. Custom APIs are further grouped according to the [APIPublisher](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apipublisher-property)/[APIGroup](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apigroup-property) properties of the API source code.

       - **Standard APIs v2.0**

         Lists the standard data APIs exposed by [Business Central API V2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/). These APIs provide access to [!INCLUDE[prod_short](includes/prod_short.md)] data, such as customers, vendors, items, general ledger entries, dimensions, payment methods, and units of measure.

       - **Web services (legacy)**

         Lists pages and queries published as OData web services in [!INCLUDE[prod_short](includes/prod_short.md)]. Codeunits aren't available as OData data sources. We recommend using APIs instead of OData web services when possible.

1. Select the data source or sources that you want to add to your data model, and then select **Load**.
1. To add more [!INCLUDE [prod_short](includes/prod_short.md)] data later, repeat the previous steps.

After the data is loaded, it appears in the **Data** pane on the right side of [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)]. You're now connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data and can start building your [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)] report.

## Create accessible reports

It's important to make your reports usable for as many people as possible. Try to design reports so that they don't require any special adaptation to meet the specific needs of different users. Make sure the design lets users take advantage of assistive technologies, like screen readers. [!INCLUDE [powerbi-name](includes/powerbi-name.md)] includes various accessibility features, tools, and guidelines to help. Learn more in [Design Power BI reports for accessibility](/power-bi/create-reports/desktop-accessibility-creating-reports) in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] documentation.

## Create reports to display data associated with a list in [!INCLUDE [prod_short](includes/prod_short.md)]

You can create reports that display in a FactBox on a [!INCLUDE [prod_short](includes/prod_short.md)] list page, and change when different rows are selected in the list. Creating these reports is similar to other reports, except there are a few things to do to make sure the reports display as expected. Learn more in [Creating Power BI Reports for Displaying List Data in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="theme"></a>Using the [!INCLUDE [prod_short](includes/prod_short.md)] report theme (optional)

Before building your report, we recommend that you download and import the [!INCLUDE [prod_short](includes/prod_short.md)] theme file. The theme file creates a color palette so you can build reports with the same color styling as the [!INCLUDE [prod_short](includes/prod_short.md)] apps, without requiring you to define custom colors for each visual.

> [!NOTE]
> This task is optional. You can always create your reports and then download and apply the style template later.

### Download the theme

The theme file is available as a json file on Microsoft Power BI Community Themes Gallery. To download the theme file, do the following steps:

1. Visit [Microsoft Power BI Community Themes Gallery for Microsoft Dynamics 365 Business Central](https://community.fabric.microsoft.com/discussions/ThemesGallery/microsoft-dynamics-365-business-central/385875).
2. Select the download attachment **Microsoft Dynamics Business Central.json**.

### Import the theme on a report

After you download the [!INCLUDE [prod_short](includes/prod_short.md)] report theme, import it to your reports. In the ribbon, select **Design** > **Import theme**, and then browse for the **Microsoft Dynamics Business Central.json** file. Learn more in [Power BI Desktop - Import custom report themes](/power-bi/create-reports/desktop-report-themes#import-custom-report-theme-files).

## <a name="publish-reports"></a>Publish reports to Power BI

After you create or modify a report, you can publish the report to your [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)] and also share it with others in your organization. After you publish a report, it's available in [!INCLUDE [prod_short](includes/prod_short.md)]. The report also becomes available for selection in [!INCLUDE[prod_short](includes/prod_short.md)].

To publish a report, select **Publish** on the **Home** tab of the ribbon or from the **File** menu. If you're signed into the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)], the report is published to this service. Otherwise, you're prompted to sign in. 

## Distribute or share a report

There are a couple of ways to share reports:

- Share a report from your [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)] (recommended)

    You need a Power BI Pro or Premium Per User (PPU) license to share reports from the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)]. Recipients also need Pro or PPU unless both the report and its semantic model are hosted in Premium capacity or Fabric F64 or larger capacity. Content in a PPU workspace requires PPU licenses for recipients. Learn more in [Share a dashboard or report](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

- Distribute reports as .pbix files.

    Reports are stored on your computer as .pbix files. You can distribute the .pbix file to users, like any other file. Then, the people you shared the file with can upload it to their [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)]. Learn more in [Upload reports from files](across-working-with-powerbi.md#upload).

    > [!NOTE]
    > Distributing reports in this way means that refreshing data for reports is done individually by each user. This situation might impact [!INCLUDE[prod_short](includes/prod_short.md)] performance.

## How to develop cross-company or cross-environment [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports

The [!INCLUDE[prod_short](includes/prod_short.md)] API endpoints all have the prefix `https://api.businesscentral.dynamics.com/v2.0/<environment_name>/api/v2.0` followed by `/companies({company_id})/accounts({id})` (here we use the `accounts` API as an illustration). You can use this structure to create PowerQuery queries that load data for multiple companies or multiple environments if the user who is reading data can access them.

To set up a query to load data for multiple companies, follow these steps:

1. Take the PowerQuery query that loads data for a single company. Convert it to a custom Power Query function that takes the company ID (or maybe the environment name) as parameters. Learn more in [Using custom Power Query functions](/power-query/custom-function).
1. Now use the new custom function in a PowerQuery query, where you map the function over a list of companies and then merge the datasets using the [Table.Combine](/powerquery-m/table-combine) Power Query function.

## Customize the Power Query code that connects to your [!INCLUDE [prod_short](includes/prod_short.md)] data source

In most cases, using the navigation experience in the Power BI Desktop user interface is enough to get you started with building reports based on [!INCLUDE [prod_short](includes/prod_short.md)] data. However, more complex scenario might require you to manually edit the Power Query code responsible to get your data.

To do that, follow these steps:

1. Start [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)].
2. Complete the step that suits your scenario:

   # [Edit existing report](#tab/existing)

   1. Select **File** > **Open**.
   2. Browse for and select the report (.pbix).
   3. In the ribbon, select **Transform Data** to open the **Power Query Editor**.

   # [Create new report](#tab/new)

   1. In the ribbon, select **Get Data**. If you don't see **Get Data**, select the **File** menu, then **Get Data**.
   2. On the **Get Data** page, select **Online Services** > **Dynamics 365 Business Central** > **Connect**.
   3. In the **Navigator** window, select the API endpoint that you want to load data from.
   4. Select **Transform Data** instead of **Load** as you might normally do. This step opens **Power Query Editor**.

   ---

3. In **Power Query Editor**, select **Advanced Editor** from the ribbon.

This displays the Power Query code that the system autogenerated when you made your selections in the navigator. For example, let's assume you selected the [!INCLUDE [prod_short](includes/prod_short.md)] environment named **Production**, the company called **CRONUS USA, Inc.**, the API folder called **Standard APIs v2.0**, and the table called **customers**. Navigating to the Advanced Editor would show a query similar to this one:

```powerquery
let
  Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null),
  PRODUCTION = Source{[Name="PRODUCTION"]}[Data],
  #"CRONUS USA, Inc." = PRODUCTION{[Name="CRONUS USA, Inc."]}[Data],
  v2.0 = #"CRONUS USA, Inc."{[Name="v2.0"]}[Data],
  customers_table = v2.0{[Name="customers",Signature="table"]}[Data]
in
  customers_table
```

You can now manually edit this query to make the changes that suite your needs.

### Connect with the ApiContentsWithOptions function

In the query above, the function `Dynamics365BusinessCentral.ApiContentsWithOptions` is responsible for connecting to [!INCLUDE [prod_short](includes/prod_short.md)] and retrieve the data. This function has 4 optional parameters that aren't provided in the default query.

Here's a breakdown of the different parameters:

|Parameter|Examples|Description|
|-|-|-|
|Environment|`"Production"`|This parameter allows you to specify the [!INCLUDE [prod_short](includes/prod_short.md)] environment to connect to. If not specified, the function returns a list of all environments, and you need to select the appropriate environment in the subsequent steps of your Power Query code|
|Company|`"CRONUS USA, Inc."`|This parameter allows you to specify the [!INCLUDE [prod_short](includes/prod_short.md)] company to connect to, inside your selected environment. This parameter is ignored if the **Environment** parameter isn't specified. If not specified, the function returns a list of all companies in your selected environent (or environments), and you need to select the appropriate company in the subsequent steps of your Power Query code|
|API category (or API route)|`"microsoft/runtime/beta"`, `"v2.0"`|This parameter allows you to specify the API route connect to in [!INCLUDE [prod_short](includes/prod_short.md)], inside your selected environment and company. This parameter is ignored if the **Environment** and **Company** parameters aren't specified. If not specified, the function returns a list of all API categories (also called API routes) in your selected environment/environments and company/companies, and you need to select the appropriate API category in the subsequent steps of your Power Query code|
|Advanced Options||This parameter allows you to specify some advanced options to connect to your [!INCLUDE [prod_short](includes/prod_short.md)] data source. Notice that in the vast majority of cases, the default values are optimized and don't need to be changed. Consult the following section for more information about these parameters.|

For example, the query shown above in this section is completely equivalent to the following query:

   ```powerquery
    let
      Source = Dynamics365BusinessCentral.ApiContentsWithOptions("PRODUCTION", "CRONUS USA, Inc.", "v2.0", null),
      customers_table = Source{[Name="customers",Signature="table"]}[Data]
    in
      customers_table
  ```

### Advanced: Customize language, timeout, database replica, or page size for your Business Central data source

The [!INCLUDE [powerbi-connector-name](includes/powerbi-connector-name.md)] supports several advanced properties for connecting to a [!INCLUDE [prod_short](includes/prod_short.md)] data source that you can set in your Power Query queries. The following table describes the parameters.

|Advanced Option|Description|Default|Learn more at|
|-|-|-|-|
|AcceptLanguage|This parameter allows you to specify preferred languages for responses, ensuring users receive messages and translatable strings in their desired language. It sets the language in which the [!INCLUDE [prod_short](includes/prod_short.md)] API session runs. It influences the language of error messages, formatted values in AL, and other values that depend on language or culture.<br><br>This option doesn't select the display language of the Power BI report.|*not specified*|[Accept-Language HTTP header](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips#AcceptLanguage).|
|ODataMaxPageSize|This parameter limits the number of entities per results page, which allows for more flexibility when connecting to large datasets or using complex queries. It sets the maximum number of records to return for each page when calling an API. For example, if your table **Customers** has 13,000 records and ODataMaxPageSize is set to 5000, Power BI makes 3 API calls to get your customers. The first call gets 5,000 records, the next one gets 5000 more, and the last call gets the remaining 3000. This option can't be higher than the maximum page size enforced by Business Central, which is 20000.<br><br>Setting this parameter ensures efficient and responsive data retrieval, leading to faster insights and decision-making. You can't exceed the maximum page size defined on the service.|5000|[ODataPreferenceHeader.MaxPageSize Property](/dotnet/api/microsoft.odata.odatapreferenceheader.maxpagesize)|
|Timeout|This parameter defines the maximum duration for a request before cancellation. It sets the timeout for each single API call to Business Central. Increasing this value doesn't extend the OData request timeout enforced by Business Central online, which is 8 minutes (00:08:00).<br><br>Setting this parameter helps manage system resources effectively and prevents long-running queries from impacting overall system performance. Users experience minimal delays and interruptions, ensuring a smoother workflow. |00:08:00|[OData.Feed](/powerquery-m/odata-feed) and [Business Central online service limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online)|
|UseReadOnlyReplica|This parameter determines whether requests target the primary database or a read-only replica. Offloading read operations from the primary database can significantly boost performance.<br><br> Setting this property leads to faster data retrieval and improved system stability, especially during peak usage times.|true||

### Configure the advanced options

1. Follow the steps to view the Power Query code from Power BI Advanced Editor
1. In **Advanced Editor**, locate the line that starts with `Source =`.

   ```powerquery
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null),
   ```

1. In the line, replace the fourth parameter of `Dynamics365BusinessCentral.ApiContentsWithOptions` with a Power Query record of properties and values you want to set, for example:

   ```powerquery
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, [UseReadOnlyReplica = true, Timeout = Duration.From("00:07:00"), ODataMaxPageSize = 10000, AcceptLanguage = "it-it"]),
   ```

1. Select **Done** to close **Advanced Editor**.
1. Select **Close & Apply** to save the changes and close Power Query Editor.

## <a name="fix-problems"></a>Troubleshoot Power BI connections

### "Expression.Error: The environment 'Production' doesn't exist." error when specifying a Business Central environment

> **APPLIES TO:** [!INCLUDE [prod_short](includes/prod_short.md)] online

When you connect to [!INCLUDE [prod_short](includes/prod_short.md)] online from [!INCLUDE [powerbi-name](includes/powerbi-name.md)], or when you install a [!INCLUDE [powerbi-desktop-name](includes/powerbi-desktop-name.md)] app from Microsoft Marketplace that uses [!INCLUDE [prod_short](includes/prod_short.md)] data, you might be prompted to input the [!INCLUDE [prod_short](includes/prod_short.md)] environment you want to connect to.

If you get an error similar to "Expression.Error: The environment 'Production' doesn't exist.", follow these steps to troubleshoot:

1. Make sure you're using the right credentials to access [!INCLUDE [prod_short](includes/prod_short.md)]. These credentials might not be the same credentials you use to access [!INCLUDE [powerbi-name](includes/powerbi-name.md)]. [How do I change or clear the account I'm currently using to connect to Business Central from Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)
2. If your environment is an embedded ISV environment, you need to specify the embedded ISV name in parenthesis as part of the environment name. For example, if you want to connect to an environment named Production from the embedded ISV named Fabrikam, you must specify "PRODUCTION (fabrikam)" as environment name.

### "Can't insert a record. Current connection intent is Read-Only." error connecting to custom API page

> **APPLIES TO:** Business Central online

By default, reports that use [!INCLUDE [prod_short](includes/prod_short.md)] data connect to a read-only replica of the [!INCLUDE [prod_short](includes/prod_short.md)] database. In rare cases, depending on the API design, you might get an error when you try to connect to and get data from the API. The error looks like this:

`Dynamics365BusinessCentral: Request failed: The remote server returned an error: (400) Bad Request. (Can't insert a record. Current connection intent is Read-Only. CorrelationId: [...])".`

If you're using a custom API, we recommend you rework the AL code to make sure it doesn't make database modifications when it's just reading data. But in case your scenario requires it, you can [configure the connector to use a read-write connection instead](#advanced-customize-language-timeout-database-replica-or-page-size-for-your-business-central-data-source).

## Related information

[Enable Your Business Data for Power BI](admin-powerbi-setup.md)  
[Business Intelligence](bi.md)  
[Get Ready for Doing Business](ui-get-ready-business.md)  
[Import Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
