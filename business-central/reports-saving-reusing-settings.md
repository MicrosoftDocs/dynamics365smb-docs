---
title: Manage Saved Settings for Reports and Batch Jobs
description: Set up saved options and filters for Business Central reports and batch jobs, and share the settings with individual users or everyone in a company.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: customization, personalization
ms.date: 11/11/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Manage saved settings for reports and batch jobs

When running reports, users are typically presented with a page that lets them select options and set filters to change the data that is included in the generated report. This page is called the *request page*. A report can include one or more *saved settings* that users can apply to the report from the request page. Saved settings are basically predefined options and filters. Using saved settings is a fast and reliable way to consistently generate reports that contain the correct data. Learn more in [Use saved settings](ui-work-report.md#SavedSettings).

> [!NOTE]
> This topic refers to *reports*, but similar information applies to *batch jobs*.

If you have the proper permissions, you can view, create, and modify the saved settings for all reports for all users in a company. You can assign saved settings for a report to individual users or to all users in the company.

## Manage saved report settings

You manage saved settings on the **Report Settings** page. There are two ways to open this page:

- [!INCLUDE[open-search](includes/open-search.md)], enter **Report Settings**, and then choose the related link.
- In a report's request page, choose the lookup in the **Use default values from** field, and then choose the **Select from full list** action.

    This field is only visible if you have run the report at least once earlier. The list will only show settings that are available to you, either because they are your own settings, or because the settings are shared with you.

The **Report Settings** page displays all the existing saved settings entries for all users. If there is a user name in the **Assigned to** field, only that user can use the saved settings for the associated report. If there is a check mark in the **Shared with all users** field, all users in the specified company can use the saved settings for the report.

> [!TIP]
> When a user runs a report that saves settings, their last-used options and filters are saved and added to this list.
>
> You can't edit or share the **Last used options and filters** entry directly. Choose **Copy** to create a named entry that you can edit and share.

## Create or modify saved settings for all users

From the **Report Settings** page, you can:

- Choose the **New** action to create a new saved settings entry from scratch.
- Select a saved settings entry from the list, and choose the **Copy** action to create a copy.
- Select a saved settings entry from the list, and choose the **Edit** action to modify a saved settings entry.

> [!Important]
> Consider the name that you give a saved settings entry. If you create a saved settings entry for all users, and you give it the same name as an existing saved settings entry that is assigned to a specific user only, then that user will not be able to use the saved settings entry that is assigned to everyone.  In the **Saved Settings** section on the request page, the user will see two saved settings entries with the same name. However, no matter which option they choose, the user-specific saved settings entry will be used.

> [!NOTE]
> The ability to save settings is available only on reports where the [SaveValues property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-savevalues-property) of the report's request page is set to `true`. The `SaveValues` property is set by the developer.

## Related information

[Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
