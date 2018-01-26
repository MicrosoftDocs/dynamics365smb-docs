---
    title: Walkthrough - Configuring UI for the Order Processor Profile | Microsoft Docs
    description: Administrators configure the user interface by customizing the user interface for a single profile, such as the Order Processor profile, that multiple users are assigned to. To configure a profile, you must have the SUPER permission set. For more information, see [Administration in the Clients](../administration-in-the-clients.md).
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
# Walkthrough: Configuring UI for the Order Processor Profile
Administrators configure the user interface by customizing the user interface for a single profile, such as the Order Processor profile, that multiple users are assigned to. To configure a profile, you must have the SUPER permission set. For more information, see [Administration in the Clients](../administration-in-the-clients.md).  

 The functions that you use to customize the UI for a profile during configuration are the same that users use to customize their own UI during personalization. The main difference is that configuration applies to multiple users and can be managed by the administrator as a profile record.  

> [!NOTE]  
>  When you make new UI configuration for a page that a user has personalized, the user’s UI personalization is preserved, and is not overwritten by the new page configuration. Likewise, when you cancel your UI configuration of a page that a user has since personalized, the user’s UI personalization is not canceled.  
>   
>  The only situation where UI configuration does overwrite UI personalization is when a UI element is removed by configuration. For example, if the administrator removes a field that the user has renamed or moved, then the field is still removed from the user’s user interface.  

## About This Walkthrough  
 This walkthrough provides examples of how to configure the Order Processor profile in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The walkthrough illustrates the following tasks:  

-   Making sure order processors only see UI elements that they have permissions for  

-   Checking the user interface of a test user who has the Order Processor profile  

-   Opening [!INCLUDE[d365fin](includes/d365fin_md.md)] in configuration mode  

-   Customizing the Sales Orders ribbon for the Order Processor profile  

-   Customizing the Sales Orders FactBox pane for the Order Processor profile  

-   Cancelling UI customization for the Order Processor profile  

-   Reusing UI customization for the Order Processor profile in other databases  

 You perform configuration of other parts of the user interface, such as FastTabs and columns, just as described for ribbons and FactBoxes in this walkthrough. For more information, see PERSONALIZATION Personalize the User Interface.  

## Prerequisites  
 To complete this walkthrough, you will need:  

-   Microsoft Dynamics NAV 2013 or a later version of Microsoft Dynamics NAV  

-   The CRONUS International Ltd. demonstration database  

## Making Sure Order Processors Only See UI Elements that They Have Permissions for  
 You can configure Microsoft Dynamics NAV Server to remove UI elements when the related object is not accessible according to the license or according to user permissions or both.  

 Before you begin to customize the user interface, you should set the **UI Elements Removal** field in ADD INCLUDE<!--[!INCLUDE[nav_admin](../../includes/nav_admin_md.md)]--> to **LicenseFileAndUserPermissions**, so that users only see UI elements that they have permissions for.  

#### To make sure order processors only see UI elements that they have permissions for  

1.  Open the ADD INCLUDE<!--[!INCLUDE[nav_admin](../../includes/Microsoft%20Dynamics%20NAV%20Server%20Administration%20Tool.md).  

2.  In the **UI Elements Removal** field, make sure that the **LicenseFileAndUserPermissions** option is selected.  

 Users assigned to the Order Processor profile will now only see UI elements that are permitted according to the company license and permission set that is assigned to the profile.  

## Checking the User Interface of a Test User with the Order Processor profile  
 Because you are logged on with the SUPER permission set, you see all UI elements, and you can therefore not see the effect that the **UI Elements Removal** function has on the Order Processor profile. To understand which UI elements an order processor can see according to permissions, you can create a test user who has the same permissions as the Order Processor profile. This enables you to see which UI elements are relevant when you customize for the profile. Whenever you want to plan or test UI customization that you are making for the profile, you can log on as the test order processor.  

#### To check the user interface of a test user  

1.  Create a test user and assign the same permission set to the user who order processors in your company have. For more information, see [Create Microsoft Dynamics NAV Users](../How%20to:%20Create%20Microsoft%20Dynamics%20NAV%20Users.md).  

2.  Log on using the credentials of the test order processor.  

 You can now assess which UI elements are removed from an order processor’s user interface according to their permissions and the company license. And you can continuously log on as the order processor to see the result of your UI customization for the profile.  

## Opening Microsoft Dynamics NAV in Configuration Mode  
 You can open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/how-to-open-microsoft-dynamics-nav-in-configuration-mode.md).  

#### To open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> in configuration mode  

1.  Open a command prompt and change to the directory that contains the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/navnow_x86install_md.md)]-->RoleTailored Client  

    > [!NOTE]  
    >  The top-level directory may be **Program Files (x86)** or **Program Files**.  

2.  Open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> in configuration mode by typing the following command: **Microsoft.Dynamics.Nav.Client.exe -configure -profile:"order processor"**  

     The ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/how-to-open-microsoft-dynamics-nav-in-configuration-mode.md).  

## Customizing the Sales Orders Ribbon for the Order Processor Profile  
 The following procedure shows how to add the **Page Notes** action to the **Process** group on the ribbon on the **Sales Orders** page. This UI customization will be visible to order processors when they access the **Sales Orders** page from the **Sales Order - Open** tile on the **Sales Order Processor** Role Center.  

#### To add an action to the ribbon  

1.  Go to the **Sales Order Processor** Role Center.  

2.  Choose the **Sales Order - Open** tile.  

3.  In the **Sales Orders** window, on **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Customize Ribbon**.  

4.  In the **Available actions** list, expand **Help**, and then choose **Page Notes**. Alternatively, use the **Search** box above the list.  

5.  Under **Show actions in this order**, expand **Home**, choose **Manage**, and then choose the **Add** button to move **Page Notes** to the **Manage** group.  

6.  Choose the **Page Notes** action, and then choose **Move Up** or **Move Down** to position it appropriately I relation to other actions in the **Manage** group.  

7.  Choose the **OK** button to save and close the **Customize** window.  

 The **Page Notes** action is now visible to users assigned to the Order Processor profile when they access the **Sales Orders** window by choosing the **Sales Orders – Open** tile on their Role Center. For more information, see [Customize Ribbons](../how-to-customize-ribbons.md).  

> [!NOTE]  
>  In some cases, an action can be a promoted action if the **PromotedIsBig** property is set to **Yes** in the ADD INCLUDE<!--[!INCLUDE[nav_dev_long](../../includes/How%20to:%20Promote%20Actions%20on%20Pages.md).  

## Customizing a Sales Orders FactBox Pane for the Order Processor Profile  
 The following procedure shows how to add the **Notes** FactBox to the FactBox pane on the **Sales Orders** page. This UI customization will be visible to order processors when they access the **Sales Orders** page from the **Customer Card** window.  

#### To add the Links FactBox to a FactBox pane  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  

2.  Select a customer, and then, on the **Navigate** tab, in the **Documents** group, choose **Orders**.  

3.  In the **Sales Orders** window, on the **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Choose FactBoxes**.  

4.  From the **Available FactBoxes** pane, select **Notes**, and then choose the **Add** button.  

5.  Choose the **OK** button to save and close the **Customize** window.  

 The **Notes** FactBox is now visible to users assigned to the Order Processor profile when they access the **Sales Orders** window by choosing the Orders actions in a **Customer Card** window. For more information, see [Customize FactBoxes](../how-to-customize-factboxes.md).  

## Cancelling UI Customization for the Order Processor Profile  
 You can cancel UI customization for profiles in three ways. For more information, see [Cancel UI Configuration](../how-to-cancel-ui-configuration.md).  

 The following procedure shows how to cancel only the specific UI customization that you made for the **Sales Orders** page when it is accessed from the **Sales Orders – Open** tile on the Role Center.  

#### To cancel a specific UI customization for a profile  

1.  Go to the **Sales Order Processor** Role Center.  

2.  Choose the **Sales Order - Open** tile.  

3.  In the **Sales Orders** window, on **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Restore Defaults**.  

4.  Choose the **OK** button to save and close the **Customize** window.  

 The UI customization that you made in a previous procedure to show the **Manage Notes** action in the **Sale Orders** window when it is accessed from the **Sales Orders – Open** tile on the Role Center is now canceled.  

## Reusing UI Customization for the Order Processor Profile in Other Databases  
 You can export a profile, for example to reuse the UI configuration by importing the profile into another [!INCLUDE[d365fin](includes/d365fin_md.md)] database.  

> [!NOTE]  
>  ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> must be in configuration mode, otherwise the exported XML file will be empty.  

#### To export a profile  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export Profiles**, and then choose the related link.  

2.  In the **Export Profiles** window, on the **Profile** FastTab, enter **Order Processor** as a filter value for profile ID, and then choose **OK**.  

3.  Name the XML file **New Order Processor.xml** and save it in an appropriate location.  

#### To import a profile  

1.  Logon to a database where you want to implement the Order Processor profile that you have configured in the previous procedures.  

2.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Import Profiles**, and then choose the related link.  

3.  In the **Import from XML File** window, select the profile that you want to import.  

    > [!NOTE]  
    >  If the database already contains an Order Processor profile, then you must first delete that profile. For more information, see [Manage Profiles](../manage-profiles.md).  

4.  Choose the **OK** button to import the new profile.  

 The UI customization that you have configured for the Order Processor profile in another database is now available in this database.  

## Next Steps  
 In this walkthrough, you have configured the user interface for the Order Processor profile and prepared to reuse the configuration in another database. All users assigned to the profile see these changes. If you want users to have even more customized user interfaces, you can urge them to make their own UI customization in addition to the customization that you have made. For more information, PERSONALIZATION Personalize the User Interface.  

## See Also  
 [Customize the User Interface](../customize-the-user-interface.md)   
 [Administration in the Clients](../administration-in-the-clients.md)
