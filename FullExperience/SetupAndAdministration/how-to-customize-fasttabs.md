---
title: "How to: Customize FastTabs"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "removing, fields"
  - "fields, hiding"
  - "FastTabs, collapsing"
  - "adding, FastTabs"
  - "customizing, FastTabs"
  - "FastTabs, customizing"
  - "restoring defaults"
  - "adding, fields"
  - "show fields"
  - "FastTabs, adding"
  - "fields, removing"
  - "collapsed FastTabs"
  - "removing, FastTabs"
  - "fields, showing"
  - "fields, adding"
  - "FastTabs, removing"
  - "hiding, fields"
ms.assetid: 262f3ee0-7041-4456-a680-5d66f665058a
caps.latest.revision: 22
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
# How to: Customize FastTabs
FastTabs help organize information about pages into simple, manageable groups. You can customize FastTabs on pages so that they support your workflow. For example, you may want to show fewer FastTabs or hide specific fields on FastTabs. You can also promote the most important fields to be included in the FastTab headers when the FastTabs are collapsed.  
  
 You can peform the following tasks to customize FastTabs on pages:  
  
-   Add or remove FastTabs.  
  
-   Add or remove fields from FastTabs.  
  
-   Show fields on collapsed FastTab headers.  
  
-   Hide fields on FastTabs.  
  
> [!NOTE]  
>  Depending on the setting in the **UI Elements Removal** field in the [!INCLUDE[nav_admin](../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)], only FastTabs and fields that you have permissions for will appear in the **Customize** window. For more information, see [How to: Specify When UI Elements Are Removed](../Topic/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md).  
  
 You can make multiple customizations of the same page based on different access points to the page. For example, you can customize that FastTabs in the **Sales Orders** window look different when the window is opened from the **Customer Card** window than when it is opened from your Role Center. The point from which you access the page to be customized is recorded in that specific page customization. Accordingly, there may be multiple customization records for the same page under your logon, as you can see in the **\($ N\_9191 Delete User Personalization $\)** window.  
  
### To start customizing a FastTab  
  
1.  On a page with FastTabs, on the **Application** menu ![Microsoft Dynamics NAV Application menu](../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/media/rtc_applicationmenu.png "RTC\_ApplicationMenu"), select **Customize**, and then choose **Customize This Page**.  
  
2.  In the **Customize \<Page Name\>** dialog box, choose **FastTabs**.  
  
### To add a FastTab to a page  
  
-   In the **Available FastTabs** box, choose the **Add** button.  
  
### To remove a FastTab from a page  
  
-   In the **Show FastTabs in this order** box, select the FastTab that you want to remove, and then choose the **Remove** button.  
  
### To add a field to a FastTab  
  
1.  In the **Show FastTabs in this order** box, select the FastTab that you want to change, and then choose **CustomizeFastTab**.  
  
2.  In the **Fields shown** field, select the field that you want to add, and then choose the **Add** button.  
  
### To remove a field from a FastTab  
  
1.  In the **Show FastTabs in this order** box, select the FastTab that you want to change, and then choose **Customize FastTab**.  
  
2.  In the **Fields shown** box, select the field that you want to remove, and then choose the **Remove** button.  
  
### To show a field in a collapsed FastTab header  
  
1.  In the **Show FastTabs in this order** box, select the FastTab that you want to change, and then choose **Customize FastTab**.  
  
2.  In the **Fields shown** box, select the field that you want to show in the collapsed FastTab header.  
  
3.  In the **Importance** list, select **Promoted**, and then choose the **OK** button.  
  
> [!NOTE]  
>  When you expand a FastTab, promoted fields are only shown in the FastTab and not in the header.  
  
### To hide a field on a FastTab  
  
1.  In the **Show FastTabs in this order** box, select the FastTab that you want to change, and then choose **Customize FastTab**.  
  
2.  In the **Fields shown** box, select the field that you want to hide by default.  
  
3.  In the **Importance** list, choose **Additional**, and then choose the **OK** button.  
  
> [!NOTE]  
>  To view additional fields on a FastTab, expand the FastTab, and then choose **Show more fields**.  
  
### To mark a field as a Quick Entry field  
  
1.  In the **Show FastTabs in this order** box, select the FastTab that you want to change, and then choose **Customize FastTab**.  
  
2.  In the **Fields shown** box, select the field that you want to mark as a Quick Entry field.  
  
3.  Select the **Quick Entry** check box.  
  
 Using the Enter key, the pointer jumps to the next field set to be a Quick Entry field.  
  
### To restore default settings  
  
-   In the Customize window, choose the **Restore Defaults** button, and then choose the **OK** button.  
  
    > [!NOTE]  
    >  All customization of FastTabs that you have ever made for this page under your current user logon or since you last used the **Restore Defaults** button are canceled. The layout of FastTabs on the page is reset to the default configuration for your profile. For more information, see [How to: Cancel UI Personalization](../SetupAndAdministration/how-to-cancel-ui-personalization.md).  
  
## See Also  
 [\($ S\_PERSONALIZATION Personalize the User Interface $\)](../SetupAndAdministration/-$-s_personalization-personalize-the-user-interface-$-.md)   
 [How to: Customize Ribbons](../SetupAndAdministration/how-to-customize-ribbons.md)   
 [How to: Customize FactBoxes](../SetupAndAdministration/how-to-customize-factboxes.md)   
 [How to: Specify When UI Elements Are Removed](../Topic/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md)   
 [How to: Cancel UI Personalization](../SetupAndAdministration/how-to-cancel-ui-personalization.md)   
 [\($ N\_9191 Delete User Personalization $\)](../Topic/\($%20N_9191%20Delete%20User%20Personalization%20$\).md)   
 [Customize the User Interface](../SetupAndAdministration/customize-the-user-interface.md)   
 [Working with \($ P\_1 Product Name $\)](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)   
 [Learn About the RoleTailored Design](../GettingStarted/learn-about-the-roletailored-design.md)