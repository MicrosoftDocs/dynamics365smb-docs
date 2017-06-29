---
title: "How to: Work with the BASIC Permission Set"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "BASIC permission set, importing"
  - "permission sets, BASIC"
ms.assetid: 7cb71f04-d703-44c4-8f39-6b8d99c2d649
caps.latest.revision: 35
ms.author: "jswymer"
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
# How to: Work with the BASIC Permission Set
When a user creates a new database, that user is assigned only one permission set automatically: the SUPER permission set. As you create and define permission sets in a new database and companies, remember to always assign the BASIC permission set, which grants users access to required system tables and other fundamental tables, to all users.  
  
 The BASIC permission set primarily functions as a prerequisite to open the client and show all pages.  
  
 The BASIC permission set and permissions, as well as other permission sets, are provided in an XML file, examples of which are included with the [!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)]. If you want to extend them with new permission sets or permissions, you can modify them.  
  
> [!NOTE]  
>  Another prerequisite permission set is the FOUNDATION permission set.  
>   
>  If you want to use the UI Elements Removal feature to automatically remove UI elements according to user permissions, it is recommended that you use the FOUNDATION permission set together with the relevant application permission sets. For more information, see [Removing Elements from the User Interface According to Permissions](../SetupAndAdministration/removing-elements-from-the-user-interface-according-to-permissions.md).  
  
## Modifying the BASIC Permission Set with Default Permissions  
 Before beginning the following procedure, you have to install [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] and include [!INCLUDE[demo](../ApplicationDesign/includes/demo_md.md)].  
  
#### To modify permission sets with default permissions using [!INCLUDE[rim](../Roles/includes/rim_md.md)]  
  
1.  In the **Search** box, enter **Configuration Packages**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Manage** group, choose **New** to create a new package.  
  
3.  Enter a appropriate values in the **Package Code** and **Description** fields.  
  
4.  On the **Tables** lines, add the following tables.  
  
    |Table name|Table number|  
    |----------------|------------------|  
    |Permission Set|2000000004|  
    |Permission|2000000005|  
  
5.  Select both lines, and on the **Tables** toolbar, choose **Excel**, and then choose **Export to Excel**.  
  
6.  Navigate to the [!INCLUDE[rim](../Roles/includes/rim_md.md)] package. Choose **Open**.  
  
     The package contains all permission sets, including the Basic permission set. You can modify the permission settings in Excel. Save your changes.  
  
7.  On the **Tables** toolbar, choose **Excel**, and then choose **Import from Excel**.  
  
8.  In the configuration packages list, select the .xlsx file.  
  
9. On the **Home** tab, in the **Process** group, choose **Apply Package**.  
  
 You can also modify permission sets directly in the [!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)]. For more information, see [How to: Create or Modify Permission Sets](../Topic/How%20to:%20Create%20or%20Modify%20Permission%20Sets.md). In addition, if you are upgrading from an earlier version of [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)], you can upgrade permissions and roles as part of the upgrade process. For more information, see [Upgrading Data Common to All Companies](../Topic/Upgrading%20Data%20Common%20to%20All%20Companies.md).  
  
> [!NOTE]  
>  Depending on the setting in the **UI Elements Removal** field in the [!INCLUDE[nav_admin](../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)], only UI elements that the user has permissions for will appear in the user interface. For more information, see [How to: Specify When UI Elements Are Removed](../Topic/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md).  
  
## See Also  
 [Security Overview](../Topic/Security%20Overview.md)   
 [Managing Permissions and Permission Sets](../Topic/Managing%20Permissions%20and%20Permission%20Sets.md)   
 [How to: Create or Modify Permission Sets](../Topic/How%20to:%20Create%20or%20Modify%20Permission%20Sets.md)   
 [Customize the User Interface](../SetupAndAdministration/customize-the-user-interface.md)   
 [Removing Elements from the User Interface According to Permissions](../SetupAndAdministration/removing-elements-from-the-user-interface-according-to-permissions.md)