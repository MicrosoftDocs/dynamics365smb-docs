---
title: Assign or Edit User Permissions  | Microsoft Docs
description: Describes how add Office 365 users to Business Central, and then assign permissions, access rights, and security settings.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.date: 04/19/2018
ms.author: sgroespe

---
# Manage Users and Permissions
To add users in [!INCLUDE[d365fin](includes/d365fin_md.md)], your company's Office 365 administrator must first create the users in the Office 365 Admin Center. For more information, see [Add Users to Office 365 for business](https://support.office.com/en-us/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)

Once users are created in Office 365, they can be imported into the **Users** window by using the **Get Users from Office 365** action. Users are assigned permission sets depending on the plan assigned to the user in Office 365.

You can then proceed to assign permission sets to the users to define which database objects, and thereby which UI elements, they have access to, and in which companies. You can add users to user groups. This makes it easier to assign the same permission sets to multiple users.

A permission set is a collection of permissions for specific objects in the database. All users must be assigned one or more permission sets before they can access [!INCLUDE[d365fin](includes/d365fin_md.md)]. A number of predefined permission sets are provided by default. You can use these permission sets as already defined, modify the default permission sets, or create additional permission sets.

Administrators can use the **User Setup** window to define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on.

Another system that defines what users can access is the Experience setting. For more information, see [Changing Which Features are Displayed](ui-experiences.md).

## To assign permissions to a user
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** window.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To group users in user groups
You can set up users groups to help you manage permission sets for groups of users in your company.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Groups**, and then choose the related link.
2. Alternatively, in the **Users** window, choose the **User Groups** action.
3. In the **User Group** window, choose the **User Group Members** action.
6. In the **User Group Members** window, choose the **Add Users** action.
7. To add new or additional permission sets, in the **User Groups** window, choose the **User Group Permission Sets** action.
8. In the **User Group Permission Sets** window, on a new line, fill in the fields as necessary by selecting from existing permission sets.

## To copy a user group and all its permission sets
To quickly define a new user group, you can copy all permission sets from an existing user group to your new user group.

The user group members are not copied to the new user group. You must add them manually afterwards.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to copy, and then choose the **Copy User Group** action.
3. In the **New User Group Code** field, enter a name for the group, and then choose the **OK** button.

The new user group is added to the **User Groups** window. Proceed to add users. For more information, see the "To group users in user groups" section.

## To set up user time constraints
Administrators can define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on. Administrators can also assign responsibility centers to users. For more information, see [Work with Responsibility Centers](inventory-responsibility-centers.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Setup**, and then choose the related link.
2. In the **User Setup** window opens, choose the **New** action.
3. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
4. Fill in the fields as necessary.

## See Also
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
