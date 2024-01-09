---
title: Personalizing pages (contains video)
description: Learn how to customize the user interface and personalize your workspace to suit your way of working and personal preferences in Business Central.
author: jswymer
ms.topic: conceptual
ms.service: dynamics365-business-central
ms.custom: bap-template
ms.reviewer: jswymer
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields, resize column, change column width
ms.search.form: 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 12/05/2023
ms.author: jswymer
---
# Personalize your workspace

You can personalize your workspace to suit your work and preferences. Change pages so that they display only the information you need, where you need it. Personalization affects only your workspace. It doesn't change how others work. You can personalize all types of pages, including the [role center](ui-change-basic-settings.md#role-center) page.

> [!NOTE]
> Due to restrictions on design capabilities in the web client, it's currently not possible to customize or personalize the controls within the grid syntax.
It applies to all design modes, not just personalization.

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

You can make various changes, such as move or hide fields, columns, actions, and entire parts, and add new fields. Most personalization must be done by first activating the **Personalizing** banner. You can make simple adjustments, such as the column width, immediately on any list.

> [!NOTE]
> Administrators can make the same layout changes as users by customizing profile (role) that multiple users are assigned. To learn more about pages for Roles, go to [Customize Pages for Roles](ui-personalization-manage.md)<br /><br />
Administrators can also override or disable users' personalization, and they can define which features are even available for users to see in all or specific companies. For more information, see [Customizing Business Central](ui-customizing-overview.md).

## Video

The following video shows some of the ways in which you can personalize your Role Center.

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4ArUB?rel=0]

## Change the width of a column

You can easily resize columns on any list. Just drag the boundary between two columns to the left or the right.  

1. In the header of a list, select and drag the boundary between two columns.
2. Alternatively, double-click the boundary between two columns to autofit the width of the column. The width adjusts to the optimal size for readability.

As for other personalization, the changes you make to column width are stored on your account and follow you no matter which device you sign into.

## Start personalizing by using the personalization mode

1. Open any page that you want to personalize.
1. In the upper-right corner, select the ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, and then choose the **Personalize** action.

    The **Personalizing** banner appears at the top to indicate that you can start making changes.

    > [!NOTE]
    > To navigate during personalization, use <kbd>Ctrl</kbd>+<kbd>Click<kbd> on an action if it is highlighted by the arrowhead.

    If you see a ![Personalize Lock](media/personalization-lock-icon.png "Personalize lock") or ![Personalization blocked](media/personalization-blocked-icon.png "Personalization blocked") on the banner, you can't personalize the page. For more information, see [Why a Page is Locked from Personalization](ui-personalization-locked.md).

1. To change a UI element, point to the element, such as an action, a field, or a part. The element is immediately highlighted with an arrowhead or border. Choose the element, and then choose either **Move**, **Remove**, **Hide**, **Show**, **Show under "Show more"**, **Show when collapsed**, **Show always**, **Set/Clear Freeze Pane**, or **Include/Exclude from Quick Entry**, depending on the type and state of the UI element.
1. To add a field, choose the **+ Field** action. From the **Add Field to Page** pane, drag and drop a field into the desired position on the page.
1. When you have finished changing the layout of one or more pages, choose the **Done** button on the **Personalizing** banner.

For more information, see [What You Can Personalize](#What).

## <a name="What"></a>What you can personalize

|What do you want to do|How to do it|Remarks|
|----|------------|-------|
|Move something, like a field, column in list, tile, action, or part to another place on the page|Point anywhere on what you want to move, and drag it to its new position. A thick horizontal or vertical line indicates the position.<br /><br />![Cannot move here icon](media/personalization-cannot-move-here.png "Personalizing mode - Cannot move here icon") indicates that you can't move the element to the selected position.|Parts are subdivisions or areas on a page that contain things like multiple fields, another page, a chart, or tiles.<br /><br />[Learn more about personalizing actions](#Actions)<br>[Learn more about personalizing parts](#Parts)|
|Hide an element that's currently shown, like a field, column in list, tile, action, or part.|Select the element, select the arrowhead, and then select <b>Hide</b>.|In the personalization mode, hidden actions are grayed with italic text, and hidden parts are shaded by diagonal lines. Hidden fields and columns aren't indicated on the page. <!--The element is grayed when you are in personalizing mode.--> When you exit personalization mode, all elements disappear from view. If the field you hide is also shown on the FastTab heading when the FastTab is collapsed, the field no longer appears there.|
|Show an action or part that is currently hidden|For a grayed (hidden) element, choose the arrowhead, and then choose <b>Show</b>.|The hidden element is visible again.|
|Show a field that's currently hidden|In the <b>Personalizing</b> banner, choose the <b>+ Field</b> action.<br /></br>The <b>Add Field to Page</b> pane opens on the right side of the page. If you select a field in the pane, it's hidden location appears on the page.<br /><br />To show a field, drag it from the pane, or from its hidden location, to the position that you want it. The position is indicated by either a thick horizontal or vertical line.<br><br> Another way is to select the arrowhead in the field's hidden location and select **Show**. |Each page includes a predefined set of fields that you can choose to display.<br /><br />[Learn more about working fields](#fields) |
|Display a field in the heading of a FastTab when it's collapsed.|Choose the arrowhead, and then choose <b>Show when collapsed</b>. <br /> <br />If you don't see this option, then it's already set. In this case, to stop displaying the field on the FastTab heading, choose <b>Show always</b>.|*FastTab* is the term used for a group of fields that appear under a common heading. Use the <b>Show when collapsed</b> option to display the most important fields. If you select a field in the heading, the FastTab opens and focuses on the selected field.<br /><br />This option is only applicable if a page has a more than one FastTab. If there's only one FastTab, it can't be collapsed, so the <b>Show when collapsed</b> option isn't available.|
|Make a field display only when you select **Show more**.|Choose the arrowhead, and then choose <b>Show under "Show More"</b>.|If you don't see the <b>Show under "Show More"</b> option, then the field's already set. In this case, to make a field display always, not just when you select **Show more**, choose <b>Show always</b>.|
|Change whether or not a field can be edited.|Select the field, select the arrowhead on the field, and then select <b>Lock editing</b> to prevent changing the field's value or <b>Unlock editing</b> to allow changing the field's value.|You can only unlock fields that you've previously locked yourself. Some fields are locked by default, either by design or by a profile admin who has [customized the page](ui-personalization-manage.md). These fields can't be unlocked.|
|Change the freeze pane in a list to another column. |Choose the arrowhead of the column that you want as the last column of the freeze pane, and then choose <b>Set Freeze Pane</b>.<br /><br/>If you want to set the freeze pane back to its original designed position, choose the arrowhead for the current freeze pane column, and choose <b>Clear Freeze Pane</b>. Note: You can't remove this freeze pane.|The freeze pane specifies the columns that always appear on the left side of the list, even as you scroll horizontally.|  
|Skip over a field when pressing Enter.|Choose the arrowhead next to the field, or column heading in a list, and choose **Exclude from Quick Entry**.  | If you don't see **Exclude from Quick Entry**, then the field is already skipped. In this case, to stop skipping the field, choose **Include in Quick Entry**.<br><br>[Learn more about Quick Entry](ui-enter-data.md#QuickEntry)|
|Reorder and remove views representing filtered lists.|Choose the arrowhead next to a view, and then choose **Move**, **Remove**, or **Hide**.|[Learn more about saving and personalizing list views](ui-views.md)|  
|Add a new action to a page or report on your Role Center.|From the target page, report request page, or Tell Me window, choose the bookmark icon.|[Learn more about bookmarking pages and reports](ui-bookmarks.md)|
|Always start a list as expanded or collapsed|Choose the **Expand All** or **Collapse All** button in the top-left corner of the list. Alternatively, choose the **Expand All** or **Collapse All** action in the menu of the first column. |Applies to collapsible hierarchy lists|

## <a name="Actions"></a>Personalize action bar and menus

Personalization lets you decide which actions to show on the navigation and action bars and on Role Centers, and where to show them. You can show, hide, or move individual actions or action groups.

The following video shows how you can personalize actions on pages and Role Centers.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE594m2]

Personalizing the navigation and action bars is done basically the same way as with other UI elements. However, what you can do with an action or group depends on where the action or group is located. The best way to find out is to enter personalizing mode and then let the arrowheads guide you.

There are a couple terms that you should be familiar with to better understand action personalization: *action group* and *promoted category*.  

An *action group* is an element that expands to display other actions or groups. For example, on the **Sales Orders** page, one action group is the **Functions** action that appears when you choose the **Actions** action.

A *promoted category* is an action group that appears before the vertical line `|` on the action bar. The categories typically include the most commonly used actions, so that you can quickly find them. For example, on the **Sales Orders** page, the **Order**, **Release**, and  **Posting** actions are promoted categories.

> [!NOTE]  
> To clear personalization, select the arrowhead around the part's designer menu, and then choose **Clear personalization**.

### Remove, hide, and show actions and action groups

When you want to show or hide an action, the options under the arrowhead define what can do depending on the action's state. 

1. Choose the arrowhead for an action or action group.
2. Choose from one of the following options:

|Option|What it does|
|------|------------
|**Remove**|This option appears if the selected action is also shown somewhere else on the navigation bar or action bar. Choosing this option deletes the action from the selected location so that it no longer appears. The action or action group remains in the other locations. |
|**Hide**|This option appears if the action or action group isn't located anywhere else on the navigation bar or action bar. Like **Remove**, choosing this option makes the action or action group disappear from the navigation bar or action bar. However, in personalizing mode, the action or action group are still shown in the current position, except that it appears dimmed.|
|**Show**|This option appears if the action or action group has been previously hidden (dimmed). Choosing this option makes the action or action group appear on the navigation bar or action bar.|

### Move actions and action groups

Where you can drop actions or actions groups is indicated by a horizontal line between two actions or a border around an action group. The following limitations exist:

- You can move individual actions into the promoted categories, but you can't rearrange the order of the actions in the category.
- You can't move an action group into a promoted category.

1. To move an action or action group, drag and drop it to the desired position, like you do with fields and columns.
2. To move an action or action group into another action group that is empty, drag the action or action group to the new group and drop it in the **Drop an action here** box.

### About the Automate menu

- You can't hide or move the **Automate** menu or the **Power Automate** submenu and its actions.
- You can move flows included under the **Automate** item, but you can't hide them using personalization. Moving the flow makes a copy the flow to the destination, it doesn't remove it from the **Automate** item.

> [!TIP]
> As an administrator, you can hide the **Automation** item from users. Learn more at [Set Up Power Automate Integration](/dynamics365/business-central/dev-itpro/powerplatform/power-automate-setup).

## <a name="Parts"></a>Personalize parts

Point to or select <kbd>Alt</kbd>+<kbd>Up Arrow</kbd>
Parts are areas on a page that are typically composed of multiple fields, charts or other content. A part shows a colored border when you focus on the part. For example, a Role Center home screen has multiple parts. Because of their well-defined boundary, you can personalize the entire part and its' contents.

- To move a part, drag and drop it to the desired position. A colored line indicates valid positions on the screen. For example, FactBoxes can only be moved next to other FactBoxes in the FactBox pane.
- You can hide a part by choosing the **Hide** option under the arrowhead.
- When you start personalizing or navigate to a new page, any parts that are currently hidden appear on the page with distinctive visuals to indicate they're hidden. You can unhide that part by choosing the **Show** option under the arrowhead.

You can clear all personalization changes that you have made within a single part by choosing the **Clear personalization** option under the part's arrowhead. Clearing personalization of a part only affects changes to the contents of the part, not the placement or visibility of the part on the page.  

## <a name="fields"></a> Work with fields and columns

When personalizing a page, you use **Add field to page** pane to show fields that are currently hidden on the page. You open this pane by selecting the **+ Field** action near the top of the page. Unlike other elements, hidden fields aren't indicated on the page itself in personalization mode. However, you can identify hidden fields by using the **Add field to page** pane.

To make working with fields easier, here are some general guidelines to follow when using the **Add field to page** pane:

- By default, the pane lists all hidden fields, which are marked by the [Shows the hidden field icon](media/hidden-icon.png "Shows the hidden field icon") icon.
- You can filter the list show other fields, like those currently shown on the page, by selecting the **Recommended fields** button above the list and choosing a filter option. The name of the button changes  based on the filter option you choose.
  
   :::image type="content" source="media/personlaization-filter.svg" alt-text="Shows the filter button in the Add a field pane in the personalization mode.":::
- Selecting a field in the list highlights its location on the page. If the field's currently hidden, it's designed location is shown in a shaded state. 
- To get more details about a field in the list, point to it or select <kbd>Alt</kbd>+<kbd>Up Arrow</kbd> to display a tooltip.
- The fields available in the Add field to page pane are determined by the developer of the page and its source table, or by a profile admin who has [customized the page](ui-personalization-manage.md). You can't create new ones.
- Some pages have multiple page fields that map to the same source table. The pane will show both/all of those page fields independently. Showing/Hiding/moving those fields is also independent without one affecting the other.


### Make a hidden field visible

There are two ways to show a field that's currently hidden on the page:

- Drag the field to the desired position. A thick horizontal or vertical line indicates the target location.
- Select the field in the list, then go to the shaded field on the page and select the **Show** option.

## Clear personalization

At some point, you might want to undo some or all of the personalization changes that you have made to a page over time.

1. On the **Personalizing** banner, choose the **Clear personalization** action.
2. Choose one of the following options.  

> [!CAUTION]
> Clearing personalization can't be undone.

|Option|What it does|
|------|------------
|**Only Navigation Menu**|Clears any personalization changes that you have ever made to the navigation menu that is shared across the Role Center and other pages. Such changes include any new actions that were added as bookmarks, and any changes to links and groups in the menu.|  
|**Only Actions**|Clears any personalization changes that you have ever made on the navigation or action bars on the page.|
|**Only Fields and Columns**|Clears any personalization changes that you have ever made to the page except changes on the navigation or action bar. Such changes include changes to fields, columns, parts, and tiles. |
|**All**|Clears all personalization changes that you have made to the page so it looks like it did originally. Such changes include changes to navigation and action bars, fields, columns, parts, and tiles.|

## Tips and other points of interest

To help you better understand personalization, here are some pointers.

- When you make changes to a card page that you open from a list, the changes take effect on all records that you open from that list. For example, let's say you open a specific customer from the Customers list page, and then personalize the page by adding a field. When you open other customers from the list, the field that you added is also shown.
- Changes that you make affect all your Role Centers. For example, if you make a change to the Customer list when the Role Center is set to Business Manager, you also see the change on the **Customers** page when the Role Center is set to Sales Order Processor.
- Changes to a page in a pane take effect on the page where ever it's shown.  
- You can't personalize a page that's in [analysis mode](analysis-mode.md). The **Analyze** switch is deactivated. If you happen to switch to personalization mode while the page is in analysis mode, then analyze mode is automatically switched off. 
- Some pages have multiple page fields that map to the same source table. The pane will show both/all of those page fields independently. Showing/Hiding/moving those fields is also independent without one affecting the other.
- If a part or group is hidden, ghosted fields will still show inside it, but you cannot drag-drop or add/show that field until you make the group/part visible.


## See also
[Customize Pages for Profiles](ui-personalization-manage.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
