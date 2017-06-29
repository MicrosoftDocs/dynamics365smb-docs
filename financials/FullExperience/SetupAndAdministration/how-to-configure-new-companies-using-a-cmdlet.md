---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Configure New Companies using a Cmdlet
In a number of scenarios, you may want to load and import a configuration package without involving your users or using the FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[rim](../Roles/includes/rim_md.md)] --> --> user interface. You can do so by using a FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> Windows PowerShell cmdlet. Scenarios where this may be useful include:  
  
-   Performing data import across multiple [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] installations without opening each of installation manually.  
  
-   Configuring additional application areas for multiple customers.  
  
### To deploy a configuration package using a cmdlet  
  
1.  Prepare a [!INCLUDE[rim](../Roles/includes/rim_md.md)] package. For example, you can create a package to import certain values and the names of the table and the fields to insert these values into.  
  
2.  Place the package on a computer where you will run the cmdlet.  
  
3.  Open the FIX INCLUDE HERE<!--[!INCLUDE[nav_shell](../SetupAndAdministration/includes/nav_shell_md.md)] -->.  
  
4.  Enter **Invoke-NAVCodeUnit**, and specify information similar to the following example.  
  
    ```  
    Invoke-NAVCodeunit -Tenant Default -CompanyName "CRONUS International Ltd." -CodeunitId 8620 -MethodName ImportRapidStartPackage -Argument "C:\TEMP\RS_CONFIG.rapidstart" -ServerInstance DynamicsNAV71  
  
    ```  
  
     The cmdlet imports the package into each company.  
  
 Users can start to use the new functionality immediately.  
  
## See Also  
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](../Topic/Microsoft%20Dynamics%20NAV%20Windows%20PowerShell%20Cmdlets.md)   
 [How to: Configure New Companies](../SetupAndAdministration/how-to-configure-new-companies.md)