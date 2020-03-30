---
title: Define Granular Permissions  | Microsoft Docs
description: Describes how to give users access to objects by assigning permission sets to them.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.date: 04/01/2020
ms.author: sgroespe

---
# Assign Permissions to Users and Groups
The [!INCLUDE[d365fin](includes/d365fin_md.md)] security system allows you to control which objects a user can access within each database or environment. You can specify for each user whether they are able to read, modify, or enter data in the selected database objects. For detailed information, see [Data Security](/dynamics365/business-central/dev-itpro/security/data-security?tabs=object-level) in the Developer and ITPro help for [!INCLUDE[d365fin](includes/d365fin_md.md)].

Before you assign permissions to users and user groups, you must define who can sign in to by creating users according to the license as defined in the Microsoft 365 Admin Center. For more information, see [Create Users According to Licenses](ui-how-users-permissions.md).

In [!INCLUDE[d365fin](includes/d365fin_md.md)], there are two levels of permissions to database objects:
- Overall permissions according to the license, also referred to as the entitlement.
- More detailed permissions as assigned from within [!INCLUDE[d365fin](includes/d365fin_md.md)].

To make it easier to manage permissions for multiple users, you can organize them in user groups and thereby assign or change one permission set for many users in one action. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md#to-manage-permissions-through-user-groups).

> [!NOTE]
> An additional method of defining which features a user has access to is by setting the **Experience** field on the **Company Information** page. For more information, see [Change Which Features are Displayed](ui-experiences.md).
>
> You can also define what users see in the user interface and how they interact with their permitted functionality through pages. You do this through profiles that you assign to different types of users according to their job role or department. For more information, see [Manage Profiles](admin-users-profiles-roles.md) and [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md).

## To assign permission sets to users
A permission set is a collection of permissions for specific database objects. All users must be assigned one or more permission sets before they can access [!INCLUDE[d365fin](includes/d365fin_md.md)].

A [!INCLUDE[d365fin](includes/d365fin_md.md)] solution contains a number of predefined permission sets that are added by Microsoft or by your solution provider. You can also add new permission sets tailored to meet the needs of your organization. For more information, see [To create or edit a permission set](ui-define-granular-permissions.md#to-create-or-modify-a-permission-set).

> [!NOTE]
> If you do not want to restrict a user's access more than already defined by the license, you can assign a special permission set called SUPER to the user. This permission set ensures that the user can access all objects specified in the license.<br /><br />
> A user with the Essential license and the SUPER permission set has access to more functionality than users with the Team Member license and the SUPER permission set.

You can assign permissions sets to users in two ways:
- From the **User Card** page by selecting permission sets to assign to the user.
- From the **Permission Set by User** page by selecting users that a permission set is assigned to.

### To assign a permission set on a user card
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** page.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. For more information, see [To create or edit a permission set](ui-define-granular-permissions.md#to-create-or-modify-a-permission-set).

### To assign a permission set on the **Permission Set by User** page  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User** action.
3. On the **Permission Set by User** page, select the **[user name]** check box on a line for the relevant permission set to assign the set to the user.
4. Select the **All Users** check box to assign the permission set to all users.

## To get an overview of a user's permissions
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Open the card of the relevant user.
3. Choose the **Effective Permissions** action.

    The **Permissions** part lists all the database objects that the user has access to. You cannot edit this section.

    The **By Permission Set** part shows the assigned permission sets through which the permissions are granted to the user, the source and type of the permission set, and to which extend the different access types are permitted.

    For each row that you select in the **Permissions** section, the **By Permission Set** section shows which permission set or sets that the permission is granted through. In this section, you can edit the value in each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, **Execute Permission**.

    > [!NOTE]  
    > Only permission sets of type **User-Defined** can be edited.<br /><br />
    > Rows of source Entitlement originate from the subscription license. The permission values of the entitlement overrule values in other permission sets if they have a higher ranking. A value in a non-entitlement permission set that has a higher ranking than the related value in the entitlement will be surrounded by brackets to indicate that it is not effective as it is overruled by the entitlement.<br /><br />
    > For an explanation of ranking, see [To create or edit permissions manually](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).  

4. To edit a permission set, in the **By Permission Set** part, on the line for a relevant permission set of type **User-Defined**, choose one of the five access type fields and select a different value.

5. To edit individual permissions within the permission set, choose the value in the **Permission Set** field to open the **Permissions** page. Follow the steps described in [To create or edit permissions](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).  

> [!NOTE]  
> When you edit a permission set, the changes will also apply to other users that have the permission set assigned.

## To create or modify a permission set
Permission sets function as containers of permissions, so that you can easily manage multiple permissions in one record.

> [!NOTE]  
> A [!INCLUDE[d365fin](includes/d365fin_md.md)] solution typically contains a number of predefined permission sets that are added by Microsoft or by your software provider. These permission sets are of type **System** or **Extension**. You cannot create or edit these types of permission sets or the permissions within them. However, you can copy them to define your own permission sets and permissions. <br /><br />
Permission sets that users create, from new or as copies, are of type **User-Defined** and can be edited.

### To create new permission set from scratch
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2. To create a new permission set, choose the **New** action.
3. On the new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
When you have created a permission set, you must add the actual permissions. For more information, see [To create or modify permissions manually](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).

### To copy a permission set
You can also use a copy function to quickly carry all the permissions of another permission set to a new permission set.

> [!NOTE]  
> If a System permission set that you have copied is changed, you will be notified (depending on your selection), so that you can consider if the changes are relevant to copy or write into your user-defined permission set.

1. On the **Permission Sets** page, select the line for a permission set that you want to copy, and then choose the **Copy Permission Set** action.
2. On the **Copy Permission Set** page, specify the name of the new permission set, and then choose the **OK** button.
3. Select the **Notify on Changed Permission Set** check box if you want to maintain a link between the original and the copied permission sets. The link is then used to notify you if the name or content of the original permission set changes in a future version that the solution is upgraded to later.

The new permission set, containing all the permissions of the copied permission set, is added as a new line on the **Permission Sets** page. Now you can modify permission in the new permission set. Note that the lines are sorted alphabetically within each type.

## To create or modify permissions manually
This procedure explains how to add or edit permissions manually. You can also have a permissions generated automatically from your actions in the UI. For more information, see [To create or modify permissions by recording your actions](ui-define-granular-permissions.md#to-create-or-modify-permissions-by-recording-your-actions).

> [!NOTE]
> When you edit a permission and thereby the related permission set, the changes will also apply to other users that have the permission set assigned.

1. On the **Permission Sets** page, select the line for a permission set, and then choose the **Permissions** action.
2. On the **Permissions** page, create a new line or edit the fields on an existing line.

In each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, and **Execute Permission**, you can select one of the following three permission options:

|Option|Description|Ranking|
|------|-----------|
|**Yes**|The user can perform the action on the object in question.|Highest|
|**Indirect**|The user can perform the action on the object in question but only through another related object that the user has full access to. For more information about indirect permissions, see [Permissions Property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-permissions-property) in Developer and IT-Pro Help|Second highest|
|**Blank**|The user cannot perform the action on the object in question.|Lowest|

### Example - Indirect Permission
You can assign an indirect permission to use an object only through another object.
For example, a user can have permission to run codeunit 80, Sales-Post. The Sales-Post codeunit performs many tasks, including modifying table 37, Sales Line. When the user posts a sales document, the Sales-Post codeunit, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks if the user has permission to modify theSales Line table. If not, the codeunit cannot complete its tasks, and the user receives an error message. If so, the codeunit runs successfully.

However, the user does not need to have full access to the Sales Line table to run the codeunit. If the user has indirect permission for the Sales Line table, then the Sales-Post codeunit runs successfully. When a user has indirect permission, that user can only modify the Sales Line table by running the Sales-Post codeunit or another object that has permission to modify the Sales Line table. The user can only modify the Sales Line table when doing so from supported application areas. The user cannot run the feature inadvertently or maliciously by other methods.

## To create or modify permissions by recording your actions
1.    Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2.    Alternatively, on the **Users** page, choose the **Permission Sets** action.
3.    On the **Permission Sets** page, choose the **New** Action.
4.    On a new line, fill in the fields as necessary.
5.    Choose the **Permissions** action.
6.    On the **Permissions** page, choose the **Record Permissions** action, and then choose the **Start** action.

    This starts a recording process that captures all your action in the user interface.
7.    Go to the various pages and activities in [!INCLUDE[d365fin](includes/d365fin_md.md)] that you want users with this permission set to access. You must carry out the tasks that you want to record permissions for.
8.    When you want to finish the recording, return to the **Permissions** page, and then choose the **Stop** action.
9.    Choose the **Yes** button to add the recorded permissions to the new permission set.
10.    For each object in the recorded list, specify if users are able to insert, modify, or delete records in the recorded tables.

## Security Filters - To limit a user's access to specific records in a table
For record-level security in [!INCLUDE[d365fin](includes/d365fin_md.md)], you use security filters to limit a user's access to data in a table. You create security filters on table data. A security filter describes a set of records in a table that a user has permission to access. You can specify, for example, that a user can only read the records that contain information about a particular customer. This means that the user cannot access the records that contain information about other customers. For more information, see [Using Security Filters](/dynamics365/business-central/dev-itpro/security/security-filters) in Developer and IT-Pro help.

## To manage permissions through user groups
You can set up user groups to help you manage permission sets for groups of users in your company.

You start by creating a user group. Then you assign permission sets to the group to define which object users of the group can access. When you add user to the group, the permission sets defined for the group will apply to the user.

Permission sets assigned to a user through a user group stay synchronized so that a change to the user group permissions are automatically propagated to the user. If you remove a user from a user group, the involved permissions are automatically revoked.

### To group users in user groups
The following procedure explains how to create user groups manually. To create user groups automatically, see [To copy a user group and all its permission sets](ui-define-granular-permissions.md#to-copy-a-user-group-and-all-its-permission-sets).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Alternatively, on the **Users** page, choose the **User Groups** action.
3. On the **User Group** page, choose the **User Group Members** action.
4. On the **User Group Members** page, choose the **Add Users** action.

### To copy a user group and all its permission sets
To quickly define a new user group, you can copy all permission sets from an existing user group to your new user group.

> [!NOTE]
> The user group members are not copied to the new user group. You must add them manually afterwards. For more information, see [To group users in user groups](ui-define-granular-permissions.md#to-group-users-in-user-groups).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to copy, and then choose the **Copy User Group** action.
3. In the **New User Group Code** field, enter a name for the group, and then choose the **OK** button.

The new user group is added to the **User Groups** page. Proceed to add users. For more information, see [To group users in user groups](ui-define-granular-permissions.md#to-group-users-in-user-groups).  

### To assign permission sets to user groups
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **User Permission Sets** action to open the **User Permission Sets** page.
4. On the **User Permission Sets** page, on a new line, fill in the fields as necessary.

### To assign a permission set on the **Permission Set by User Group** page  
The following procedure explains how to assign permission sets to a user group on the **Permission Set by User Group** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User Group** action.
3. On the **Permission Set by User Group** page, select the **[user group name]** check box on a line for the relevant permission set to assign the set to the user group.
4. Select the **All User Groups** check box to assign the permission set to all user groups.

## To set up user time constraints
Administrators can define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on. Administrators can also assign responsibility centers to users. For more information, see [Work with Responsibility Centers](inventory-responsibility-centers.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.
2. On the **User Setup** page opens, choose the **New** action.
3. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
4. Fill in the fields as necessary.

## See Also
[Create Users According to Licenses](ui-how-users-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help
