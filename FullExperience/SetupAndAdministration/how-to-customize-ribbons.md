---
title: "How to: Customize Ribbons"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "ribbon"
ms.assetid: 87ece5bf-2e88-4a6d-a6af-963c13bb9c2b
caps.latest.revision: 33
ms.author: "solsen"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Customize Ribbons
By opening the **Customize Ribbon** window from any page that has a ribbon, you can customize the ribbon to optimize it for your work processes and preferences. For example, if you frequently use the **Dimensions** window, you can add the **Dimensions** action to the **Process** actions group. You can also remove actions that you never use for better overview.  
  
 ![Customize ribbon dialog for selecting actions](../SetupAndAdministration/media/rtc_customizeribbon.png "RTC\_CustomizeRibbon")  
  
> [!NOTE]  
>  Depending on the setting in the **UI Elements Removal** field in the [!INCLUDE[nav_admin](../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)], only actions that you have permissions for will appear in the **Customize Ribbon** window. For more information, see [How to: Specify When UI Elements Are Removed](../Topic/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md).  
  
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
>     3.  Open the dialog again and re\-add the actions to the group.  
  
> [!CAUTION]  
>  Any customization that alters the ribbon could affect the guidance provided in the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] Help, because navigation steps in Help may refer to a different ribbon layout.  
  
 The following procedures describe how to perform typical customization of ribbons by working with groups, but the same steps apply to working with tabs.  
  
### To start customizing a ribbon  
  
-   On a page with a ribbon, on the **Application** menu ![Application Menu button in menu bar](../BusinessFunctionality/IntegratingWithMicrosoftOffice/media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Customize Ribbon**.  
  
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
    >  In some cases, an action can be a promoted action if the **PromotedIsBig** property is set to **Yes** in the [!INCLUDE[nav_dev_long](../BusinessFunctionality/DataExchange/includes/nav_dev_long_md.md)].  If an action has this setting, this takes precedence over your choices in the **Customize Ribbon** window. For more information, see [How to: Promote Actions on Pages](../Topic/How%20to:%20Promote%20Actions%20on%20Pages.md).  
  
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
    >  All customization of ribbons that you have ever made for this page under your current user logon or since you last used the **Restore Defaults** button are canceled. The layout of the ribbon on the page is reset to the default configuration for your profile. For more information, see [How to: Cancel UI Personalization](../SetupAndAdministration/how-to-cancel-ui-personalization.md).  
  
## See Also  
 [Ribbon](../GettingStarted/ribbon.md)   
 [Personalize the User Interface](../SetupAndAdministration/-$-s_personalization-personalize-the-user-interface-$-.md)   
 [How to: Define Promoted Action Categories Captions for the Ribbon](../Topic/How%20to:%20Define%20Promoted%20Action%20Categories%20Captions%20for%20the%20Ribbon.md)   
 [Troubleshooting: Removing Promoted Actions in Home Tab](../TroubleshootingUsingMicrosoftDynamicsNav/troubleshooting-removing-promoted-actions-in-home-tab.md)   
 [How to: Customize FastTabs](../SetupAndAdministration/how-to-customize-fasttabs.md)   
 [How to: Customize FactBoxes](../SetupAndAdministration/how-to-customize-factboxes.md)   
 [How to: Cancel UI Personalization](../SetupAndAdministration/how-to-cancel-ui-personalization.md)   
 [Delete User Personalization](../Topic/\($%20N_9191%20Delete%20User%20Personalization%20$\).md)   
 [Customize the User Interface](../SetupAndAdministration/customize-the-user-interface.md)   
 [Working with Product Name](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)   
 [Learn About the RoleTailored Design](../GettingStarted/learn-about-the-roletailored-design.md)