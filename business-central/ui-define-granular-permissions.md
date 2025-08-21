---
title: Define granular permissions
description: This article describes how to define granular permissions and assign each user the permission sets that they need to do their jobs.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: access, right, security
ms.search.form: 1, 119, 8930, 9800, 9802, 9807, 9808, 9816_Primary, 9830, 9831, 9855_Primary, 9862_Primary, 9874_Primary, 9878_Primary, 9865_Primary
ms.date: 05/28/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Assign permissions to users and groups

In combination with the user's license, the [!INCLUDE[prod_short](includes/prod_short.md)] security system controls user access to objects in each database or environment. For each user, you can specify whether they're able to read, modify, or enter data in database objects. To learn more, go to [Data Security](/dynamics365/business-central/dev-itpro/security/data-security?tabs=object-level) in the developer and administration content for [!INCLUDE[prod_short](includes/prod_short.md)].

Before you assign permissions to users and groups, you must define who can sign in by creating users according to their license. To learn more, go to [Create Users According to Licenses](ui-how-users-permissions.md).

In [!INCLUDE[prod_short](includes/prod_short.md)], there are two levels of permissions to database objects:

- Overall permissions according to the license, also referred to as the entitlement.

  The licenses include default permission sets. Admins can customize these default permissions for the relevant license types. To learn more, go to [Configure permissions based on licenses](ui-how-users-permissions.md#licensespermissions).  

- Detailed permissions that you assign in [!INCLUDE[prod_short](includes/prod_short.md)].

This article describes how to define, use, and apply permissions in [!INCLUDE [prod_short](includes/prod_short.md)] to change the default configuration.  

[!INCLUDE [prod_short](includes/prod_short.md)] online includes default user groups that are assigned to users automatically based on their license. You can change the default configuration by modifying or adding security groups, permission sets, and permissions. The following table outlines key scenarios for modifying the default permissions.  

|To...  |Go to...  |
|---------|---------|
|Make it easier to manage permissions for multiple users, you can organize them in security groups and then assign or change one permission set for many users in one action.| [Control access to Business Central using security groups](ui-security-groups.md) or [Manage permissions through user groups (legacy)](ui-legacy-user-groups.md) |
|Manage permission sets for specific users | [Assign permission sets to users](#assign-permission-sets-to-users) |
|Learn how to define a permission set|[Create a permission set](#create-a-permission-set)|
|View or troubleshoot a user's permissions|[Get an overview of a user's permissions](#get-an-overview-of-a-users-permissions)|
|Learn about record-level security|[Security filters limit a user's access to specific records in a table](#security-filters-limit-a-users-access-to-specific-records-in-a-table)|

> [!NOTE]
> A broader way to define which features users have access to is by setting the **Experience** field on the **Company Information** page. To learn more, go to [Change Which Features are Displayed](ui-experiences.md).
>
> You can also define the features that are available to users in the user interface and how they interact with them through pages. You define features through profiles that you assign to different types of users according to their job role or department. To learn more, go to [Manage Profiles](admin-users-profiles-roles.md) and [Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md).

## Create a permission set

> [!NOTE]
> Rather than adding permissions individually, you can add entire permission sets. If needed, you can then exclude individual permissions in them. To learn more, go to [To add other permission sets](#to-add-other-permission-sets). To make that possible, we replaced the Permission Set page with a new one. The key differences are the new **Permission Sets** and **Results** panes, and the **Included permissions** FactBox. To continue using the replaced Permissions page, on the **Permission Sets** page, choose the **Permissions (legacy)** action.

When you add a system permission, your user-defined permission set is automatically updated with any changes that Microsoft makes to those permissions.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Permission Sets**, and then choose the related link.
1. Choose the **New** action.
1. On the new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Choose the **Permissions** action.
1. On the **Permission Set** page, in the **Type** field, include or exclude permissions to the object as follows:

   To include the permission, choose **Include**, and then choose level of access to give in the **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, and **Execute Permission** fields. The following table describes the options.

   |Option|Description|Ranking|
   |------|-----------|-------|
   |**Blank**|The user can't perform the action on the object.|Lowest|  
   |**Yes**|The user can perform the action on the object.|Highest|
   |**Indirect**|The user can perform the action on the object, but only through another related object that the user has full access to. For more information, see [Example - Indirect Permission](#example---indirect-permission) in this article, and [Permissions Property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-permissions-property#example---indirect-permission) in Developer and IT-Pro Help.|Second highest|
  
   To exclude the permission, or one or more access levels, choose **Exclude**, and then choose the level of access to give. The following table describes the options.

   |Option|Description|
   |------|-----------|
   |**Blank**|Use the access level based on the hierarchy of permissions in the set.  |
   |**Exclude**|Remove the specific access level for the object.|
   |**Reduce to indirect**|Change the access level to Indirect if any permission sets give Direct access to the object. For example, choose this option if the permission set gives Direct access to G/L entries but you don't want users to have full access to the entries.|
  
   > [!NOTE]
   > If a permission is in both an included and excluded permission set, the permission is excluded.

1. Use the **Object Type** and **Object ID** fields to specify the object you're giving access to.

   > [!TIP]
   > New lines show default values. For example, the **Object Type** field contains **Table Data**, and the **Object ID** field contains **0**. The default values are just placeholders, and aren't used. You must choose a type of object and an object in the **Object ID** field before you can create another new line.

1. Optional: If you're defining permissions for a Table Data object type, in the **Security Filter** field you can filter the data that a user can access in fields on the selected table. For example, you might want to let a user access only records that contain information about a particular customer. To learn more, go to [Security filters limit a user's access to specific records in a table](#security-filters-limit-a-users-access-to-specific-records-in-a-table) and [Using Security Filters](/dynamics365/business-central/dev-itpro/security/security-filters).
1. Optional: On the **Permission Sets** pane, add one or more other permission sets. To learn more, go to [To add other permission sets](#to-add-other-permission-sets).

> [!IMPORTANT]
> Use caution when assigning **Insert Permission** or **Modify Permission** to the **9001 User Group Member** or **9003 User Group Permission Set** table. Any users assigned to the permission set could potentially assign themselves to other user groups, which in turn might give them unintended permissions.

### Example - Indirect Permission

You can assign Indirect permission to allow a user to use an object, but only through another object. For example, a user has permission to run codeunit 80, Sales-Post. The Sales-Post codeunit performs many tasks, including modifying table 37, Sales Line. When the user posts a sales document using the Sales-Post codeunit, [!INCLUDE[prod_short](includes/prod_short.md)] checks whether the user has permission to modify the Sales Line table. If not, the codeunit can't complete its tasks, and the user receives an error message. If so, the codeunit runs successfully.

However, the user doesn't need to have full access to the Sales Line table to run the codeunit. If the user has Indirect permission for the Sales Line table, the Sales-Post codeunit runs successfully. When a user has Indirect permission, they can only modify the Sales Line table by running the Sales-Post codeunit or another object that has permission to modify the Sales Line table. The user can only modify the Sales Line table when doing so from supported application areas. The user can't run the feature inadvertently or maliciously by other methods.

### To add other permission sets

Expand a permission set by adding other permission sets to it. Afterward, you can include or exclude specific permissions, or entire permission sets, in each set you add. This setting includes permissions in the Extension and System type permission sets, which otherwise isn't allowed. Exclusions apply only to the permission set you're expanding. The original set isn't affected.

On the **Permission Set** page, add a permission set on the **Permission Sets** pane. The **Result** pane lists all added permission sets. To explore the permissions that are included in a set you added, choose the set on the Result pane so the **Included permissions** FactBox shows the permissions.

On the **Result** pane, use the **Inclusion Status** field to identify the permission sets in which you excluded permissions or permission sets. If something's excluded, the status is **Partial**.

For an overall view of permissions in the permission set, choose the **View all permissions** action. The **Expanded Permissions** page shows all permissions that were already assigned to the permission set and the permissions in the added permission sets.

To fully exclude all permissions from a permission set, on the **Result** pane, select the line, choose **Show more options**, and then choose **Exclude**. When you exclude a permission set, a line is created on the **Permission Sets** pane of the type Excluded. If you excluded a permission set, but want to include it again, delete the line on the **Permission Sets** pane.

To fully or partially exclude a specific permission in a set you added, under **Permissions**, create a line for the object. The access level fields, such as **Insert Permission**, **Modify Permission**, and so on, all contain **Exclude**. To allow a certain access level, choose the appropriate option.

Excluding a permission set excludes all of the permissions in the set. [!INCLUDE [prod_short](includes/prod_short.md)] calculates permissions as follows:

1. Calculate the full list of included permissions
1. Calculate the full list of excluded permissions
1. Remove excluded permissions from the list of included permissions (removing an indirect permission is the same as Reduce to Indirect)

## Copy a permission set

Create a new permission set by copying another. The new set includes all of the permissions and permission sets from the set you copied. How the permissions and permission sets are arranged in the new permission set differs, depending on your choice in the **Copy operation** field. The following table describes the options.

|Option  |Description  |
|---------|---------|
|**Copy by reference**     | The original permission set and all of the permission sets that were added to it are listed on the **Results** pane.       |
|**Flat permission copy**  | All permissions from all permission sets are included in a flat list on the **Permissions pane**. Permissions aren't organized by permission set.        |
|**Clone**     | Create an exact copy of the original permission set.        |

1. On the **Permission Sets** page, select the line for a permission set that you want to copy, and then choose the **Copy Permission Set** action.
1. On the **Copy Permission Set** page, specify the name of the new permission set.
1. In the **Copy operation** field, specify how to arrange permission in the new permission set.
1. Optional: If you're adding a System permission set, you might want to be notified if the name or content of the original permission set changes in a future version. This lets you consider whether to update your user-defined permission set. To receive a notification, turn on the **Notify on Changed Permission Set** toggle.

> [!NOTE]
> The notification requires that the **Original System permission set changed** notification is enabled on the **My Notifications** page.

## Create or modify permissions by recording your actions

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Permission Sets**, and then choose the related link.

   Alternatively, on the **Users** page, choose the **Permission Sets** action.
1. On the **Permission Sets** page, choose the **New** Action.
1. On a new line, fill in the fields as necessary.
1. Choose the **Permissions** action.
1. On the **Permissions** page, choose the **Record Permissions** action, and then choose the **Start** action.

   Recording must be done either by using the **Open this page in a new windows** (pop-out) feature to have the **Permissions** recording window side-by-side, or by working within the same tab.  
    A recording process now starts and captures all of your actions in the user interface.
1. Go to the various pages and activities in [!INCLUDE[prod_short](includes/prod_short.md)] that you want users with this permission set to access. You must carry out the tasks that you want to record permissions for.
1. When you want to finish the recording, return to the **Permissions** page, and then choose the **Stop** action.
1. Choose the **Yes** button to add the recorded permissions to the new permission set.
1. For each object in the recorded list, specify whether users are able to insert, modify, or delete records in the recorded tables.

### To export and import a permission set

To quickly set up permissions, you can import permission sets that you exported from another [!INCLUDE[prod_short](includes/prod_short.md)] tenant.

In multitenant environments, a permission set is imported into a specific tenant. In other words, the scope of the import is *Tenant*.

1. In tenant 1, on the **Permission Sets** page, select the line or lines for the permission sets to export, and then choose the **Export Permission Sets** action.

   An XML file is created in the download folder on your machine. By default, the name is *Export Permission Sets.xml*.

1. In tenant 2, on the **Permission Sets** page, select the **Import Permission Sets** action.
1. On the **Import Permission Sets** dialog page, consider if you want to merge existing permission sets with any new permission sets in the XML file.

   If you select the **Update existing permissions** checkbox, existing permission sets that match names in the XML file merge with the imported permission sets.

   If you don't select the **Update existing permissions** checkbox, permission sets that match names in the XML file are skipped during import. In that case, you're notified about the permission sets that are skipped.

1. From the **Import** dialog page, find and select the XML file to be imported, and then choose the **Open** action.

The permission sets are imported.

## Remove obsolete permissions from all permission sets

On the **Permission Sets** page, choose the **Remove Obsolete Permissions** action.

## Set up time constraints for users

Administrators can define periods of time during which specified users are able to post. Administrators can also specify if the system logs how much time users are signed in. Similarly, administrators can assign responsibility centers to users. To learn more, go to [Work with Responsibility Centers](inventory-responsibility-centers.md).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **User Setup**, and then choose the related link.
1. On the **User Setup** page opens, choose the **New** action.
1. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
1. Fill in the fields as necessary.

## Control access to specific companies

When you have multiple companies in Business Central, managing permissions across companies requires extra consideration. You might not want users to have identical access rights to all companies. Instead, you might need to grant users' permissions based on their company affiliations. When you assign permission sets to individual users or security groups, you can select a specific company to which the permission set applies. The company isn't explicitly specified within the permission set, but rather when the permission set is assigned to the user or security group.

If you don't specify the company when assigning a permission set, the permission set then applies to all companies. If you want a permission set to apply to more than one company, but not all companies, add the permission set specifically for each company separately.

To learn how, go to [Assign permission sets to users](#assign-permission-sets-to-users) or [Assign permissions to a security group](ui-security-groups.md#assign-permissions-to-a-security-group).

## Review the permissions in a security group

On the **Security Groups** page, the FactBox pane shows the **Permission Sets** that are assigned to the group. Each user listed in the **Members** card has those permissions. The **Permission Set by Security Group** action provides a more detailed view. There you can also explore the individual permissions in each security group.

Permissions are also available on the **Users** page. The FactBox pane shows the **Permission Sets from Security Group** and **Security Group Memberships** cards for the selected user.

## Assign permission sets to users

A permission set is a collection of permissions for specific database objects. All users must be assigned one or more permission sets before they can access [!INCLUDE[prod_short](includes/prod_short.md)].  

A [!INCLUDE[prod_short](includes/prod_short.md)] solution contains predefined permission sets that Microsoft or your solution provider add. You can also add new permission sets tailored to meet the needs of your organization. To learn more, go to [Create a permission set](#create-a-permission-set).

> [!NOTE]
> If you don't want to restrict a user's access more than already defined by the license, you can assign a special permission set called **SUPER** to the user. This permission set ensures that the user can access all objects specified in the license.
>
> A user with the Essential license and the SUPER permission set has access to more functionality than users with the Team Member license and the SUPER permission set.

You can assign permissions sets to users in two ways:

- From the **User Card** page, by selecting permission sets to assign to the user.
- From the **Permission Set by User** page, by selecting users that a permission set is assigned to.

### To assign a permission set on a user card

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Users**, and then choose the related link.
1. Select the user that you want to assign permission to.

   Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
1. Choose the **Edit** action to open the **User Card** page.
1. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. To learn more, go to [Create or edit a permission set](ui-define-granular-permissions.md#create-a-permission-set).

   If you want the permission set to apply to a specific company, select the company in the **Company** field. If you want the permission set to apply to all companies, leave the **Company** field blank. [Learn more](#control-access-to-specific-companies).

## To assign a permission set on the Permission Set by User page

This method makes it easier for you to assign different permission sets to multiple users. 

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Users**, and then choose the related link.
1. On the **Users** page, choose the **Permission Set by User** action.
1. If you want the permission sets to apply only to a specific company, set the **Company name** field to that company. If you want the permission set to apply to all companies, leave the **Company name** field blank. [Learn more](#control-access-to-specific-companies).
1. On the **Permission Set by User** page, select the **[user name]** checkbox on a line for the relevant permission set to assign the set to the user.

    Select the **All Users** checkbox to assign the permission set to all users.

## Get an overview of a user's permissions

You can view other users' effective permissions only if you're assigned to the SECURITY or SUPER permissions. 

The **Effective Permissions** page offers additional information about the source of each permission. For example, whether the source is a security group, or a permission is inherited. The page also contains a column where administrators can review the security filters that are applied. To learn more about security filters, go to [Security filters limit a user's access to specific records in a table](#security-filters-limit-a-users-access-to-specific-records-in-a-table).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Users**, and then choose the related link.
1. Open the card of the relevant user.
1. Choose the **Effective Permissions** action.

   The **Permissions** part lists all the database objects that the user has access to. You can't edit this section.

   The **By Permission Set** part shows the assigned permission sets through which the permissions are granted to the user, the source and type of the permission set, and to which extent the different access types are permitted.

   For each row that you select in the **Permissions** section, the **By Permission Set** section shows which permission set or sets that the permission is granted through. In this section, you can edit the value in each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, **Execute Permission**.

   > [!NOTE]  
   > Only permission sets of type **User-Defined** can be edited.
   >
   > Rows of source Entitlement originate from the subscription license. The permission values of the entitlement overrule values in other permission sets if they have a higher ranking. A value in a nonentitlement permission set that has a higher ranking than the related value in the entitlement is surrounded by brackets. The brackets indicate that it isn't effective because the entitlement overrules it.
   >
   > To learn more about ranking, go to [Create a permission set](ui-define-granular-permissions.md#create-a-permission-set).  

1. To edit a permission set, in the **By Permission Set** part, on the line for a relevant permission set of type **User-Defined**, choose one of the five access type fields and select a different value.
1. To edit individual permissions within the permission set, choose the value in the **Permission Set** field to open the **Permissions** page.

> [!NOTE]  
> When you edit a permission set, the changes also apply to other users that have the permission set.

### Security filters limit a user's access to specific records in a table

For record-level security in [!INCLUDE[prod_short](includes/prod_short.md)], use security filters to limit a user's access to data in a table. You create security filters on table data. A security filter describes a set of records in a table that a user has permission to access. You can specify, for example, that a user can only read the records that contain information about a particular customer. In this way, the user can't access the records that contain information about other customers. To learn more, go to [Using Security Filters](/dynamics365/business-central/dev-itpro/security/security-filters) in the administration content.

## View permission changes telemetry

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to send changes that are done to permission to an Application Insights resource in Microsoft Azure. Then, using Azure Monitor, you create reports and set up alerts on the gathered data. To learn more, go to the following articles in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and admin help:

- [Monitoring and Analyzing Telemetry - Enabling Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-overview#enable)
- [Analyzing Field Monitoring Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-permission-changes-trace)

## Delegated admin users

[!INCLUDE [admin-gdap-users](includes/admin-gdap-users.md)]

## Related information

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Microsoft 365 for business](/microsoft-365/admin/add-users/add-users)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help  
[Assign a telemetry ID to users](/dynamics365/business-central/dev-itpro/administration/telemetry-enable-application-insights#assign-a-telemetry-id-to-users)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
