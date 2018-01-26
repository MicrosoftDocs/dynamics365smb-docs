---
    title: Configure the User Interface | Microsoft Docs
    description: As an administrator, you configure the company’s default user interfaces by customizing page layouts for different user profiles in the company. To perform this work, you must be an administrator with the SUPER permission set. In addition, profiles must be set up and the appropriate users assigned to them. For more information, see [Administration in the Clients](../administration-in-the-clients.md).
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
# Configure the User Interface
As an administrator, you configure the company’s default user interfaces by customizing page layouts for different user profiles in the company. To perform this work, you must be an administrator with the SUPER permission set. In addition, profiles must be set up and the appropriate users assigned to them. For more information, see [Administration in the Clients](../administration-in-the-clients.md).  
  
 You configure the user interface for multiple users by customizing pages for a particular profile that the users are assigned to. You perform this UI customization in the **Customize** window after you have opened the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/dyn_nav_md.md)]-->. Typical customizations include which actions to include on the ribbon, how fields are placed on FastTabs or in FactBoxes, and which menu items to include in the navigation pane. For more information, see PERSONALIZATION Personalize the User Interface.  
  
> [!NOTE]  
>  When you make new UI configuration for a page that a user has personalized, the user’s UI personalization is preserved, and is not overwritten by the new page configuration. Likewise, when you cancel your UI configuration of a page that a user has since personalized, the user’s UI personalization is not canceled.  
>   
>  The only situation where UI configuration does overwrite UI personalization is when a UI element is removed by configuration. For example, if the administrator removes a field that the user has renamed or moved, then the field is still removed from the user’s user interface.  
  
 You can record UI customizations of the same page based on different access points to the page. For example, the **Sales Orders** window can be customized to look different when opened from the **Customer Card** window than when opened from the **Sales Order Processor** Role Center. The point from which you access the page to be customized is recorded in that specific page customization. Accordingly, there may be multiple page customization records in the database, as you can be seen in the **Delete Profile Configuration** window.  
  
 Before you begin to customize user interfaces, you can specify on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> that UI elements that users do not have permissions for are removed from their user interface, including from the lists of UI elements in the **Customize** window.  
  
> [!TIP]  
>  To see the effect of the initial UI customization that is provided with the **UI Elements Removal** option, you can log on as a test user with the permission set of the profile you are configuring. The reason is that you as the administrator have the SUPER permission set, and you can therefore not see and test the resulting user interface during your own logon. For more information, see [Walkthrough: Configuring UI for the Order Processor Profile](../walkthrough-configuring-ui-for-the-order-processor-profile.md).  
  
> [!NOTE]  
>  Unlike when users change the size of windows or the width of columns on their own computer, any such basic view changes that you make during your configuration of the UI for a profile are not saved to the profile and will not be available for users assigned to the profile. Basic view changes are computer-specific. For more information, see [Make Basic UI Changes](../how-to-make-basic-ui-changes.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Configure ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/removing-elements-from-the-user-interface-according-to-permissions.md)|  
|Prepare to customize the user interface for a profile by opening the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/how-to-open-microsoft-dynamics-nav-in-configuration-mode.md)|  
|Customize the user interface for a profile by changing which actions, fields, and page parts to show, how filter buttons are displayed, and how the navigation pane is structured. You use the same functions in the **Customize** window that users use to personalize their own user interface.|PERSONALIZATION Personalize the User Interface|  
|Cancel UI customization that you have made as configuration for a profile in either of three ways.|[Cancel UI Configuration](../how-to-cancel-ui-configuration.md)|  
|Export the UI configuration for a profile so that it can be imported into another ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-export-or-import-profiles.md)|  
|Follow an end-to-end procedure to learn how to ensure that disallowed UI elements are removed and that you can test the order processor’s user interface. Then, learn how to open you ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/walkthrough-configuring-ui-for-the-order-processor-profile.md)|  
  
## See Also  
 [Customize the User Interface](../customize-the-user-interface.md)   
 [Customization: Configuration and Personalization](http://msdn.microsoft.com/en-us/library/jj677170(v=nav.70).aspx)   
 [Administration in the Clients](../administration-in-the-clients.md)   
 [Working with Product Name](../working-with-$-p_1-product-name-$-.md)