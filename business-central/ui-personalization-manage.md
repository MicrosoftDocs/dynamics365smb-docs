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
# Customize the Workspace for Profiles (Roles)

Users can personalize pages that make up their workspace to suit their own preferences. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

Administrators can customize the workspace for a role so that all users that are assigned the related profile will see the customized pages. The administrator customizes the role's workspace using the same functionality as the user, namely the **Personalizing** banner.

In addition to customizing roles and controlling if users can personalize the role further, administrators can clear any page personalization that users have made. For more information, see [To clear personalizations](ui-personalization-manage.md#to-clear-users'-personalization).

## To customize pages for a role
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles (Roles)**, and then choose the related link.
2. Select the line for the profile (role) that you want to customize pages for, and then choose the **Edit** action.

    On the **Profile (Role)** page, you can make various settings for the profile, such as the name of the role as users see it, which Role Center it uses, and whether users assigned the role can personalize their pages. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

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

## To see all customized pages
As an administrator, you can quickly 

## To clear personalizations
Clearing page personalization changes the page back to its original layout before any personalization was made. There are two ways to clear the personalizations that users have made to pages: using the **Delete User Personalization** page and using the **User Personalization Card** page.

### To clear user personalizations by using the Delete User Personalization page
The **Delete User Personalization** page enables you to clear personalizations on a per-page basis for each user individually.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete User Personalization**, and then choose the related link.

    The page lists all the pages that have been personalized and the user that they belong to.

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
[Personalize Your Workspace](ui-personalization-user.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
