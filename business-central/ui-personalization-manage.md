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
ms.date: 09/04/2019
ms.author: sgroespe

---
# Customize the Workspace for Profiles (Roles)

Users can personalize pages that make up their workspace to suit their own preferences. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

Administrators can customize the workspace for a profile (role) so that all users that are assigned the related role will see the customized pages. The administrator customizes the role's workspace by using the same functionality as users when they personalize.

Page customization starts from the **Profiles (Roles)** page, the administrators starting point for managing users' profiles on individual profile cards. In addition to customizing roles and administrating customized pages, you control various other settings for profiles on the Profile (Role) card for each profile. For more information, see [Managing Profiles (Roles)](admin-users-profiles-roles.md).

## To customize pages for a role
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles (Roles)**, and then choose the related link.
2. Select the line for the profile (role) that you want to customize pages for, and then choose the **Edit** action.

3. Choose the **Customize pages** action.

    [!INCLUDE[d365fin](includes/d365fin_md.md)] opens on a new browser tab for the selected profile (role) with the **Customizing** banner activated. The **Customizing** banner offers the same functionality as the **Personalizing** banner that is available to users.

4. Customize pages according to the needs of the role in question in exactly the same way as a user would do when personalizing. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

    > [!NOTE]
    > To navigate to other pages that you want to customize, use Ctrl + Click on the action in question. If you only click on the action, the customization options appear, **Move**, **Hide**, etc.

5. When you have finished changing the layout of one or more pages, choose the **Done** button on the **Customizing** banner.
6. Close the browser tab.

    The customization of pages is now recorded for the profile (role) that you selected in step 2. This can be seen on the **Profile (Role)** page from the fact that the **Clear customized pages** action is active.

7. To enable the customized pages for users when they are assigned the role, select the **Enabled** check box.
8. To cancel all customizations made for the role, choose the **Clear customized pages** action.  

## To view all customized pages
You can get an overview of which pages are customized for a profile, for example to plan which to customize further or delete.


## See Also
[Personalize Your Workspace](ui-personalization-user.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
