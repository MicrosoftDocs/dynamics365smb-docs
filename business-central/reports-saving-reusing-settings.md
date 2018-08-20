---
title: Apply and Modify Saved Settings on Reports | Microsoft Docs
description: Describes using predefined options and filters to customize a report, and to generate the correct data.
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customization, personalization
ms.date: 09/08/2017
ms.author: jswymer

---
# Managing Saved Settings on Reports
When running a reports, users are typically presented with a page that lets them set certain options and filters for changing the data that is included in the generated report. This page is called the report request page. A report can include one or more *saved settings* that users can apply to the report from the request page. *Saved settings* are basically predefined options and filters. Using saved settings is a fast and reliable way to consistently generate reports that contain the correct data. For more information about how saved settings are used, see [Using Saved Settings](ui-work-report.md#SavedSettings).

If you have the proper permissions, you can view, create, and modify the saved settings for all reports for all users in company. You can assign saved settings for a report to individual users or all users in the company.

<!-- 
## Apply saved settings to a report
1. Open the report.

   The report request page appears.    
2. In the **Saved Settings** section of the page, set the **Name** field  to the saved settings that you want to use.

   The **Saved Settings** section only appears if the report has been run before or if there are existing saved settings entries. The saved settings entry called **Last used options and filters** is always available. These settings are the option and filter values that were used the last time you ran the report.

-->

## Create and modify saved settings for all users
You manage saved settings from page **1560 Reports Settings**. There are two ways to open this page:
-   Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Settings**, and then choose the related link.
-   Open a report, choose the lookup next to the **Used default values from:** box, choose **Select from full list**.

The page displays all the existing save settings entries for all users. If there is a user name in the **Assigned to** column, only that user can use the saved settings for the associated report. If there is a check mark in the **Share with all users** column, all users can use the saved settings for the report.

From the **Report Settings** page, you can:
-   Choose **New** to create a new saved settings entry from scratch.
-   Select a saved settings entry from the list, and choose **Copy** to create a copy.
-   Select a saved settings entry from the list, and choose **Edit** to modify a saved settings entry.


> [!Important]
> Consider the name that you give a saved settings entry. If you create a saved settings entry for all users, and you give it the same name as an existing saved settings entry that is assigned to a specific user only, then that user will not be able to use the saved settings entry that is assigned to everyone.  Under **Saved Settings** on the report request page, the user will see two saved settings entries with the same name. However, no matter which option he chooses, the user-specific saved settings entry will be used.

> [!NOTE]
> The saved settings feature is available only on reports where the [SaveValues property](https://docs.microsoft.com/en-us/dynamics-nav/savevalues-property) of the report's request page is set to `Yes`. The **SaveValues** property is set in the development environment.  

## See Also
[Working with Reports](ui-work-report.md)  
