---
title: Personalizing the Way Information is Displayed for a User Account | Microsoft Docs
description: Describes how to customize the look and feel of Business Central for your user account.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize
ms.date: 03/29/2017
ms.author: sgroespe

---
<!-- # User Personalization
You can change how certain UI elements are displayed in your version of [!INCLUDE[d365fin](includes/d365fin_md.md)] to best serve your needs.

> [!NOTE]  
>   Personalizations apply to your user account only. Other users do not see them.

## To add or remove a column
On lists and document lines, not all available column information is displayed by default. You can add or remove columns with the **Choose Columns** function.

1. Open the window with a list or document lines that you want to add or remove columns on.
2. Choose any column heading, access the drop-down menu, and then choose the **Choose Columns** action.
3. In the **Choose Columns** window, select or clear the **Visible** check box for the columns that you want to add or remove.
4. Choose the **OK** button.
-->
# Personalize Your Workspace
<!--NAV in the Web client-->
You can customize, or *personalize*, your workspace to suit your work and preferences by changing pages so that they display only the information you need, where you need it. The personalization changes that you make will only affect what you see, not what other users see.

Depending on the type of page and what it includes, you can:

-   Add, move, and remove fields.
-   Add, move, and remove columns in a list.
-   Change the freeze pane of columns in a list.

    The freeze pane defines the columns that always appear in the list, even when you scroll horizontally.
-   Add, move, and remove cues (tiles).
-   Move and remove entire parts.

    Parts are typically larger areas on a page that contain elements such as another page, a chart, or tiles.  

## Personalization in detail
To help you better understand personalization, here are some pointers.  
-   When you make changes to a card page of record that you open from a list, the changes will take effect on all records that you open from that list. For example, let's say you open a specific customer from the Customers list page, and then personalize the page by adding a field. When you open other customers from the list, the field that you added will also be shown.
-   Changes that you make will take effect on all your Role Centers. For example, if you make a change to the Customer list when the Role Center is set to Business Manager, you will also see the change in the Customer list when Role Center is set to Sales Order Processor.
-   Changes to a page in a part will take effect where ever the part is used.  
-   You can only add fields, columns, or tiles from a predetirmend list based on the page. You cannot create new ones.

<!--NAV

-   You can perform personalization in either the Web client or the Windows client. When you start to personalize a page in the Web client, if the page has already been personalized by using the Windows client, you will get a message. If you continue in the Web client, the personalization that was done in the Windows client will be removed. The page is restored to its original layout, from which you can start to personalize for the Web client only. In the Windows client, the personalization will remain as is. If you want to keep the personalization in the Windows and Web clients identical, you should use the Windows client. #-->       

## To personalize a page

1. In the upper-right corner, select the ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, and then **Personalize**.

    The **Personalizing** bar appears at the top to indicate that you can start making changes.

    ![Personalize mode](media/ui_personalize_mode.png "Personalize mode")

    Choose **More** to see additional personalization actions.

2.  Go to a page that you want to personalize.

3.  Point to an area or component that you want to personalize, such as a field or column header in a list.

    -   If a component can be personalized, an arrow head (![Personalization indicator arrow left](media/ui_personalize_arrow_left.png "Personalization indicator arrow left") or ![Personalization indicator arrow down](media/ui_personalize_arrow_down.png "Personalization indicator arrow down")) appears.
    -   If the component is a part, the extent of the part is indicated by a border.
    -   The freeze pane in a list is indicated by a vertical line along the entire right-side of the last column of the freeze pane.

4.  Use this table to help make changes:
        <table>
        <tr><th>What do you want to do</td><th>How to do it</th></tr>
        <tr><td>Move the component, like a field, column in list, tile, or part</td><td> Point anywhere on component, and drag it to its new location. The location is indicated by either a thick horizontal or vertical line.</td></tr>
        <tr><td>Remove the component</td><td>Select the arrowhead, and choose <b>Remove</b>.</td></tr>
        <tr><td>Change the freeze pane in a list to another column</td><td>Select the arrowhead of the column that you want as the last column of the freeze pane, and then choose <b>Set Freeze Pane</b>.<br /></br>If you do not want a freeze pane, select the arrowhead for the current freeze pane column, and choose <b>Clear Freeze Pane</b>.</td></tr>
        <tr><td>Add a field, column, or tile</td><td>In the <b>Personalizing</b> bar, choose <b>More</b>, and then choose <b>Field</b>.<br /></br>The <b>Add Field to Page</b> pane opens on the right that lists the fields that you can add to the page. Fields marked as <b>Placed</b> are already on the page. Fields marked as <b>Ready</b> are not currently on the page.<br /></br>To add a field, drag it from the pane to the location that you want it. The location is indicated by either a thick horizontal or vertical line.</td></tr>
        </table>

    > [!IMPORTANT]  
    >   You cannot make changes to a list if the list is shown as tiles. You must first switch the page to the list view by selecting the ![Show as list](media/ui_show_as_list_icon.png "Show as list arrow left") icon.

5.  You can continue to make changes on the same page or move to another page. Your changes are automatically saved as you make them. When you are done, in the **Personalizing** bar, choose **I'm Done**.

## Undo personalization and restore a page to its original layout
At some point, you might want to undo all the personalization changes that you have made over time to a page so that page looks like it originally. To do this, choose the ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, **Personalize**, and then **Undo All**. You will not see the changes, until you close and open the page again.

## See Also
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Changing Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)  
