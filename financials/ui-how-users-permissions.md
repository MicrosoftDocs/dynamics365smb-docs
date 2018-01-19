---
title: Assign User Permissions and Create or Modify Permission Sets | Microsoft Docs
description: Describes how add Office 365 users to Dynamics 365, Business edition, and then assign permissions, access rights, and security settings.
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.date: 10/16/2017
ms.author: sgroespe

---
# How to: Manage Users and Permissions
To add users in [!INCLUDE[d365fin](includes/d365fin_md.md)], your company's Office 365 administrator must first create the users in the Office 365 Admin Center. For more information, see [Add Users to Office 365 for business](https://support.office.com/en-us/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)

Once users are created in Office 365, they can be imported into the **Users** window by using the **Get Users from Office 365** action. Users are assigned permission sets depending on the plan assigned to the User in Office 365.

You can then proceed to assign permission sets to the users to define which database objects, and thereby which UI elements, they have access to, and in which companies.

A permission set is a collection of permissions for specific objects in the database. All users must be assigned one or more permission sets before they can access [!INCLUDE[d365fin](includes/d365fin_md.md)]. A number of predefined permission sets are provided by default. You can use these permission sets as already defined, modify the default permission sets, or create additional permission sets.

You can add users to user groups. This makes it easier to assign the same permission sets to multiple users.

Administrators can use the **User Setup** window to define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on.

## To assign permissions to a user
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** window.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To group users in user groups
You can set up users groups to help you manage permission sets for groups of users in your company. You can use a function to copy all permission sets from an existing user group to your new user group. User group members are not copied.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Groups**, and then choose the related link.
2. Alternatively, in the **Users** window, choose the **User Groups** action.
3. In the **User Groups** window, select an existing user group that you want to copy, and then choose the **Copy User Group** action.
4. In the **New User Group Code** field, specify the name of the new user group, and then choose the **OK** button.

    As an alternative to copying, you can choose the New action to create a new line for an empty user group, which you then fill in manually.
5. To add new or additional users, in the **User Group** window, choose the **User Group Members** action.
6. In the **User Group Members** window, on a new line, fill in the fields as necessary by selecting from existing users.
7. To add new or additional permission sets, in the **User Group** window, choose the **User Group Permission Sets** action.
8. In the **User Group Permission Sets** window, on a new line, fill in the fields as necessary by selecting from existing permission sets.

## To set up user time constraints
Administrators can define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on. Administrators can also assign responsibility centers to users. For more information, see [How to: Work with Responsibility Centers](inventory-responsibility-centers.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Setup**, and then choose the related link.
2. In the **User Setup** window opens, choose the **New** action.
3. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
4. Fill in the fields as necessary.

## See Also
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Setup and Administration in [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](admin-setup-and-administration.md)  
[Welcome to [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Working with [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)  
