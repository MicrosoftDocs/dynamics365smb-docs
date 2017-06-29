---
title: "Removing Elements from the User Interface According to Permissions"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 1104b836-a557-47ee-a6c6-4c19d3469fcc
caps.latest.revision: 11
ms.author: "sgroespe"
---
# Removing Elements from the User Interface According to Permissions
You can configure FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] --> --> --> to show and hide user interface \(UI\) elements based on the license or the user's permissions to the underlying tables. All elements, fields, actions, and page parts, can be removed from the user’s view of [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)].  
  
 Depending on the setting in the **UI Elements Removal** field in the FIX INCLUDE HERE<!--[!INCLUDE[nav_admin](../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)] -->, only UI elements on objects in the license or on objects that the user has permissions to will appear in the user interface.  
  
 UI elements that are directly related to an object through the **TableRelation** or the **CalcFormula** property can be removed automatically according to the license file and\/or user permissions.  
  
 For UI elements that are not directly related to an object, you can use the **AccessByPermission** property to remove the element according to the user’s permission to a related object.  
  
 To make full use of the **LicenseFileAndUserPermissions** option in the **UI Elements Removal** field, it is recommended that you assign the special permission set, FOUNDATION, along with the relevant permission sets that define which application objects the user will access.  
  
> [!IMPORTANT]  
>  The majority of the permission sets that are provided with the FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[demo](../ApplicationDesign/includes/demo_md.md)] --> --> demonstration database cannot be combined with the FOUNDATION permission set to fully use the UI Elements Removal feature. You must first create or edit the relevant permission sets to avoid that the user is blocked from performing the involved tasks.  
>   
>  If you only use the **LicenseFile** option in the **UI Elements Removal** field, then you do not have to edit any permission sets as they will not affect which UI elements are removed.  
  
 A couple of permission sets in the [!INCLUDE[demo](../ApplicationDesign/includes/demo_md.md)] demonstration database are adapted to support the FOUNDATION permission set for demonstration purposes. You can use those permission sets to try out how UI elements are removed for a user performing the task to create and edit a new customer.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Configure FIX INCLUDE HERE<!--[!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] --> to automatically remove UI elements from the user’s interface if they are on objects that are not in the license or on objects that the user does not have permissions for.|[How to: Specify When UI Elements Are Removed](../Topic/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md)|  
|Use the **AccessByPermission** property to define which user permissions to a certain object are required before the user can see and access the UI element. This method can be used to remove UI elements without a direct object relation from the user’s interface based on permissions.|[How to: Remove UI Elements Using the AccessByPermission Property](../Topic/How%20to:%20Remove%20UI%20Elements%20Using%20the%20AccessByPermission%20Property.md)|  
|To experience how UI elements are removed for a user performing the task to create and edit a new customer, create a sample user interface based on two permission sets that are provided with [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)].|[How to: Try Out the UI Elements Removal Feature Based on Demonstration Permission Sets](../Topic/How%20to:%20Try%20Out%20the%20UI%20Elements%20Removal%20Feature%20Based%20on%20Demonstration%20Permission%20Sets.md)|  
|Learn about FOUNDATION and other special permission sets.|[Special Permission Sets](../Topic/Special%20Permission%20Sets.md)|  
|Modify the existing permission sets to fully support the FOUNDATION permission set.|[How to: Create or Modify Permission Sets](../Topic/How%20to:%20Create%20or%20Modify%20Permission%20Sets.md)|  
  
## See Also  
 [Configuring Microsoft Dynamics NAV](../Topic/Configuring%20Microsoft%20Dynamics%20NAV.md)   
 [Customize the User Interface](../SetupAndAdministration/customize-the-user-interface.md)