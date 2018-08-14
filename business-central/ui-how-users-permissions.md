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
ms.date: 08/14/2018
ms.author: sgroespe

---
# Managing Users and Permissions
To add users in [!INCLUDE[d365fin](includes/d365fin_md.md)], your company's Office 365 administrator must first create the users in the Office 365 Admin Center. For more information, see [Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users).

Once users are created in Office 365, they can be imported into the **Users** window in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Users are assigned permission sets depending on the plan assigned to the user in Office 365. For detailed information about licensing, see [Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing).

You can then proceed to assign permission sets to the users to define which database objects, and thereby which UI elements, they have access to, and in which companies. You can add users to user groups. This makes it easier to assign the same permission sets to multiple users.

A permission set is a collection of permissions for specific objects in the database. All users must be assigned one or more permission sets before they can access [!INCLUDE[d365fin](includes/d365fin_md.md)].

From the **User Card** window, you can open the **Effective Permissions** window to see which permissions the user has and through which permission sets they are granted. Here you can also change permission details for permission sets of type **User-Defined**. For more information, see the "To view or edit a user's permissions" section.

Administrators can use the **User Setup** window to define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on.

Another system that defines what users can access is the Experience setting. For more information, see [Changing Which Features are Displayed](ui-experiences.md).

## To add a user in Business Central
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
2. Choose the **Get Users from Office 365** action.

Any new user that has been created for your Office 365 subscription will be added in the **Users** window.

## To group users in a user group
You can set up users groups to help you manage permission sets for groups of users in your company.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Groups**, and then choose the related link.
2. Alternatively, in the **Users** window, choose the **User Groups** action.
3. In the **User Group** window, choose the **User Group Members** action.
4. In the **User Group Members** window, choose the **Add Users** action.

When users or user groups are created, you must assign permission sets to each to define which object a user can access. First, you must organize the relevant permissions in permission sets. For more information, see the "To create or edit a permission set" section.

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

## To create or edit a permission set
Permission sets function as containers of permissions, so that you can easily manage multiple permissions in one record. When you have created a permission set, you must add the actual permissions. For more information, see the "To create or edit permissions" section.

> [!NOTE]  
> A [!INCLUDE[d365fin](includes/d365fin_md.md)] solution typically contains a number of predefined permission sets that are added by Microsoft or by your software provider. These permission sets are of type **System** or **Extension**. You cannot create or edit these types of permission sets or the permissions within them. However, you can copy them to define your own permission sets and permissions. <br /><br />
Permission sets that users create, from new or as copies, are of type **User-Defined** and can be edited.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Permission Sets**, and then choose the related link.
2. To create a new permission set, choose the **New** action.
3. On the new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### To copy a permission set
When you create new permission sets, you can use a copy function to quickly carry all the permissions of another permission set to a new permission set.

> [!NOTE]  
> If a System permission set that you have copied is changed, you will be notified (depending on your selection), so that you can consider if the changes are relevant to copy or write into your user-defined permission set.

1. In the **Permission Sets** window, select the line for a permission set that you want to copy, and then choose the **Copy Permission Set** action.
2. In the **Copy Permission Set** window, specify the name of the new permission set, and then choose the **OK** button.

The new permission set, containing all the permissions of the copied permission set, is added as a new line in the **Permission Sets** window. Note that the lines are sorted alphabetically within each type.

## To create or edit permissions
1. In the **Permission Sets** window, select the line for a permission set, and then choose the **Permissions** action.
2. In the **Permissions** window, create a new line or edit the fields on an existing line.

In each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, and **Execute Permission**, you can select one of the following three permission options:

|Option|Description|Ranking|
|------|-----------|
|**Yes**|The user can perform the action on the object in question.|Highest|
|**Indirect**|The user can perform the action on the object in question but only through another related object that the user has full access to.|Second highest|
|Blank|The user cannot perform the action on the object in question.|Lowest|

> [!NOTE]  
> When you edit a permission and thereby the related permission set, the changes will also apply to other users that have the permission set assigned.

## To assign permission sets to users or user groups
You can assign permissions to users in two ways:
- Define permission sets on a user's user card.
- Select the check box for a user, on a column, for a related permission set, on a row, in the **Permission Set by User** matrix window.
    With this method, you can also assign permissions sets to user groups.

### To assign a permission set on a user card
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** window.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. For more information, see the "To create or edit a permission set" section.

### To assign a permission set in the **Permission Set by User** window  
The following procedure explains how to assign permission sets to a user in the **Permission Set by User** window. The steps are similar in the **Permission Set by User Group** window.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
2. In the **Users** window, select the relevant user, and then choose the **Permission Set by User** action.
3. In the **Permission Set by User** window, select the **[user name]** check box on a line for the relevant permission set to assign the set to the user.
4. Select the **All Users** check box to assign the permission set to all users.

## To view or edit a user's permissions
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
2. Open the card of the relevant user.
3. Choose the **Effective Permissions** action.

    The **Permissions** part lists all the database objects that the user has access. You cannot edit this section.

    The **By Permission Set** part shows the assigned permission sets through which the permissions are granted to the user, the source and type of the permission set, and to which extend the different access types are permitted.

    For each row that you select in the **Permissions** section, the **By Permission Set** section shows which permission set or sets that the permission is granted through. In this section, you can edit the value in each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, **Execute Permission**.   

    > [!NOTE]  
    > Only permission sets of type **User-Defined** can be edited.<br /><br />
    > Rows of source Entitlement originate from the subscription plan. The permission values of the entitlement overrule values in other permission sets if they have a higher ranking. A value in a non-entitlement permission set that has a higher ranking than the related value in the entitlement will be surrounded by brackets to indicate that it is not effective as it is overruled by the entitlement. For en explanation of ranking, see the "To create or edit permissions" section.  

4. To edit a permission set, in the **By Permission Set** section, on the line for a relevant permission set of type **User-Defined**, choose one of the five access type fields and select a different value.

5. To edit individual permissions within the permission set, choose the value in the **Permission Set** field to open the **Permissions** window. For more information, see the "To create or edit permissions" section.  

> [!NOTE]  
> When you edit a permission set, the changes will also apply to other users that have the permission set assigned.

## See Also
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
