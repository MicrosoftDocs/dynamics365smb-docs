---
title: Customizing Pages for Roles
description: Learn how to customize the user interface for a profile (role) so that all users assigned that role see a customized workspace.
author: jswymer
ms.topic: how-to
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.search.form: 9171
ms.date: 06/13/2024
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Customize pages for profiles

Business Central provides both [personalization](ui-personalization-user.md) for users and customization for administrators. Personalization allows users to tailor their workspace by adjusting page layouts to suit their own preferences. Administrators can customize page layouts for a specific profile, based on business roles or departments, so that all assigned users see the same customized page. While personalization allows users to show, hide, and move fields and actions on a page, customization offers extra capabilities. For example, customization allows you to show fields that are in the page's source table or extension tables but aren't defined on the page object&mdash;this isn't possible personalization.  <!--For more information, see [Personalize Your Workspace](ui-personalization-user.md).-->

<!--Similarly, administrators can customize pages for a profile, according to the related business role or department, so that all users assigned the profile see the customized page layout. As an administrator, you customize pages by using the same functionality as users do when they personalize pages, except with few extra capabilities. Like personalization, you can show, hide, and move fields, actions, or parts on a page. But while personalization only allows you to work with fields that are defined on the page object, customization allows you add fields that are in the source table or table extension, but not defined on the page object. -->

> [!NOTE]
> The typical business use of a profile is a role. A profile is therefore named *Profile (Role)* in the UI.

Page customization starts from the **Profiles (Roles)** page, the administrator's starting point for managing users' profiles on individual profile cards. In addition to customizing the page layout, you control various other settings for profiles on the **Profile (Role)** page for each profile. For more information, see [Manage Profiles](admin-users-profiles-roles.md).

## Prerequisites

- Your Business Central account must have the **D365 Profile Mgt.** permission set or equivalent permissions. 

   The **D365 Profile Mgt.** permission set includes the execute permission on the system object **9026 Add Field to Table**. If you don't have this permission, you're not allowed to add fields on the page unless they're defined on the page object. 

## Customize pages for a profile

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Profiles (Roles)**, and then choose the related link.
2. Select the line for the profile that you want to customize pages for, and then choose the **Edit** action.
3. Choose the **Customize pages** action.

    [!INCLUDE[prod_short](includes/prod_short.md)] opens on a new browser tab for the selected profile with the **Customizing** banner activated. The **Customizing** banner offers the same functionality as the **Personalizing** banner that is available to users.

4. Customize pages according to the needs of the role or department in question in the same way as a user would do when personalizing. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

    > [!NOTE]
    > To navigate during personalization, use <kbd>Ctrl</kbd>+<kbd>Click</kbd> on an action if it is highlighted by the arrowhead.

5. When you have finished changing the layout on one or more pages, choose the **Done** button on the **Customizing** banner.
6. Close the browser tab.

The customization of pages is now recorded for the profile.

## View all customized pages for a profile

You can get an overview of which pages are customized for a profile, for example to plan which pages to customize further or delete.

- On the **Profile (Role)** page, choose the **Manage customized pages** action.

On the **Customized Pages** page, you can delete customizations, and you can troubleshoot by scanning for potential issues.  

## Delete all customizations for a profile

You can cancel all customizations that you have made for a profile. Customizations introduced with an extension and personalizations made by a user aren't deleted. You can delete all personalizations with another action. For more information, see [To delete all personalizations made by a user](admin-users-profiles-roles.md#delete-all-personalizations-made-by-a-specific-user).

- On the **Profile (Role)** page for a customized profile, choose the **Clear customized pages** action.

The layout on pages for the profile is reset to the default layout.  

## Delete customization for specific pages for a profile

You can delete individual page customizations that you have made for a profile. Customizations introduced with an extension and personalizations made by a user aren't deleted. You can delete specific page personalizations with another action. For more information, see [To delete personalizations for specific pages](admin-users-profiles-roles.md#delete-personalizations-for-specific-pages).

1. On the **Profile (Role)** page, choose the **Manage customized pages** action.
2. On the **Customized Pages** page, select one or more lines for page customizations that you want to delete, and then choose the **Delete** action.

The layout on the selected pages is adjusted to the changes you made.

## Add a field

You add fields to the page from the **Add field to page** pane, which you open by selecting the **+ Field** action when in the customization mode. It's important to understand that the **Add field to page**  pane is used to show fields that already exist&mdash;either on the page and its source tables,&mdash;but are currently hidden from view. You can't create new fields.

The **Add field to page** pane presents all fields that can be shown on the page. Fields are divided into the following categories, as determined by the underlying design of the page itself, its source table, and extensions:

|Category|Description|
|-|-|
|Table fields not on the page object|Includes fields that are defined in the base table or extension tables, but aren't defined on the page. The tooltip for these fields includes the label **Defined by the table**.<br><br>|
|Page fields bound to a table|Includes fields that are defined in the base table or table extensions and are also defined on the page as either shown or hidden. The tooltip for these fields includes the label **Defined by the page**.|
|Page fields that aren't bound to a table| Fields that are only defined on the page, not in the base table or extension tables. These fields typically used for variable or calculation. The tooltip for these fields includes the label **Defined by the page**.|

<!--
- Table fields not on the page object. Includes fields that are defined in the base table or extension tables, but aren't defined on the page, either as shown or hidden.   
- Page fields bound to a table. Includes fields that are defined in the base table or table extensions and are also defined on the page as either shown or hidden. 
 - Page fields that are not bound to a table. Fields that are Includes fields that are only defined on the page, not in base table or extension table. These fields typically used for variable or calculation. -->

Use the filter button above the list to change what category of fields are presented the **Add field to page** pane.  

:::image type="content" source="media/customization-filter.svg" alt-text="Shows the filter button in the Add a field pane in the customization mode.":::
 
### Add table field that's not on the page object

If you want to make a table-only field available on a page to users, you must first add it to the page. Once you've added the field, users can choose to show or hide the field by using personalization. There are couple ways to add a field.

- One way is to drag it from  **Add field to page** pane to the desired position.
- Another way is to select the field in the pane to display the recommended location on the page. Then go to the field location on the pages, select the arrowhead, then select **Add**. 

Once the field has been added, the tooltip for the field in the  **Add field to page** pane switches to **Defined by the page**.

> [!NOTE]
> The added field is locked from editing and can't be unlocked.

## Remove a field

If you've added a table field that originally wasn't on the page object, you can remove it again. Removing a field is different that hiding it. When you hide a field, users can still show it on their workspace through personalization. However, if you remove a field, the field is no longer available for users to show, or hide for that matter. If the field is currently displayed on a user's workspace, it disappears from their workspace when you remove it. 

To remove a field, select the arrowhead on the field in the page and then **Remove**. If you can't find the field, select it in the **Add field to page** pane to indicate its hidden location. 

> [!IMPORTANT]
> Removing a field doesn't delete data that's stored in the field or it's source tables. It just removes the field from view. 

## Lock and unlock editing

Customization allows you to lock (allow editing) or unlock editing (prevent editing) of most fields on a page. To lock or unlock editing, select the field on the page, select the arrowhead, and then select **Lock editing** or **Unlock editing**. It's important to keep in mind a few rules about locking and unlocking fields:

- Field's that were originally not on the page object but were added to the page by customization are always locked, and can't be unlocked using customization or personalization.
- The design of the field can also prevent it from being edited. If the AL developer set the field's [Editable property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-editable-property) to `false`, it's always locked and can't be unlocked.
- It's important to note that the lock editing feature is intended to aid in the accuracy, consistency, and reliability of data. It's not intended to secure data integrity.


<!--However, whatever option you choose for a field, users can always change the setting on their own workspace using personalization. For this reason, it's important to consider locking as a deterrence measure and not a preventative measure.--> 
## Important information and tips

- Not all table fields may be available for customization from the **Add field to page** pane. The developer of a table can choose to prevent a field from appearing in customization by setting the field's [AllowInCustomization property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-allowincustomizations-property) to `Never`.
- You can't customize a page that's in [analysis mode](analysis-mode.md). The **Analyze** switch is deactivated. If you switch to customization mode while the page is in analysis mode, then analyze mode is automatically switched off. 
- Some pages have multiple page fields that map to the same source table. The **Add field to page** pane shows all of these page fields independently. You can show, hide, or move these fields independently without affecting the others.
- If a part or group is hidden, you can still identify hidden fields inside the part or group, but you can't add, move or show fields in the part or group until they're made visible. 
## Related information

[Personalize Your Workspace](ui-personalization-user.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
