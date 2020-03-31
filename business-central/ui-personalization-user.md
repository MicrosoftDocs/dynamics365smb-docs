---
title: Personalizing Pages | Microsoft Docs
description: Learn how to customize the user interface to suit your way of working in Business Central.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields, resize column, change column width
ms.date: 04/01/2020
ms.author: sgroespe

---
# Personalize Your Workspace
You can personalize your workspace to suit your work and preferences by changing pages so that they display only the information you need, where you need it. The personalization changes that you make will only affect what you see, not what other users see.

You can personalize all types of pages, including the Role Center page. For more information about Role Centers, see [Role Center](ui-change-basic-settings.md#role-center).

Depending on the type of page and what it includes, you can make various changes, such as move or hide fields, columns, actions, and entire parts, and add new fields. Most personalization must be done by first activating the **Personalizing** banner, but very simple adjustments, such as column width can be performed immediately on any list.

> [!NOTE]
> Administrators can perform the same layout changes as users can by customizing the workspace for a profile that multiple users are assigned. For more information, see [Customize Pages for Roles](ui-personalization-manage.md)<br /><br />
Administrators can also override or disable users' personalization, and they can define which features are even available for users to see in all or specific companies. For more information, see [Customizing Business Central](ui-customizing-overview.md).

## To change the width of a column
You can easily resize columns on any list by dragging the boundary between two columns to the left or the right.
1. In the header of a list, select and drag the boundary between two columns.
2. Alternatively, double-click the boundary between two columns to auto-fit the width of the column. This sets the width to the optimal size for readability.

As for other personalization, the changes you make to column width are stored on your account and follow you no matter which device you sign into.

## To start personalizing a page through the **Personalizing** banner
1. Open any page that you want to personalize.
2. In the upper-right corner, select the ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, and then choose the **Personalize** action.

    The **Personalizing** banner appears at the top to indicate that you can start making changes.

    > [!NOTE]
    > To navigate during personalization, use Ctrl + Click on an action if it is highlighted by the arrowhead.

    If you see a ![Personalize Lock](media/personalization-lock-icon.png "Personalize lock") or ![Personalization blocked](media/personalization-blocked-icon.png "Personalization blocked") on the banner, you cannot personalize the page. For more details, see [Why a Page is Locked from Personalization](ui-personalization-locked.md).

3. To add a field, choose the **+ Field** action.
4. From the **Add Field to Page** pane, drag and drop a field into the desired position on the page.
5. To change a UI element, point to the element, such as an action, a field, or a part. The element is immediately highlighted with an arrowhead or border.
6. Choose the element, and then choose either **Move**, **Remove**, **Hide**, **Show**, **Show under "Show more"**, **Show when collapsed**, **Show always**, **Set/Clear Freeze Pane**, or **Include/Exclude from Quick Entry**, depending on the type and state of the UI element. For more information, see [What You Can Personalize](#What).
7. When you have finished changing the layout of one or more pages, choose the **Done** button on the **Personalizing** banner.

## <a name="What"></a>What You Can Personalize

|What do you want to do|How to do it|Remarks|
|----|------------|-------|
|Move something, like a field, column in list, tile, action, or part|Point anywhere on what you want to move, and drag it to its new position. The position is indicated by either a thick horizontal or vertical line.<br /><br />![Cannot move here icon](media/personalization-cannot-move-here.png "Personalizing mode - Cannot move here icon") indicates that you cannot move the element to the selected position.|Parts are subdivisions or areas on a page that contain things like multiple fields, another page, a chart, or tiles.<br /><br />For more details about action personalization, see [Personalizing Actions](ui-personalization-user.md#Actions). |
|Hide something, like a field, column in list, tile, action, or part.|Choose the arrowhead, choose <b>Hide</b>.|The element is grayed when you are in personalizing mode. If the field you hide is also shown on the FastTab heading when the FastTab is collapsed, the field will no longer appear there.|
|Show hidden actions and parts.|For a grayed (hidden) element, choose the arrowhead, and then choose <b>Show</b>.|The hidden element is visible again.|
|Add a field or column.|In the <b>Personalizing</b> banner, choose the <b>+ Field</b> action.<br /></br>The <b>Add Field to Page</b> pane opens on the right. It lists the fields that you can add to the page.<br /><br />To add a field, drag it from the pane to the position that you want it. The position is indicated by either a thick horizontal or vertical line.|Each page includes a predefined set of fields that you can display. Use this procedure to add fields or columns that have not been previously displayed or to show fields that you have hidden.|
|Display a field in the heading of a Fastab when the FastTab is collapsed.|Choose the arrowhead, and then choose <b>Show when collapsed</b>. <br /> <br />If you do not see this option, then it is already set. In this case, to stop displaying the field on the FastTab heading, choose <b>Show always</b>.|*FastTab* is the term used for a group of fields that appear under a common heading. Use the <b>Show when collapsed</b> option to display the most important fields. If you select a field in the heading, the FastTab will open and focus on the selected field.<br /><br />This option is only applicable if a page has a more than one FastTab. If the is only one FastTab, it cannot be collapsed, so the <b>Show when collapsed</b> option is not available.|
|Make a field display only when you select **Show more**.|Choose the arrowhead, and then choose <b>Show under "Show More"</b>. <br /> <br />If you do not see the <b>Show under "Show More"</b> option, then it is already set. In this case, to make a field display always, not just when you select **Show more**, choose <b>Show always</b>.||
|Change the freeze pane in a list to another column. |Choose the arrowhead of the column that you want as the last column of the freeze pane, and then choose <b>Set Freeze Pane</b>.<br /><br/>If you want to set the freeze pane back to its original designed position, choose the arrowhead for the current freeze pane column, and choose <b>Clear Freeze Pane</b>. Note: You cannot remove this freeze pane.|The freeze pane specifies the columns that always appear on the left, even as you scroll horizontally.|  
|Skip over a field when pressing Enter.|Choose the arrowhead next to the field, or column heading in a list, and choose **Exclude from Quick Entry**. <br /><br /> If you do not see this option, then the field is already set to be skipped. In this case, to stop skipping the field, choose **Include in Quick Entry**. |See [Accelerating Data Entry Using Quick Entry](ui-enter-data.md#QuickEntry)|
|Reorder and remove views representing filtered lists.|Choose the arrowhead next to a view, and then choose **Move**, **Remove**, or **Hide**.|See [Save and Personalize List Views](ui-views.md)|  
|Add a new action to a page or report on your Role Center.|From the target page, report request page, or Tell Me window, choose the bookmark icon.|See [Bookmark a Page or Report on Your Role Center Role Center](ui-bookmarks.md)|
|Always start a list as expanded or collapsed|Choose the Expand All or Collapse All button in the top-left corner of the list, or choose the Expand All or Collapse All action in the menu of the first column. |Applies to collapsible hierarchy lists|

## <a name="Actions"></a>Personalizing Actions

Personalization lets you decide which actions to show on the navigation and action bars and on Role Centers and where to show them. You can show, hide, or move individual actions or action groups. Personalizing the navigation and action bars is done basically the same way as with other UI elements. However, what you can do with an action or group depends on where the action or group is located. The best way to find out is to enter personalizing mode and then let the arrowheads guide you.

There are a couple terms that you should be familiar with to better understand action personalization: *action group* and *promoted category*.  

An *action group* is an element that expands to display other actions or groups. For example, on the **Sales Orders** page, the **Functions** action that appear when you choose the **Actions** action is an action groups.

A *promoted category* is an action group that appears before the vertical line `|` on the action bar. The categories typically include the most commonly used actions, so that you can quickly find them. For example, on the **Sales Orders** page, the **Order**, **Release**, and  **Posting** actions are promoted categories.

> [!NOTE]
> You cannot personalize the action bar that appears in parts on the page (for example, the sales lines part on the **Sales Order** page).

### To remove, hide, and show actions and action groups
When you want to show or hide an action, the options under the arrowhead define what can do depending on the action's state.
1. Choose the arrowhead for an action or action group.
2. Choose from one of the following options:

|Option|What it does|
|------|------------
|**Remove**|This option appears if the selected action is also shown somewhere else on the navigation bar or action bar. Choosing this option deletes the action from the selected location so that it no longer appears. The action or action group will remain in the other locations. |
|**Hide**|This option appears if the action or action group is not located anywhere else on the navigation bar or action bar. Like **Remove**, choosing this option will make the action or action group disappear from the navigation bar or action bar. However, in personalizing mode, the action or action group will still be shown in the current position, except that it appears dimmed.|
|**Show**|This option appears if the action or action group has been previously hidden (dimmed). Choosing this option will make the action or action group appear on the navigation bar or action bar.|

### To move actions and action groups
Where you can drop actions or actions groups is indicated by a horizontal line between two actions or a border around an action group. The following limitations exist:

- You can move individual actions into the promoted categories, but you cannot rearrange the order of the actions in the category.
- You cannot move an action group into a promoted category.

1. To move an action or action group, drag and drop it to the desired position, like you do with fields and columns.
2. To move an action or action group into another action group that is empty, drag the action or action group to the new group and drop it in the **Drop an action here** box.


## <a name="Parts"></a>Personalizing Parts

Parts are areas on a page that are typically composed of multiple fields, charts or other content, and can be identified by a colored border when setting focus to the part. For example, a Role Center home screen has multiple parts. Because of their well-defined boundary, you can personalize the entire part as well as its' contents.

- To move a part, drag and drop it to the desired position. A colored line indicates valid positions on the screen. For example, FactBoxes can only be moved next to other FactBoxes in the FactBox pane.
- You can hide a part by choosing the **Hide** option under the arrowhead.
- When you start personalizing or navigate to a new page, any parts that are currently hidden will appear on the page with distinctive visuals to indicate they are hidden. You can unhide that part by choosing the **Show** option under the arrowhead.

You can clear all personalization changes that you have made within a single part by choosing the **Clear personalization** option under the part's arrowhead. Clearing personalization of a part only affects changes to the contents of the part, not the placement or visibility of the part on the page.  


## To clear personalization
At some point, you might want to undo some or all of the personalization changes that you have made to a page over time.

1. On the **Personalizing** banner, choose the **Clear personalization** action.
2. Choose one of the following options. Be aware that clearing personalization cannot be undone.

|Option|What it does|
|------|------------
|**Only Navigation Menu**|Clears any personalization changes that you have ever made to the navigation menu that is shared across the Role Center and other pages. This includes any new actions that were added as bookmarks, and any changes to links and groups in the menu.|  
|**Only Actions**|Clears any personalization changes that you have ever made on the navigation or action bars on the page.|
|**Only Fields, Columns, and Parts**|Clears any personalization changes that you have ever made to the page except those on the navigation or action bar. This includes changes to fields, columns, parts, and tiles. |
|**All**|Clears all personalization changes that you have made to the page so it looks like it did originally. This includes changes to navigation and action bars, fields, columns, parts, and tiles.|

## Additional Points of Interest
To help you better understand personalization, here are some pointers.

- When you make changes to a card page that you open from a list, the changes will take effect on all records that you open from that list. For example, let's say you open a specific customer from the Customers list page, and then personalize the page by adding a field. When you open other customers from the list, the field that you added will also be shown.
- Changes that you make will take effect on all your Role Centers. For example, if you make a change to the Customer list when the Role Center is set to Business Manager, you will also see the change on the **Customers** page when the Role Center is set to Sales Order Processor.
- Changes to a page in a pane will take effect on the page where ever it is shown.  
- You can only add fields and columns from a predefined list, which is based on the page. You cannot create new ones.

## See Related Training at [Microsoft Learn](/learn/modules/personalize-ui-dynamics-365-business-central/index)

## See Also
[Customize Pages for Profiles](ui-personalization-manage.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
