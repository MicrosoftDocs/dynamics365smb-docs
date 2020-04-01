---
title: Apply and Modify Saved Settings on Reports | Microsoft Docs
description: Describes using predefined options and filters to customize a report, and to generate the correct data.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customization, personalization
ms.date: 04/01/2020
ms.author: sgroespe

---
# Manage Saved Settings for Reports and Batch jobs
When running reports, users are typically presented with a page that lets them select options and set filters to change the data that is included in the generated report. This page is called the request page. A report can include one or more *saved settings* that users can apply to the report from the request page. *Saved settings* are basically predefined options and filters. Using saved settings is a fast and reliable way to consistently generate reports that contain the correct data. For more information, see [Using Saved Settings](ui-work-report.md#SavedSettings).

> [!NOTE]
> This topic refers mainly to "report", but similar information applies to batch jobs.

If you have the proper permissions, you can view, create, and modify the saved settings for all reports for all users in a company. You can assign saved settings for a report to individual users or to all users in the company.

<!--
## Apply saved settings to a report
1. Open the report.

   The request page appears.    
2. In the **Saved Settings** section of the page, set the **Name** field  to the saved settings that you want to use.

   The **Saved Settings** section only appears if the report has been run before or if there are existing saved settings entries. The saved settings entry called **Last used options and filters** is always available. These settings are the option and filter values that were used the last time you ran the report.

-->

## To create and modify saved settings for all users
You manage saved settings on the **Reports Settings** page. There are two ways to open this page:
-   Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Settings**, and then choose the related link.
-   Open a report, choose the lookup in the **Use default values from** field, and then choose the **Select from full list** action.

The page displays all the existing saved settings entries for all users. If there is a user name in the **Assigned to** field, only that user can use the saved settings for the associated report. If there is a check mark in the **Share with all users** field, all users can use the saved settings for the report.

From the **Report Settings** page, you can:
-   Choose the **New** action to create a new saved settings entry from scratch.
-   Select a saved settings entry from the list, and choose the **Copy** action to create a copy.
-   Select a saved settings entry from the list, and choose the **Edit** action to modify a saved settings entry.

> [!Important]
> Consider the name that you give a saved settings entry. If you create a saved settings entry for all users, and you give it the same name as an existing saved settings entry that is assigned to a specific user only, then that user will not be able to use the saved settings entry that is assigned to everyone.  In the **Saved Settings** section on the request page, the user will see two saved settings entries with the same name. However, no matter which option they choose, the user-specific saved settings entry will be used.

> [!NOTE]
> The Saved Settings feature is available only on reports where the [SaveValues property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-savevalues-property) of the report's request page is set to **Yes**. The **SaveValues** property is set in the development environment.  

## See Also
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
