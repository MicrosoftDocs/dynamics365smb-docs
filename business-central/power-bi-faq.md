---
title: Power BI FAQ
description: Get answers for some typical questions about working with Power BI and Business Central.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: Power BI, reports, faq, errors
ms.date: 01/19/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Power BI FAQ

This article answers some of the questions you might have about working with Power BI and [!INCLUDE [prod_short](includes/prod_short.md)].

<!-- ## [General questions](#tab/general) -->
## General questions

<!-- 26 -->
### I selected a report for my role center in Business Central. If I later make changes to the report's visuals online, does the role center automatically update to my changes?

Yes. The reports you see inside [!INCLUDE [prod_short](includes/prod_short.md)] are embedded directly from Power BI, and not a copy.

<!-- 3 -->
### Are the Business Central apps for Power BI available in languages other than English?

No. These apps are currently only available in English.

<!-- 24 -->
### Once a report is published on my powerbi.com workspace, can I download its pbix? 

Yes. Learn more at [Download a report from the Power BI service to Power BI Desktop](/power-bi/create-reports/service-export-to-pbix).  

<!-- 27 -->
### Can I download the apps as pbix files?

No. Currently, we don’t offer downloading pbix files for the official Power BI apps, because they're published on Marketplace.

<!-- ## [User access and licensing](#tab/license) -->
## Questions about user access and licensing


<!-- 14 -->
### Do I need a Power BI Pro license to publish reports?

<!-- todo What does " or for every user that consults the published report" mean? fixed -->
No. A Pro license isn't needed to publish reports. The standard (free) Power BI license is enough. Learn more in [Power BI Licensing](admin-powerbi-setup.md#license).

<!-- 15 -->
### Is there anything I can't do with the free license?

You can't share reports or install the Business Central apps for Power BI. The free license allows you to create almost all variations of charts and reports.

<!-- 16 -->
### If someone shares a report with another person, then that person needs a Pro license to see the report. Are there plans to make this capability possible with the free license?

We don't have control over this requirement. Power BI sets this requirement. Learn more at [Share Power BI dashboards and reports with coworkers and others](/power-bi/collaborate-share/service-share-dashboards).  

### How do guest users and delegated admins access my organization's data and reports?

There are some differences and limitations for external users, like guest users and delegated admins. For instance, external users typically have a Power BI license assigned by their own organization. When they sign in to Power BI or Power BI Desktop, they connect to their organization's tenant and shared workspaces by default.

To access your organization's data and shared workspaces or reports, external users must connect to your Microsoft 365 tenant. From Power BI service, they can use the tenant switcher (preview) to connect. Power BI Desktop doesn't support connecting to a provider tenant's data source or service for creating and publishing reports. External users need to use the Power BI service to upload Power BI Desktop files.

<!--
1. Sign in to [Power BI](https://app.powerbi.com).
1. In the upper-right corner, select the profile picture to open the account manager, and then select **Switch** next to **Tenant name**.
1. In the **Switch tenant (preview)** dialog, open the dropdown menu and choose the tenant.-->

Learn more about the features and limitations for guests users in [Distribute Power BI content to external guest users](/power-bi/enterprise/service-admin-azure-ad-b2b).
<!--
To access and design reports with your organization's data, external users must connect to your Microsoft 365 tenant. The connection method differs in Power BI service and Power BI Desktop.

#### In Power BI service
From the Power BI service, use the tenant switcher:

1. Sign in to [Power BI](https://app.powerbi.com).
1. Select your profile picture to open your account manager and select **Switch** next to **Tenant name**.
1. In the **Switch tenant (preview)** dialog, open the dropdown menu and choose the tenant you want to navigate to.

Learn more in [Distribute Power BI content to external guest users](/power-bi/enterprise/service-admin-azure-ad-b2b#tenant-switcher).

#### In Power BI Desktop

The methods in this section require that guest users know the domain name of your Microsoft 365 tenant, such as `contoso.onmicrosoft.com`.

> [!NOTE]
> The methods described in this section aren't supported. You might experience unexpected behavior.

##### Creating and refreshing reports: Change data source to host's Business Central tenant

1. Clear the current data source connection. Learn more in [How do I change or clear the user account I'm currently using to connect to Business Central from Power BI Desktop](#how-do-i-change-or-clear-the-user-account-im-currently-using-to-connect-to-business-central-from-power-bi-desktop).
1. Select **Get Data**.
1. On the **Get Data** page, select **Online Services** > **Dynamics 365 Business Central** > **Connect**.
1. On the **Dynamics Business Central** connector dialog box, select **Sign in** and then follow the instructions to [sign in to the host's organization](#sign-in-to-hosts-organization).

   :::image type="content" source="media/power-bi-desktop-connector-sign-in.png" alt-text="Shows a screenshot of the the Business Central connector sign-in dialog box":::

##### Publishing reports: Switch to host's Business Central tenant

1. Open Power BI Desktop.
1. In the upper-right corner, select **Sign in**.

   If you're already signed in, first sign out by selecting your name or profile picture, and then **Sign out**.

1. Enter your email address, select **Continue**, and then follow the instructions to [sign in to the host's organization](#sign-in-to-hosts-organization).

##### Sign in to host's organization

1. On the **Pick an account** dialog box, select **Use another account**.
1. On the **Sign in** dialog box, select **Sign-in options**.
1. On the **Sign in options** dialog box, select **Sign in to an organization**.
1. On the **Find your organization** dialog box, enter the domain name of the tenant, for example, `contoso.onmicrosoft.com`.
1. Select **Next**.
1. On the **Pick an account** dialog box, select your account, and then sign in usual.
1. On the **Dynamics Business Central** connector dialog, select **Connect**.-->

<!-- ## [Designer](#tab/designer) -->
## Questions about the Power BI Designer

<!-- 7 -->
### Does the connector work with pages exposed as web services?

Web services are an old technology and aren't recommended to use with Power BI. The Power BI connector supports both Business Central web services and API pages, but API pages generally have better performances and are more suited for making data available to other systems. Learn more at [Enable Power BI connector to work with Business Central APIs, instead of with web services only](/dynamics365-release-plan/2021wave1/smb/dynamics365-business-central/enable-power-bi-connector-work-business-central-apis-instead-web-services-only).

### Can I build a Power BI report using the Sales Invoice Lines or Journal Lines APIs?

The most commonly used line records are available in the [Business Central APIs v2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/)). So you can use them to build reports in Power BI by selecting them in the **Dynamics 365 Business Central** connector. However, the **Lines** APIs are designed for use with specific filters only, and might not work in your scenario. You might get an error similar to "You must specify an ID or a Document ID to get the lines." To fix this problem, do the following steps when getting data from Business Central for the report in Power BI Desktop:

1. Instead of including the data source for the lines entity, add the parent data source. For example, add **Sales Invoice** instead of **Sales Invoice Lines**.
2. Select **Transform Data** in the Power BI Desktop action bar.
3. Select the query you just added, for example **Sales Invoices**.
4. To reduce the number of records loaded in your report, apply any needed filtering on the records.
5. Scroll vertically until you find a column named as the lines, for example **SalesInvoiceLines**.
6. Select the expand button in the header of the column, next to the column name.

   :::image type="content" source="media/saleinvoicelines.png" alt-text="Shows the SalesInvoiceLines column in Power BI Desktop.":::
<!-- 11 --> 
### Is it possible to choose which Business Central environment to get data from for Power BI, for example, like a sandbox or production environment? 

Yes. It can be easily chosen. When you connect to Business Central using the connector, you have to choose the environment and company name.

<!-- 6 --> 
### Can I merge data from several production environments of the same tenant?

Yes. In Power BI, just run the "get data" operation again and choose the environment you want.

<!-- 25 -->
### Which pages in Business Central have the Power BI Report part?  

Currently, there are a few selected pages that have a FactBox with a **Power BI Reports** part for displaying a report. 

On list pages, the **Power BI Reports** part is filtered to show reports that pertain to data in the list. Here's the list type pages that include the **Power BI Reports** part:

|Page ID|Name|
|-------|----|
|22|Customer List|
|27|Vendor List|
|31|Item List|
|9305|Sales Order List|
|9308|Purchase Invoices|

Here are other pages that contain the larger, nonfiltered **Power BI Reports** part:

|Page ID|Name|
|-------|----|
|1156|Company Detail|
|4013|Intelligent Cloud Insights |
|9006|Order Processor Role Center|
|9008|Whse. Basic Role Center|
|9010|Production Planner Role Center|
|9015|Job Project Manager RC|
|9016|Service Dispatcher Role Center|
|9022|Business Manager Role Center|
|9024|Security Admin Role Center|
|9026|Sales & Relationship Mgr. RC|
|9027|Accountant Role Center|

> [!TIP]
> We don't have plans to add it to all list pages at the moment. However, you can create a simple page extension that adds the **Power BI Reports** part in a FactBox. Learn more at [Adding Power BI Report Parts to Pages](/dynamics365/business-central/dev-itpro/developer/devenv-power-bi-report-parts) in the Developer and IT Pro help.

<!-- 5 -->
### Is there any way to filter a dataset from Business Central *before* I pull it into Power BI, instead of applying filters afterwards?

To filter larger datasets, the easiest way is to set a filter on your Power BI report by editing directly the Power Query formula. Most of the filters you set this way are passed on to Business Central through query folding. See [Incremental refresh for datasets](/power-bi/admin/service-premium-incremental-refresh).

There's currently no way of setting a filter for the web service data from within Business Central. If your application needs to set a filter from within Business Central, you must create a custom Business Central App for this purpose.

<!-- 10 -->
### From Power BI, besides using a query, is there another way to get data from Business Central tables that don't have an associated page? For example, like the *Item Attributes Value Mapping* table.

No. Not at this point.

<!-- 12 --> 
### Are published queries faster to use than published pages?

When it comes to web services, published queries are usually faster than equivalent published pages. The reason is that queries are optimized for reading data and don’t contain expensive triggers like OnAfterGetRecord.

Web services are based on pages or queries that are built for access from the web and not optimized for access from external services. Even though the Business Central connector still supports getting data from web services, we encourage you to use API pages instead of web services whenever possible.

<!-- 13 --> 
### Is there a way for an end user to create a web service with a column that's in a Business Central table, but not a page? Or does the developer have to create a custom query? 

There's currently no way of adding a new field to a web service. API pages offer full flexibility on the page structure, so a developer can create a new API page to meet this requirement. 

<!-- 28 --> 
### Can I connect Power BI to a read-only database server of [!INCLUDE [prod_short](includes/prod_short.md)] online? 

By default, the Power BI connector reads data from a read-only replica of the Business Central database, which is the case for all reports created after February 2022. This behavior causes your reports to refresh faster and has less impact on performance if you're using Business Central while a report is refreshing. We still recommend that you schedule your reports to refresh outside of normal working hours whenever possible.

If you have old reports based on Business Central data, they don't connect to the read-only database replica. In this case, consider recreating the query inside Power BI so that it uses the latest defaults.

### <a name="databasemods"></a>When I use the Power BI connector to connect to my custom [!INCLUDE [prod_short](includes/prod_short.md)] API page, I get the error "Cannot insert a record. Current connection intent is Read-Only." How can I fix it?

Reports that use Business Central data connect to a read-only replica of the Business Central database by default. In rare cases, this behavior might cause the error "Current connection intent is Read-Only.". This error typically happens because your custom API is making modifications to Business Central records while Power BI tries to get the data. In particular, it happens as part of the AL triggers: OnInit, OnOpenPage, OnFindRecord, OnNextRecord, OnAfterGetRecord, and OnAfterGetCurrRecord.

To fix this issue by forcing the Business Central connector to allow this behavior, see [Building Power BI Reports to Display Business Central Data - Fix Problems](across-how-use-financials-data-source-powerbi.md#fix-problems).

<!--
In general, we recommend avoiding any database modifications in API pages when they're opening or loading records, because they cause performance issues and might cause your report refresh to fail. In some cases, you might still need to make a database modification when your custom API page opens or loads records. You can force the Business Central connector to allow this behavior. Do the following steps when getting data from Business Central for the report in Power BI Desktop:

1. Start Power BI Desktop.
2. In the ribbon, select **Get Data** > **Online Services**.
3. In the **Online Services** pane, select **Dynamics 365 Business Central**, then **Connect**.
4. In the **Navigator** window, select the API endpoint that you want to load data from.
5. In the preview pane on the right, you'll see the following error:

   *Dynamics365BusinessCentral: Request failed: The remote server returned an error: (400) Bad Request. (Cannot insert a record. Current connection intent is Read-Only. CorrelationId: [...])".*

6.	Select **Transform Data** instead of **Load** as you might normally do.
7. In **Power Query Editor**, select **Advanced Editor** from the ribbon.
8.	Replace the following line:

   ```
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null),
   ```

   with the line:

   ```
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, [UseReadOnlyReplica = false]),
   ```

9.	Select **Done**.
10. Select **Close & Apply** from the ribbon to save the changes and close Power Query Editor.

-->
### <a name="perms"></a>How do I change or clear the user account I'm currently using to connect to Business Central from Power BI Desktop?

In Power BI Desktop, do the following steps:

1. In the File menu, select **Options and settings** > **Data source settings**.
2. Select **Dynamics Business Central** from the list, then select **Clear permissions** > **Delete**.

Then next time you connect to Business Central to get data, you'll be asked to sign in.


<!-- ## [Performance](#tab/performance) -->
## Questions about data refresh performance

<!-- 17 -->

### Is it faster to get data using API pages than using web services?

Yes. Our tests indicate that API pages are up to 25% more performant than web services.

<!-- 18 -->
### Are there plans to have a mirror on the Azure SQL Database instance, which I can connect to directly?

No. Not at this point. You can only communicate with Business Central through APIs.

<!-- 19 -->
### Loading data from Business Central web services seems slow. Is there any way to get data directly from the SQL database table?

No. Direct access to the database isn't possible, but switching to API pages helps greatly.

## Troubleshooting questions

### My semantic model does not refresh. How do I see what is wrong?

[!INCLUDE [powerbi-refresh-tsg-include](includes/powerbi-refresh-tsg-include.md)]

<!-- ## [Advanced](#tab/advanced) -->
## Advanced questions
<!-- 1 -->

### Are there plans for the Power BI connector to support the incremental refresh features in the Power BI Service?

Yes. It's on our roadmap.

<!-- 2 -->
### If a Business Central on-premises solution doesn't have internet access, can I still use Power BI?
<!-- todo: please explain this one-->

Yes. In this case, you use Power BI Desktop locally and connect to the Business Central on-premises. Once connected, can create and view reports, but you just can't publish them to the Power BI Service. 
<!-- 20 -->
### Are there any plans to make it possible to replicate Business Central online databases so they're accessible for read-only SQL queries? This capability would support incremental refresh and be a lot faster than APIs or web services.

<!-- todo: what does "BC-Saas-DB-replicated DB accessible" mean? fixe-->
Yes. We have this feature on our long-term roadmap. 

<!-- 21 -->
### If I use Azure Data Factory to get data from Business Central and consume it on Power BI, does that help in increase in performance? 

Yes. This advanced scenario helps Business Central stay performant, because the data access would be done via the Azure Data Factory.

<!-- 22 -->
### Are there any plans to support Power BI deployment pipelines or a way to build deployment pipelines for PBI reports, similar to extensions? Or maybe even a simple API in the Business Admin Center? 

We're looking into this feature. Power BI offers rich APIs to control report deployments. Learn more at [Introduction to deployment pipelines](/power-bi/create-reports/deployment-pipelines-overview).

### When I get data from Business Central to use in my Power BI reports, I see some values like "_x0020_". What are these values?

Some API pages, including most API v2.0 pages, have fields based on [AL Enum objects](/dynamics365/business-central/dev-itpro/developer/devenv-extensible-enums). Fields based on AL enum objects must have names that are consistent and always the same, so that filters on the report always work&mdash;no matter the language or operating system you're using. For this reason, the fields based on AL enums aren't translated and are encoded to avoid any special character, including the space. In particular, whenever there's an empty option in the AL Enum object, it's encoded to "_x0020_". You can always apply a transformation to your data on Power BI if you want to display some different value for these fields, for example "Empty".

---

## Related information

[Power BI licensing](admin-powerbi-setup.md#license)  
[Business Central and Power BI introduction](admin-powerbi.md)  
[Power BI Integration Overview](admin-powerbi-overview.md)  
[Enabling Power BI in Business Central](admin-powerbi-setup.md)  
[Work with Power BI reports in Business Central](across-working-with-powerbi.md)  
[Connect to Power BI from Business Central on-premises](across-working-with-business-central-in-powerbi.md)  
[Building Power BI Reports to display Business Central data](across-how-use-financials-data-source-powerbi.md)  
[Power BI documentation](/power-bi/)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
