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
ms.date: 08/22/2019
ms.author: sgroespe

---
# Customizing the Workspace for Profiles (Roles)

Users can personalize their workspace to suit their own preferences. For more information, see [Personalizing Your Workspace](ui-personalization-user.md).

Administrators can customize the workspace for a role so that all users that are assigned the related profile will see the customized workspace. The administrator customizes the role's workspace using the same functionality as the user, namely the **Personalizing** banner.



As an administrator, you control and manage personalization by:

-   Enabling or disabling the personalization feature for the entire application (on-premises installation only).
-   Enabling or disabling the personalization feature for users of a specific profile.
-   Clearing any page personalizations that users have made.

## To customize pages for a role

## To disable personalization for a profile
You can prevent all users that belong to a specific profile from being able to personalize their pages.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles**, and then choose the related link.
2. Select the profile in the list that you want to modify.
3. Select the **Disable personalization** check box, and then choose the **OK** button.

> [!NOTE]  
> In Business Central online, you can only disable personalization for a tenant profile, not for system profiles.

## To clear user personalizations
Clearing page personalization changes the page back to its original layout before any personalization was made. There are two ways to clear the personalizations that users have made to pages: using the **Delete User Personalization** page and using the **User Personalization Card** page.

### To clear user personalizations by using the Delete User Personalization page
The **Delete User Personalization** page enables you to clear personalizations on a per-page basis for each user individually.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete User Personalization**, and then choose the related link.

    The page lists all the pages that have been personalized and the user it belongs to.

    >[!NOTE]
    > A check mark in the **Legacy Personalization** columns indicates that the personalization was done in an older version of [!INCLUDE[d365fin](includes/d365fin_md.md)], which handled personalization different than it does now. Users who try to personalize these pages are locked from doing so unless they choose to unlock the page. For more information, see [Why a page is locked from personalizing](ui-personalization-locked.md).

2. Select the entry that you want to delete, and then choose the **Delete** action.

    The user will see the changes the next time they sign-in.

### To clear user personalizations by using the User Personalization Card page
The **User Personalization Card** page enables you to clear the personalization on all pages for specific user. This requires write permission to Table 2000000072 **Profile**.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Personalization**, and then choose the related link.

    The **User Personalization** page lists all users who potentially have personalized pages. If you cannot find a user in the list, this means that they do not have any personalized pages.

2. Select the user from the list, and then choose the **Edit** action.

3. On the **Actions** tab, choose **Clear Personalized Pages**.

    The user will see the changes the next time they sign-in.

## See Also
[Personalizing Your Workspace](ui-personalization-user.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Changing Which Features are Displayed](ui-experiences.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
