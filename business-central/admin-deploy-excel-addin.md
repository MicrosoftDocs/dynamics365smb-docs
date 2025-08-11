---
title: Getting the Business Central add-in for Excel
description: Learn how to get users the Business Central Add-in for Excel. 
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.form: 1480
ms.search.keywords: Excel, add-in, centralized deployment, M365 admin center, individual acquisition, appsource
ms.date: 12/16/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Get the Business Central add-in for Excel

[!INCLUDE[prod_short](includes/prod_short.md)] includes an add-in for Excel that lets users select the **Edit in Excel** action on certain pages to open the data in an Excel worksheet. This action is different than the **Open in Excel** action because it lets users make changes in Excel, then publish the changes back to [!INCLUDE[prod_short](includes/prod_short.md)]

## Overview

### About the add-in

The add-in is called **Microsoft Dynamics Office Add-in** and it's available for installation from the [Office Store (AppSource)](https://appsource.microsoft.com/). With the add-in installed, the **Edit in Excel** action is available on most list and list part pages from the **Share** icon ![Share a page in another app.](media/share-icon.png). For more information about using the add-in, see [View and Edit in Excel From Business Central](across-work-with-excel.md).

> [!NOTE]
> The add-in works on Windows only.

### About deployment as an admin

With [!INCLUDE[prod_short](includes/prod_short.md)] online, there are a few deployment options for getting the add-in to users. One option is *individual acquisition*, where users install the add-in themselves. With this option, users must have access to downloading files from the Office Store. Another option is to set up *Centralized Deployment* in the Microsoft 365 admin center to automatically deploy the add-in to your entire organization, groups, or specific users. Centralized Deployment provides a way to get the add-in to users if your organization doesn't give users access to the Office Store.

For the user, the installation experience is different for the two deployment scenarios:

- With individual acquisition, the first time users choose the **Edit in Excel** action, the **New Office Add-in** pane opens in Excel. To install the add-in, the user chooses **Trust this add-in**, which in turn installs the add-in directly from the Office Store. Users then sign in to [!INCLUDE[prod_short](includes/prod_short.md)] using their user name and password.

- With Centralized Deployment, the first time users choose the **Edit in Excel** action, the add-in is automatically installed in Excel from Centralized Deployment; not the Office Store. The only thing users have to do is sign in to [!INCLUDE[prod_short](includes/prod_short.md)].

With both these deployment options, the add-in is automatically configured to connect to [!INCLUDE[prod_short](includes/prod_short.md)]. A third deployment option is a manual installation of the add-in directly from Excel. With this option, users need to configure the add-in to connect to [!INCLUDE[prod_short](includes/prod_short.md)].

### <a name="switch"></a>Switching from individual acquisition to Centralized Deployment or the other way around

When you change from individual acquisition of the add-in to Centralized Deployment, or vice versa, it affects Excel files that users created before the transition. After the transition, users can still open any Excel worksheets previously created using the **Edit in Excel** action or created manually by configuring the Excel add-in. But they can't update the data in the file from Business Central or push updates to Business Central.

This situation happens because each Excel file gets assigned an "add-in" identifier. In the transition to or from Centralized Deployment, a different ID is assigned, so the earlier ID becomes blocked.

## Preparation (on-premises only)

[!INCLUDE[prod_short](includes/prod_short.md)] on-premises requires that your environment is configured for the add-in. If not, the **Edit in Excel** action isn't available to users. Learn more in [Setting up the Business Central add-in for Excel in Business Central on-premises](/dynamics365/business-central/dev-itpro/administration/configuring-excel-addin) in the Developer and IT Pro help.

## Deploy the add-in by using Centralized Deployment

Centralized Deployment is a feature in the Microsoft 365 admin center that you use to automatically install add-ins in users' Office apps, like Excel. To help you with Centralized Deployment, [!INCLUDE[prod_short](includes/prod_short.md)] includes the **Excel Add-in Centralized Deployment** assisted setup.

### Before you begin

- Learn more about preventing users from downloading from the Office store at [Manage add-ins in the admin center](/microsoft-365/admin/manage/manage-addins-in-the-admin-center).
- Verify that Centralized Deployment works for your organization. Learn more at [Determine if Centralized Deployment of add-ins works for your organization](/microsoft-365/admin/manage/centralized-deployment-of-add-ins).
- Learn more about transitioning from individual acquisition at [Switching from individual acquisition to Centralized Deployment](#switch).

> [!NOTE]
> Enabling Centralized Deployment affects features that use the Excel add-in, such as the **Edit in Excel** action. It has no effect on other Excel-related features or permissions assigned to users in [!INCLUDE[prod_short](includes/prod_short.md)].

### Set up Centralized Deployment of the add-in

In this task, you work in both [!INCLUDE[prod_short](includes/prod_short.md)] and the Microsoft 365 admin center.

1. In [!INCLUDE[prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Excel Add-in Centralized Deployment**, and then choose the related link.
2. Read the information on the **Business Central Excel add-in setup** page and choose **Next**.
3. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/?linkid=2163967) and go to **Integrated Apps**<!--**Add-ins**-->.

    Complete the following steps to configure the add-in to deploy from the Office Store: 
    1. Choose **Get apps** to open Office Store (AppSource). <!--**Deploy Add-in** 5. In the **Deploy a new add-in**, select **Choose from the store**.-->
    2. Search for **Microsoft Dynamics Office Add-in**, then select **Get it now**. <!--On the **Select add-in** page, search for and select **Microsoft Dynamics Office Add-in** > **Add** > **Continue**.-->
    3. On the **Add Users** page, specify the users that you want to deploy the add-in for, then choose **Next**.<!--On the **Configure add-in**, specify the users that you want to deploy the add-in for.-->
    4. Review the **Accept permissions requests**, then choose **Next** > **Finish Deployment**.
    5. Wait for the green check mark next to **Deployed** appears for the add-in, then choose **Done**. <!--Select **Deploy** and wait til successful, then **Next** > **Continue**.-->

       The add-in appears on the **Add-ins** page. For more information about deploying add-ins in the Microsoft 365 admin center, see [Deploy add-ins in the admin center](/power-platform/admin/use-service-admin-role-manage-tenant?azure-portal=true).
4. Go back to **Excel Add-in Centralized Deployment** assisted setup in [!INCLUDE[prod_short](includes/prod_short.md)], and choose **Next**.
5. Turn on **Use Centralized Deployment**, and choose **Finish**.

    If you don't turn on this switch, [!INCLUDE[prod_short](includes/prod_short.md)] gets the add-in directly from the Office Store.

When finished, you can always change the deployment in the Microsoft 365 admin center, like assigning more users. For more information about deploying add-ins in the admin center, see [Deploy add-ins in the admin center](/power-platform/admin/use-service-admin-role-manage-tenant?azure-portal=true).

> [!IMPORTANT]
> If you have more than one environment, you must run the **Excel Add-in Centralized Deployment** assisted setup on each environment that you want to use Centralized Deployment. However, you don't have to configure the Centralized Deployment in Microsoft 365 again. The only thing you have to do is turn on the **Use Centralized Deployment** switch in the assisted setup. 

> [!NOTE]
> It can take up to 24 hours before the add-in deploys automatically in Excel for users.

## <a name="install"></a>Individual acquisition: Install the add-in manually for your own use

In most cases, when you open Excel from Business Central, the add-in is either installed automatically for you or you're prompted to install it. There might be cases, however, where you have to manually install the add-in.

1. Open Excel, then open any Excel workbook.
1. On the **Home** tab, select **Add-ins** > **More Add-ins**.
1. Go to **Admin managed** and look for **Microsoft Dynamics Office Add-In**. If you see it there, select it, and then choose **Add**. If you don't see it, go to **Store**, and then search for *Microsoft Dynamics Office add-In* and follow the instructions to add it.

When the add-in is installed, it shows up as a panel in Excel. Next, configure the connection.

### Configure the Business Central connection

If a user can't connect automatically, you can unblock them by asking them to follow these steps:

1. In the **Microsoft Dynamics** add-in pane in Excel, choose **Add server information**. If you don't see it, choose the ![More option button in Excel.](media/cogwheel.png) icon at the top to open the options dialog. 
2. For [!INCLUDE[prod_short](includes/prod_short.md)] online, set **Server URL** to `https://exceladdinprovider.smb.dynamics.com`. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, set it to the URL of the web client, like `https://myBCserver/240`.
3. Choose **OK**, and then confirm that the app reloads.
4. When prompted, sign in with your Business Central user name and password.
5. Optionally, choose the environment and company that you want to connect to.

The add-in is now connected to [!INCLUDE [prod_short](includes/prod_short.md)], and you can edit data and publish the changes to [!INCLUDE [prod_short](includes/prod_short.md)].  

## Prepare devices and network for the Excel add-in

Network services such as proxies or firewalls must allow routing between each client device on which the add-in is installed and many service endpoints. For a list of endpoints, go to [Preparing your network for the Excel add-In](/dynamics365/business-central/dev-itpro/administration/configuring-network-for-addins).

## Troubleshooting

Sometimes, users run into problems with the Excel add-in. This section gives tips for how to unblock users in certain circumstances.

|Problem  |Solution or workaround  |Comments  |
|---------|---------|---------|
|The add-in doesn't start. <br><br>For example, the user gets the message "Add-in Warning: This add-in is no longer available" when trying to use the add-in. This particular problem can happen if Centralized Deployment is configured correctly, but the user wasn't assigned access.|Check whether the add-in is deployed centrally. Or, check whether the user is blocked from installing it locally. | The admin can configure Office so that users can't acquire add-ins. In that case, the admin must deploy the add-in centrally. For more information, see [Deploy add-ins in the admin center](/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide&preserve-view=true).|
|Data doesn't load into Excel.|Test the connection by opening another list in Excel from [!INCLUDE [prod_short](includes/prod_short.md)]. Or, open the workbook in Excel in a browser.|If the user specified a company name that contains special characters, the add-in can't connect. |
|Data can't publish back to [!INCLUDE [prod_short](includes/prod_short.md)].|Test the connection by opening the workbook in Excel in a browser. |Sometimes an extension can block the publishing job. If the page is extended or customized, remove the extensions, and then try again.|
|The dates are wrong.  |Excel might show times and dates in a different format than [!INCLUDE [prod_short](includes/prod_short.md)]. This condition doesn't make them wrong, and the data in [!INCLUDE [prod_short](includes/prod_short.md)] doesn't get messed up.|         |
|For some list pages, editing multiple lines in Excel consistently causes errors. This condition can occur if OData calls include FlowFields and fields outside of the repeater control.|On the **Web Services** page, select the **Exclude Non-Editable FlowFields** and **Exclude Fields Outside of the Repeater** checkboxes for the published page. Selecting these checkboxes excludes noneditable FlowFields and fields from the eTag calculation. |These checkboxes are hidden by default. To show them on the **Web Services** page, use [personalization](/dynamics365/business-central/ui-personalization-user). |
|Users can no longer sign in to the add-in. When they try to sign in, the process stops without completing.| This problem might happen because of an update that we made to the add-in, sometime in July 2022. For more information and a fix, see [Modify the Excel Add-in Configuration to Support July 2022 Update](/dynamics365/business-central/dev-itpro/administration/update-excel-addin-configuration).|Applies to [!INCLUDE [prod_short](includes/prod_short.md)] on-premises only.|
| The add-in communicates using the API v2.0 for Dynamics 365 Business Central, and any limitations of this API are automatically inherited. An example limitation is if you try to edit a list and the underlying card uses a confirmation dialog in its AL logic, for example, as its validation logic. | Sometimes there's nothing to do because it's a design choice that the user must explicitly confirm the change. If the confirmation is negligible when using **Edit in Excel**, then you can wrap the confirmation dialog call in an if-conditional statement that checks whether the client type is different from ODataV4, for example, `if SESSION.CurrentClientType() <> ClientType::ODataV4 then`. | There might be other clients that you want to remove the confirmation dialog from, such as OData and SOAP. |
| You see the message dialog when clicking Edit In Excel "Certain filters applied on the page are not available in Office, so more rows will be shown compared to Business Central. Removed Filters: ...".| If you have added the field the filter is applied to through an AL extension. Then you need to make sure that the page field name and the underlying table field name are both identical. e.g. for the page field definition ```field("Customer Name", Rec."Customer Name")``` the table field definition needs to be identical ```field(1; "Customer Name"; Text)```   | If the removed filter is related to one of the Microsoft often pages and fields then the only work-around is to filter manually on the field via the Office Add-In when the workbook is opened. |

## Known limitations in business logic

|Page  |Limitation| Comments  |
|-------|---------|---------|
|Sales Orders|Error message: 'Microsoft Dynamics 365 Business Central Data Services attempted to issue a client callback to run page 301 Ship-to Address List as modal.' Client callbacks aren't supported on Microsoft Dynamics 365 Business Central Data Services. | The **Ship-to Code** on the **Sales Order** page is editable only with specific Ship-to options. Setting **Alternate Shipping Address** to **Ship-to** opens the **Ship-to Address List** modal dialog, which isn't compatible with Edit in Excel.|  
|Project Journal|Update of the **Unit Price** field doesn't trigger an update of the **Line Amount**. Instead, it updates **Line Discount**.| Using the web client, you can update fields in any order—price, amount, line discount. Other fields are updated automatically. To avoid cascade updates, the fields have advanced logic that relies on xRec, which behaves differently when called via APIs.|

## Known limitations in metadata generation

When using **Edit in Excel** in [!INCLUDE [prod_short](includes/prod_short.md)], either by selecting the **Edit in Excel** action on a page or when the Excel add-in loads after opening an Excel workbook, you might encounter the following error: _Metadata was unable to be retrieved for entity \<entity name\> as it was not found_.

This error occurs when the page you're attempting to modify becomes too complex for **Edit in Excel** to process effectively. The primary cause is the installation of multiple extensions that add fields with identical field names to the same parent page, leading to conflicts. It's also possible for a single extension to block the metadata generation.

### Single extension blocking metadata creation

Consider the following scenario involving extension _A_, which includes the page extension _CustomerCardExtA_ and the page _WebViewerA_ where _PageType = CardPart_.

When metadata is generated for the _Customer Card_ page, the algorithm evaluates each individual field, including those fields added by extensions. However, if extension _A_ is installed, this process fails because _WebViewerA_ doesn't share the same source table as the _Customer Card_ page.

To resolve this issue, you should add a _Customer_ `SourceTable` property to the _WebViewerA_ page. An example of this modification can be observed in the code snippets containing _CustomerCardExtB_ and _WebViewerB_.

In some cases, you might need to embed the `CardPart` on multiple pages without referencing a specific source table. For such scenarios, we recommend creating a separate `CardPart` for each page where you also need to generate metadata and refactoring the shared logic into a codeunit.

```AL
pageextension 50120 CustomerCardExtA extends "Customer Card"
{
    layout
    {
        addlast(content)
        {
            part("Bing WebViewer"; "WebViewer")
            {
                ApplicationArea = All;
            }
        }
    }
}
```

```AL
page 50120 "WebViewerA"
{
    ApplicationArea = All;
    Caption = 'WebViewer', Locked = true;
    PageType = CardPart;

    layout
    {
        area(Content)
        {
            usercontrol(WebViewer; WebPageViewer)
            {
                #region ControlAddInReady
                trigger ControlAddInReady(callbackUrl: Text)
                begin
                    CurrPage.WebViewer.Navigate('https://www.bing.com')
                end;
                #endregion ControlAddInReady
            }
        }
    }
}
```

```AL
pageextension 50120 CustomerCardExtB extends "Customer Card"
{
    layout
    {
        addlast(content)
        {
            part("Bing WebViewer"; "WebViewer")
            {
                ApplicationArea = All;
            }
        }
    }
}
```

```AL
page 50120 "WebViewerB"
{
    ApplicationArea = All;
    Caption = 'WebViewer', Locked = true;
    PageType = CardPart;
    SourceTable = Customer;

    layout
    {
        area(Content)
        {
            usercontrol(WebViewer; WebPageViewer)
            {
                #region ControlAddInReady
                trigger ControlAddInReady(callbackUrl: Text)
                begin
                    CurrPage.WebViewer.Navigate('https://www.bing.com')
                end;
                #endregion ControlAddInReady
            }
        }
    }
}
```

### Multiple extensions causing collisions

To resolve this issue, there are two potential solutions:

1. **Disable extensions**: To identify which extension is causing the conflict, you can disable extensions that affect the page one at a time. However, this approach might not be ideal if the extensions in question are necessary for your business processes.

2. **Modify extension code**: This solution involves analyzing the root cause of the issue and addressing it by modifying the code of the conflicting extensions.

To better understand this issue, consider the following example involving the **Customer Card** page (ID 21). When you are on the **Customer List** page (ID 22) and select **Edit in Excel**, a web service is generated in the background that exposes the fields from the **Customer Card** page. This web service includes all page fields defined on the **Customer Card** page, while table fields are only exposed if they correspond to a page field or are part of the primary key.

When an extension is installed that extends the **Customer Card** page, the fields added by the extension are also exposed in the web service. While extensions can't create page fields with the same names as those fields already existing on the **Customer Card** page, conflicts can still arise when multiple extensions add fields with identical names.

For example, suppose the following extension, referred to as _A_, is installed:

```AL
using Microsoft.Sales.Customer;

// Extension A
pageextension 50101 CustomerCardExtA extends "Customer Card"
{
    layout
    {
        addLast(General)
        {
            field("ShoeSize"; Rec.ShoeSize)
            {
                ApplicationArea = ALL;
                Caption = 'ShoeSize';
            }
        }
    }
}

tableextension 50101 CustomerTableExtension extends Customer
{
    fields
    {
        field(50100; ShoeSize; Integer) { }
    }
}
```

Now, consider that another extension, referred to as _B_, is installed, which also modifies the **Customer Card** page:

```AL
using Microsoft.Sales.Customer;

// Extension B
pageextension 50102 CustomerCardExtB extends "Customer Card"
{
    layout
    {
        addLast(General)
        {
            field("ShoeSize"; Rec.ShoeSizeField)
            {
                ApplicationArea = ALL;
                Caption = 'ShoeSize';
            }
        }
    }
}

tableextension 50102 CustomerTableExtension extends Customer
{
    fields
    {
        field(50105; ShoeSizeField; Integer) { }
    }
}
```

In this scenario, both extensions A and B add a page field named `ShoeSize` to the **Customer Card** page. This condition results in a conflict, which leads to a metadata generation failure for the **Customer Card** page.

To resolve this issue, you need access to the code of at least one of the extensions, and then to modify the conflicting page field names to avoid collisions.

<!--
## Deploy the Excel add-in for Business Central online

For [!INCLUDE [prod_short](includes/prod_short.md)] online, the administrator can deploy the add-in for all users. But users can also install the add-in themselves, provided they have permission to configure their Office experience.  

> [!TIP]
> In some organizations, administrators cannot deploy add-ins centrally. For more information, see [Determine if Centralized Deployment of add-ins works for your organization](/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide&preserve-view=true).

### To deploy the Excel add-in for all users

1. As the administrator, sign in to the Microsoft commercial website and find the add-in at [https://appsource.microsoft.com/product/office/WA104379629](https://appsource.microsoft.com/product/office/WA104379629).
2. Choose the **Get it now** button.

    You'll be redirected to the Microsoft 365 admin center.
3. In the left panel, go to **Settings**, and then choose **Add-ins**.
4. In the **Configure add-in** pane, specify which users to grant access to the add-in.
5. Save your changes.


### To add the Excel add-in locally

1. Open Excel, and then open any Excel workbook.
2. On the **Insert** menu, choose **Office Add-ins**, and then choose **Admin managed** or **Store** as appropriate.
3. Search for *Dynamics Office Add-In*, and then install the add-in.

When the add-in is installed, it shows up as a panel in Excel. Next, you must configure the connection.

> [!TIP]
> If the workbook is not automatically saved to the user's OneDrive, then recommend them to save all workbooks that they export from [!INCLUDE [prod_short](includes/prod_short.md)].When they open the workbook again, the connection is still available, so they do not have to configure the connection again.

> [!NOTE]
> In certain deployments, the administrator must configure network access to unblock the Excel add-in. For more information, see [Preparing Your Network for the Excel Add-In](configuring-network-for-addins.md).-->

## Related information

[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Work with Business Central](ui-work-product.md)  
[Enhancements to Excel integration in 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-business-central/enhancements-excel-integration)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
