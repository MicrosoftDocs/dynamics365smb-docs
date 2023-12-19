---
title: Working with Power BI Reports in Business Central| Microsoft Docs
description: Get insight, business intelligence, and KPIs from your Business Central data with Power BI.
author: jswymer

ms.topic: get-started
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 12/19/2023
ms.author: jswymer
---
# Work with Power BI Reports in [!INCLUDE [prod_short](includes/prod_short.md)]

In this article, you learn some of the basics about viewing Power BI reports, including scorecards, in [!INCLUDE [prod_short](includes/prod_short.md)].

## Overview

Power BI reports give you insight into your [!INCLUDE[prod_short](includes/prod_short.md)]. Various pages in [!INCLUDE [prod_short](includes/prod_short.md)] include a Power BI reports part that can display Power BI reports. The role center is a typical page where you'll see a Power BI reports part. Some list pages, like **Items**, also include a Power BI part.

[!INCLUDE [prod_short](includes/prod_short.md)] works together with the Power BI service. Reports for displaying in [!INCLUDE [prod_short](includes/prod_short.md)] are stored in a Power BI service. In [!INCLUDE [prod_short](includes/prod_short.md)], you can switch the report displayed in the Power BI part to any Power BI report available in your Power BI service. The first time you sign into [!INCLUDE [prod_short](includes/prod_short.md)], and until you connect to a Power BI service, parts will be empty, as shown here:

![Power BI part in Business Central.](./media/power-bi-part.png)

## Get Started

### Prerequisites

If you're using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, it must be enabled for Power BI integration. This task is typically done by an administrator. For more information, see [Set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for Power BI integration](admin-powerbi-setup.md#setup).

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] online is already set up to integrate with Power BI.

### Sign up Power BI

Before you can use Power BI with [!INCLUDE[prod_short](includes/prod_short.md)], you'll need to sign up for the Power BI service. If you haven't already signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use your work email address and password.

## <a name="connect"></a>Connect to Power BI - one time only

When you first sign into [!INCLUDE [prod_short](includes/prod_short.md)], you'll probably see an empty Power BI part (as shown in the previous figure) on various pages. The first thing to do is to connect to your Power BI account. Once connected, you can see reports. You only have to do this step once.

1. Select the **Get Started with Power BI** link in the **Power BI Reports** part.
2. The **Set Up Power BI Reports in Business Central** assisted setup starts. Select **Next** to continue.
3. On the **Check your Power BI License** page. Do one of the following steps:

    - If you haven't yet signed up for Power BI, select the [Go to Power BI homepage](https://powerbi.microsoft.com). Sign up for an account, then come back to [!INCLUDE[prod_short](includes/prod_short.md)] and finish the setup.

    - If you already have a license, select **Next**.
4. In the next page, [!INCLUDE[prod_short](includes/prod_short.md)] will now upload a demo report to Power BI. This step will take a few minutes, so it's done in the background. To complete the setup, select **Next**, then **Finish**.

The connection process starts. During the process, [!INCLUDE [prod_short](includes/prod_short.md)] communicates with the Power BI service to determine if you have a valid Power BI account and license. Once your license is verified, the default Power BI report displays on the page. If there a report isn't shown, you can select a report from the part.

> [!TIP]
> With [!INCLUDE [prod_short](includes/prod_short.md)] online, this this step will automatically upload default Power BI reports used in [!INCLUDE [prod_short](includes/prod_short.md)] to your Power BI workspace.

#### From [!INCLUDE [prod_short](includes/prod_short.md)] on-premises

Connecting to Power BI from [!INCLUDE [prod_short](includes/prod_short.md)] is similar to online. However, you might be prompted on the **MICROSOFT ENTRA SERVICE PERMISSIONS** page to grant access to Power BI Services. To grant access, select **Authorize Azure Services**, and then **Accept**.

Once connected, you can select a report from the Power BI part on pages.

## Work with Power BI reports

### Show reports on list pages

[!INCLUDE[prod_long](includes/prod_long.md)] includes a Power BI FactBox on several key list pages. This FactBox provides extra insight into the data in the list. As you move between rows in the list, the report is updated and filtered for the selected entry.

To learn how to create reports for list pages, see [Creating Power BI Reports for Displaying List Data in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

> [!TIP]
> If you don't see the Power BI FactBox, it might be hidden on your workspace by personalization. Select the ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, and then select **Personalize** action. For more information, see [Personalize Your Workspace](ui-personalization-user.md).
>
> Or if you have an older version of Business Central, go to the action bar, select **Actions** > **Display** > **Show/Hide Power BI Reports**.

### Switch reports

A Power BI part on a page can display any Power BI report that's available to you. To switch to view another report, choose the **Select Report** action from the drop-down command list at the top of the part.  

The **Power BI Reports Selection** page shows a list of all the Power BI reports that you have access to. This list is retrieved from any of your own workspaces or workspaces that have been shared with you in the Power BI service. Select the **Enable** box for each report that you want to display on the page, and then choose **OK**. You'll return to the page, and the last report you enabled will appear. Using the drop-down command list, use the **Previous** and **Next** commands to navigate between reports.  

### Get more reports

If you don't see any reports on the **Power BI Reports Selection** page, or don't see the report you want, choose **Get Reports**. This action lets you look for reports from two locations: *My Organization* or from *Services*.

- Choose **My Organization** to go to the Power BI services. From here, you can view the reports within your organization that you've been given rights to view. You can then add them to your workspace.
- Choose **Services** to go to Microsoft AppSource where you can install Power BI apps.  

> [!TIP]
> If you have Power BI Desktop, you can also create new Power BI reports. Then, once those reports are published to your Power BI workspace, they will appear on the **Power BI Reports Selection** page.  

### Manage and modify reports

You can make changes to a report in the Power BI part. The changes that you make will then be published to the Power BI service. If the report is shared with other users, they'll also see the changes, unless you save the changes to a new report.

To modify a report, choose the **Manage Report** action from the drop-down command list in the Power BI part. Then start making changes. Once you finish making changes, select **File** > **Save**. If it's a shared report, and you don't want to make the change for all users, select **Save As** to avoid making this change for all users.

When you return to the role center, the updated report will appear. If you used **Save As**, you'll have to choose **Select Report**, and then enable the new report to see it.

> [!NOTE]
> This capability is not available with [!INCLUDE [prod_short](includes/prod_short.md)] on-premises.

### <a name="upload"></a>Upload reports

Power BI Reports can be distributed among users as .pbix files. If you have any .pbix files, you can upload and share them with all users of [!INCLUDE [prod_short](includes/prod_short.md)]. The reports are shared within each company in [!INCLUDE [prod_short](includes/prod_short.md)].  

To upload a report, select the **Upload Report** action from the drop-down command list on the **Power BI Reports** part. Then, locate the .pbix file that defines the reports that you want to share. You can change the default name of the file.  

After the report uploads to your Power BI workspace, it automatically uploads to other users' Power BI workspaces.

> [!NOTE]
> Uploading a report requires that you have SUPER user permissions in [!INCLUDE[prod_short](includes/prod_short.md)]. Also, you can't upload reports with [!INCLUDE [prod_short](includes/prod_short.md)] on-premises. With on-premises, you upload reports directly to your Power BI workspace. For more information, see [Work with [!INCLUDE [prod_short](includes/prod_short.md)] Data In Power BI](across-working-with-business-central-in-powerbi.md).

## Fixing problems

However, if something goes wrong, this section provides a workaround for the most typical issues.  

### You don't have a Power BI account

A Power BI account hasn't been set up. To get a valid Power BI account, you must have a license, and you must have previously signed into Power BI to create a Power BI workspace.

### Message: There are no enabled reports. Choose Select Report to see a list of reports that you can display.

This message appears if the default report failed to deploy to your Power BI workspace. Or it deployed but didn't refresh successfully. Navigate to the report in your Power BI workspace, select **Dataset**, **Settings**, and then manually update the credentials. Once the dataset successfully refreshes, navigate back to [!INCLUDE[prod_short](includes/prod_short.md)], and manually select the report from the **Select Reports** page.

#### You can't see a report on the Select Report page on a list page

It's probably because the report's name doesn't contain the name of the list page. Clear the filter to get a full list of Power BI reports available.

## See Also

[Business Central and Power BI](admin-powerbi.md)  
[Building Power BI Reports to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md)  
[Power BI Integration Component and Architecture Overview for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Work with [!INCLUDE [prod_short](includes/prod_short.md)] Data in Power BI](across-working-with-business-central-in-powerbi.md)  
[Power BI for consumers](/power-bi/consumer/end-user-consumer)  
[The 'new look' of the Power BI service](/power-bi/service-new-look)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Power BI documentation](/power-bi/)  
[Business Intelligence](bi.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power Apps Data Source](across-how-use-financials-data-source-powerapps.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate](across-how-use-financials-data-source-flow.md)  




[!INCLUDE[footer-include](includes/footer-banner.md)]
