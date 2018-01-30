---
    title: How to Cancel UI Configuration | Microsoft Docs
    description: You can cancel UI customizations that you have made as configuration for a profile in three ways:
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
# Cancel UI Configuration
You can cancel UI customizations that you have made as configuration for a profile in three ways:  

-   Cancel all UI customization that you have made for a profile by using the **Clear Configured Pages** button in the **Profile Card** window.  
-   Cancel UI customization that you have made for specific pages for a profile by deleting rows in the **Delete Profile Configuration** window.  
-   Cancel UI customization that you have made for a specific UI area for a specific page for a profile by using the **Restore Defaults** button in the **Customize** window.

> [!IMPORTANT]  
>  Users can make UI customizations under their own user logon to personalize their user interface. When you cancel your UI configuration of a page that a user has since personalized, the user’s UI personalization is not canceled. Likewise, when you make new UI configuration for a page that a user has personalized, the user’s UI personalization is preserved, and is not overwritten by the new page configuration.  
>   
>  The only situation where UI configuration does overwrite UI personalization is when a UI element is removed by configuration. For example, if the administrator removes a field that the user has renamed or moved, then the field is still removed from the user’s UI.  

> [!NOTE]  
>  In the **Delete User Personalization** window and with the **Restore Defaults** button in the **Customize** window, users can cancel UI customization that they have made to pages under their own user logon. When they do so, the layout of those pages is reset to any UI customization that the administrator has configured for the profile. If the profile has not been configured, then the layout of the user’s pages is reset to the profile configuration that was installed with ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-cancel-ui-personalization.md).

## To cancel all UI customization that you have made for a profile  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Profiles**, and then choose the related link.  
2.  Select the profile for which you want to cancel all UI customizations, and then choose the **Edit** action.  
3.  In the **Profile Card** window, choose the **Clear Configured Pages** action.  

> [!NOTE]  
>  All UI customizations for the profile, both those installed with [!INCLUDE[d365fin](includes/d365fin_md.md)] and those made by the administrator, are canceled. No page layouts specific to the profile remain in the database.  

## To cancel UI customization that you have made for specific page for a profile  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Delete Profile Configuration**, and then choose the related link.  
2.  Select the profile/page set for which you want to cancel your UI customization, and then choose the **Delete** action.  

    > [!CAUTION]  
    >  If you have configured different UI customizations of the same page based on different navigation paths to the page, then each page customization will be listed in the **Delete Profile Configuration** window with the same information. There is no information to identify which row relates to which navigation path. Therefore, you must either delete rows one by one followed by visual checks on the page, or you can delete all rows with UI customizations for the profile/page.  

> [!NOTE]  
>  All UI customization for the page for the profile that you have ever made on the installation or since you last used the **Delete Profile Configuration** window is canceled. The layout of the page is reset to the standard layout of the page object, which is not RoleTailored.  

## To cancel UI customization that you have made for a specific UI area for a specific page for a profile  

1.  You can undo changes for that you have made to individual UI areas, such as a ribbon, by using the **Restore Defaults** button in the **Customize** window. Alternatively, you can undo all UI changes that you have made for a profile by using the **Delete Profile Configuration** window.  

The UI customization for the profile of the particular UI area on the particular page is canceled. The layout of the UI area on the page is reset to the default configuration, as made either by the administrator or as installed with [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## See Also  
 [Configure the User Interface](../configure-the-user-interface.md)   
 PERSONALIZATION Personalize the User Interface   
 Delete Profile Configuration   
 [Cancel UI Personalization](../how-to-cancel-ui-personalization.md)   
 Delete User Personalization   
 [Disable Personalization](../how-to-disable-personalization.md)   
 [Customize the User Interface](../customize-the-user-interface.md)   
 [Manage Profiles](../manage-profiles.md)
