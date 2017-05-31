---
title: "Configure the User Interface"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: b54955bc-6965-49d7-a555-18c4a541f786
caps.latest.revision: 15
ms.author: "solsen"
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
# Configure the User Interface
As an administrator, you configure the company’s default user interfaces by customizing page layouts for different user profiles in the company. To perform this work, you must be an administrator with the SUPER permission set. In addition, profiles must be set up and the appropriate users assigned to them. For more information, see [Administration in the Clients](../SetupAndAdministration/administration-in-the-clients.md).  
  
 You configure the user interface for multiple users by customizing pages for a particular profile that the users are assigned to. You perform this UI customization in the **Customize** window after you have opened the [!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] in configuration mode. Your work in the **Customize** window is the same work that users perform when they personalize their own view of [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)]. Typical customizations include which actions to include on the ribbon, how fields are placed on FastTabs or in FactBoxes, and which menu items to include in the navigation pane. For more information, see [\($ S\_PERSONALIZATION Personalize the User Interface $\)](../SetupAndAdministration/-$-s_personalization-personalize-the-user-interface-$-.md).  
  
> [!NOTE]  
>  When you make new UI configuration for a page that a user has personalized, the user’s UI personalization is preserved, and is not overwritten by the new page configuration. Likewise, when you cancel your UI configuration of a page that a user has since personalized, the user’s UI personalization is not canceled.  
>   
>  The only situation where UI configuration does overwrite UI personalization is when a UI element is removed by configuration. For example, if the administrator removes a field that the user has renamed or moved, then the field is still removed from the user’s user interface.  
  
 You can record UI customizations of the same page based on different access points to the page. For example, the **Sales Orders** window can be customized to look different when opened from the **Customer Card** window than when opened from the **Sales Order Processor** Role Center. The point from which you access the page to be customized is recorded in that specific page customization. Accordingly, there may be multiple page customization records in the database, as you can be seen in the **\($ N\_9190 Delete Profile Configuration $\)** window.  
  
 Before you begin to customize user interfaces, you can specify on the [!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] that UI elements that users do not have permissions for are removed from their user interface, including from the lists of UI elements in the **Customize** window.  
  
> [!TIP]  
>  To see the effect of the initial UI customization that is provided with the **UI Elements Removal** option, you can log on as a test user with the permission set of the profile you are configuring. The reason is that you as the administrator have the SUPER permission set, and you can therefore not see and test the resulting user interface during your own logon. For more information, see [Walkthrough: Configuring UI for the Order Processor Profile](../SetupAndAdministration/walkthrough-configuring-ui-for-the-order-processor-profile.md).  
  
> [!NOTE]  
>  Unlike when users change the size of windows or the width of columns on their own computer, any such basic view changes that you make during your configuration of the UI for a profile are not saved to the profile and will not be available for users assigned to the profile. Basic view changes are computer\-specific. For more information, see [How to: Make Basic UI Changes](../SetupAndAdministration/how-to-make-basic-ui-changes.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Configure [!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] to remove UI elements when the related object is not accessible according to the license or according to user permissions or both.|[Removing Elements from the User Interface According to Permissions](../SetupAndAdministration/removing-elements-from-the-user-interface-according-to-permissions.md)|  
|Prepare to customize the user interface for a profile by opening the [!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] in configuration mode.|[How to: Open Microsoft Dynamics NAV in Configuration Mode](../SetupAndAdministration/how-to-open-microsoft-dynamics-nav-in-configuration-mode.md)|  
|Customize the user interface for a profile by changing which actions, fields, and page parts to show, how filter buttons are displayed, and how the navigation pane is structured. You use the same functions in the **Customize** window that users use to personalize their own user interface.|[\($ S\_PERSONALIZATION Personalize the User Interface $\)](../SetupAndAdministration/-$-s_personalization-personalize-the-user-interface-$-.md)|  
|Cancel UI customization that you have made as configuration for a profile in either of three ways.|[How to: Cancel UI Configuration](../SetupAndAdministration/how-to-cancel-ui-configuration.md)|  
|Export the UI configuration for a profile so that it can be imported into another [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] database.|[How to: Export or Import Profiles](../SetupAndAdministration/how-to-export-or-import-profiles.md)|  
|Follow an end\-to\-end procedure to learn how to ensure that disallowed UI elements are removed and that you can test the order processor’s user interface. Then, learn how to open you [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] in configuration mode, customize two different UI areas on the Sales Orders page when accessed from certain points, cancel a specific UI customization, and then export a configuration file for the profile.|[Walkthrough: Configuring UI for the Order Processor Profile](../SetupAndAdministration/walkthrough-configuring-ui-for-the-order-processor-profile.md)|  
  
## See Also  
 [Customize the User Interface](../SetupAndAdministration/customize-the-user-interface.md)   
 [Customization: Configuration and Personalization](http://msdn.microsoft.com/en-us/library/jj677170\(v=nav.70\).aspx)   
 [Administration in the Clients](../SetupAndAdministration/administration-in-the-clients.md)   
 [Working with \($ P\_1 Product Name $\)](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)