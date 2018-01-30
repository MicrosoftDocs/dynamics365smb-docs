---
    title: Removing Elements from the User Interface According to Permissions | Microsoft Docs
    description: You can configure [!INCLUDE[d365fin](includes/d365fin_md.md)].
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
# Removing Elements from the User Interface According to Permissions
You can configure [!INCLUDE[d365fin](includes/d365fin_md.md)].  
  
 Depending on the setting in the **UI Elements Removal** field in the ADD INCLUDE<!--[!INCLUDE[nav_admin](../../includes/nav_admin_md.md)]-->, only UI elements on objects in the license or on objects that the user has permissions to will appear in the user interface.  
  
 UI elements that are directly related to an object through the **TableRelation** or the **CalcFormula** property can be removed automatically according to the license file and/or user permissions.  
  
 For UI elements that are not directly related to an object, you can use the **AccessByPermission** property to remove the element according to the user’s permission to a related object.  
  
 To make full use of the **LicenseFileAndUserPermissions** option in the **UI Elements Removal** field, it is recommended that you assign the special permission set, FOUNDATION, along with the relevant permission sets that define which application objects the user will access.  
  
> [!IMPORTANT]  
>  The majority of the permission sets that are provided with the ADD INCLUDE<!--[!INCLUDE[demo](../../includes/demo_md.md)]--> demonstration database cannot be combined with the FOUNDATION permission set to fully use the UI Elements Removal feature. You must first create or edit the relevant permission sets to avoid that the user is blocked from performing the involved tasks.  
>   
>  If you only use the **LicenseFile** option in the **UI Elements Removal** field, then you do not have to edit any permission sets as they will not affect which UI elements are removed.  
  
 A couple of permission sets in the ADD INCLUDE<!--[!INCLUDE[demo](../../includes/demo_md.md)]--> demonstration database are adapted to support the FOUNDATION permission set for demonstration purposes. You can use those permission sets to try out how UI elements are removed for a user performing the task to create and edit a new customer.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Configure ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/How%20to:%20Specify%20When%20UI%20Elements%20Are%20Removed.md)|  
|Use the **AccessByPermission** property to define which user permissions to a certain object are required before the user can see and access the UI element. This method can be used to remove UI elements without a direct object relation from the user’s interface based on permissions.|[Remove UI Elements Using the AccessByPermission Property](../How%20to:%20Remove%20UI%20Elements%20Using%20the%20AccessByPermission%20Property.md)|  
|To experience how UI elements are removed for a user performing the task to create and edit a new customer, create a sample user interface based on two permission sets that are provided with ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/How%20to:%20Try%20Out%20the%20UI%20Elements%20Removal%20Feature%20Based%20on%20Demonstration%20Permission%20Sets.md)|  
|Learn about FOUNDATION and other special permission sets.|[Special Permission Sets](../Special%20Permission%20Sets.md)|  
|Modify the existing permission sets to fully support the FOUNDATION permission set.|[Create or Modify Permission Sets](../How%20to:%20Create%20or%20Modify%20Permission%20Sets.md)|  
  
## See Also  
 [Configuring Microsoft Dynamics NAV](../Configuring%20Microsoft%20Dynamics%20NAV.md)   
 [Customize the User Interface](../customize-the-user-interface.md)