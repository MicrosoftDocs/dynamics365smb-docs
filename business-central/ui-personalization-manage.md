---
title: Customizing Pages for Roles | Microsoft Docs
description: Learn how to customize the user interface for a profile (role) so that all users assigned that role see a customized workspace.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.date: 04/01/2020
ms.author: sgroespe

---
# Customize Pages for Profiles
Users can personalize pages that make up their workspace to suit their own preferences. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

Administrators can customize pages for a profile, according to the related business role or department, for example, so that all users that are assigned the profile will see the customized page layout. The administrator customizes pages by using the same functionality as users do when they personalize pages.

> [!NOTE]
> The typical business use of a profile is a role. A profile is therefore named *Profile (Role)* in the UI.

Page customization starts from the **Profiles (Roles)** page, the administrator's starting point for managing users' profiles on individual profile cards. In addition to customizing the page layout, you control various other settings for profiles on the **Profile (Role)** page for each profile. For more information, see [Manage Profiles](admin-users-profiles-roles.md).

## To customize pages for a profile
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles (Roles)**, and then choose the related link.
2. Select the line for the profile that you want to customize pages for, and then choose the **Edit** action.
3. Choose the **Customize pages** action.

    [!INCLUDE[d365fin](includes/d365fin_md.md)] opens on a new browser tab for the selected profile with the **Customizing** banner activated. The **Customizing** banner offers the same functionality as the **Personalizing** banner that is available to users.

4. Customize pages according to the needs of the role or department in question in the same way as a user would do when personalizing. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

    > [!NOTE]
    > To navigate during personalization, use Ctrl + Click on an action if it is highlighted by the arrowhead.

5. When you have finished changing the layout on one or more pages, choose the **Done** button on the **Customizing** banner.
6. Close the browser tab.

The customization of pages is now recorded for the profile.

## To view all customized pages for a profile
You can get an overview of which pages are customized for a profile, for example to plan which to customize further or delete.

- On the **Profile (Role)** page, choose the **Customized Pages** action.

## To delete all customizations for a profile
You can cancel all customizations that you have made for a profile. Customizations introduced with an extension and personalizations made by a user will not be deleted. You can delete all personalizations with another action. For more information, see [To delete all personalizations made by a user](admin-users-profiles-roles.md#to-delete-all-personalizations-made-by-a-user).

- On the **Profile (Role)** page for a customized profile, choose the **Clear customized pages** action.

The layout on pages for the profile is reset to the default layout.  

## To delete customization for specific pages for a profile
You can delete individual page customizations that you have made for a profile. Customizations introduced with an extension and personalizations made by a user will not be deleted. You can delete specific page personalizations with another action. For more information, see [To delete personalizations for specific pages](admin-users-profiles-roles.md#to-delete-personalizations-for-specific-pages).

1. On the **Profile (Role)** page, choose the **Customized Pages** action.
2. On the **Profile Customizations** page, select on or more lines for page customizations that you want to delete, and then choose the **Delete** action.

The layout on the selected pages is adjusted to the changes you made.

## See Also
[Personalize Your Workspace](ui-personalization-user.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
