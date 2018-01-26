---
    title: How to Open Microsoft Dynamics NAV in Configuration Mode | Microsoft Docs
    description: To configure a profile, for example to customize the profile’s user interface, you must open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> in configuration mode.
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
# Open Microsoft Dynamics NAV in Configuration Mode
To configure a profile, for example to customize the profile’s user interface, you must open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> in configuration mode.  
  
### To open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> in configuration mode  
  
1.  At the command prompt, navigate to the root folder of the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]-->. For example:  
  
    ```  
    cd navnow_x86installRoleTailored Client  
    ```  
  
2.  Type the following command:  
  
    ```  
    Microsoft.Dynamics.Nav.Client.exe -configure -profile:"profileid"  
    ```  
  
     Replace **profileid** with the name of the profile that you want to configure.  
  
     For example, to configure the Accounting Manager profile, use this command to open the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> in configuration mode:  
  
    ```  
    Microsoft.Dynamics.Nav.Client.exe -configure -profile:"Accounting Manager"  
    ```  
  
## See Also  
 [Configure the User Interface](../configure-the-user-interface.md)   
 [Create a Profile](../how-to-create-a-profile.md)   
 [Assign a User to a Profile](../how-to-assign-a-user-to-a-profile.md)