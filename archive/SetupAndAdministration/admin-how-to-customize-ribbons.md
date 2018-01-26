---
    title: How to Customize Ribbons | Microsoft Docs
    description: By opening the **Customize Ribbon** window from any page that has a ribbon, you can customize the ribbon to optimize it for your work processes and preferences. For example, if you frequently use the **Dimensions** window, you can add the **Dimensions** action to the **Process** actions group. You can also remove actions that you never use for better overview.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Customize Ribbons
By opening the **Customize Ribbon** window from any page that has a ribbon, you can customize the ribbon to optimize it for your work processes and preferences. For example, if you frequently use the **Dimensions** window, you can add the **Dimensions** action to the **Process** actions group. You can also remove actions that you never use for better overview.  
  
 ![Customize ribbon dialog for selecting actions](../media/rtc_customizeribbon.png "RTC_CustomizeRibbon")  
  
> [!NOTE]  
>  Depending on the setting in the **UI Elements Removal** field in the ADD INCLUDE<!--[!INCLUDE[nav_admin](../../includes/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md).  
  
 You can make multiple customizations of the same page based on different access points to the page. For example, you can customize that the ribbon in the **Sales Orders** window looks different when the window is opened from the **Customer Card** window than when it is opened from your Role Center. The point from which you access the page to be customized is recorded in that specific page customization. Accordingly, there may be multiple customization records for the same page under your logon, as you can see in the **Delete User Personalization** window.  
  
 You can perform the following tasks to customize ribbons on pages:  
  
-   Add, rename, or remove tabs, groups, actions, and menus.  
  
-   Change the order of actions.  
  
-   Restore the ribbon to its default setting.  
  
> [!IMPORTANT]  
>  Be aware of the following limitations when you customize the ribbon.  
>   
>  -   System tabs or groups such as **Home** or **New** cannot be moved or renamed. The position of some groups, such as **New Document** is fixed.  
> -   Actions or groups that have dynamic visibility cannot be added or removed.  
> -   If you see unexpected behavior with groups and actions after having customized the ribbon, do the following:  
>   
>      1.  Empty, but do not delete, the group where the problem occurs.  
>     2.  Close the dialog using the **OK** button.  
>     3.  Open the dialog again and re-add the actions to the group.  
  
> [!CAUTION]  
>  Any customization that alters the ribbon could affect the guidance provided in the [!INCLUDE[d365fin](includes/d365fin_md.md)] Help, because navigation steps in Help may refer to a different ribbon layout.  
  
 The following procedures describe how to perform typical customization of ribbons by working with groups, but the same steps apply to working with tabs.  
  
### To start customizing a ribbon  
  
-   On a page with a ribbon, on the **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Customize Ribbon**.  
  
### To filter for actions  
  
-   In the **Available actions** field, type to filter for the action type that you want to add. The list of available actions is filtered as you type.  
  
### To add a new group  
  
1.  On the right side of the window, choose the **Create Group** button.  
  
2.  Enter the name of the new group.  
  
### To rename an existing group  
  
1.  Select a group to rename, and on the right side of the window, choose the **Rename** button.  
  
2.  Enter a new name for the group.  
  
### To remove an existing group  
  
-   Select a group to remove, and on the right side of the window, choose the **Remove** button.  
  
### To add an action to a group  
  
1.  Select a group to move the action into.  
  
2.  Locate the action under **Available actions**, and choose the **Add** button.  
  
    > [!NOTE]  
    >  In some cases, an action can be a promoted action if the **PromotedIsBig** property is set to **Yes** in the ADD INCLUDE<!--[!INCLUDE[nav_dev_long](../../includes/How%20to:%20Promote%20Actions%20on%20Pages.md).  
  
### To create a menu of actions  
  
1.  On the right side of the window, choose the **Create Menu** button.  
  
    > [!NOTE]  
    >  You can only create menus inside groups, not inside tabs.  
  
2.  Enter the name of the new menu.  
  
3.  Move actions from **Available actions** into the new menu.  
  
> [!CAUTION]  
>  You can nest a menu within another menu, but this is not recommended.  
  
### To change the order of actions  
  
-   Select the action to move, and then choose the **Move up** or **Move down** button several times to move the action to the desired position in the hierarchy.  
  
### To restore default settings  
  
-   In the **Customize** window, choose **Restore Defaults**, and then choose the **OK** button.  
  
    > [!NOTE]  
    >  All customization of ribbons that you have ever made for this page under your current user logon or since you last used the **Restore Defaults** button are canceled. The layout of the ribbon on the page is reset to the default configuration for your profile. For more information, see [Cancel UI Personalization](../how-to-cancel-ui-personalization.md).  
  
## See Also  
 [Ribbon](../ribbon.md)   
 PERSONALIZATION Personalize the User Interface   
 [Define Promoted Action Categories Captions for the Ribbon](../How%20to:%20Define%20Promoted%20Action%20Categories%20Captions%20for%20the%20Ribbon.md)   
 [Troubleshooting: Removing Promoted Actions in Home Tab](../troubleshooting-removing-promoted-actions-in-home-tab.md)   
 [Customize FastTabs](../how-to-customize-fasttabs.md)   
 [Customize FactBoxes](../how-to-customize-factboxes.md)   
 [Cancel UI Personalization](../how-to-cancel-ui-personalization.md)   
 Delete User Personalization   
 [Customize the User Interface](../customize-the-user-interface.md)   
 [Working with Product Name](../working-with-$-p_1-product-name-$-.md)   
 [Learn About the RoleTailored Design](../learn-about-the-roletailored-design.md)