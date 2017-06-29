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
# How to: Create a New Company
To use ADD INCLUDE<!--[!INCLUDE[rimlong](../SetupAndAdministration/includes/rimlong_md.md)]-->, you first create a new company for which you want to perform a ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> implementation. When you create a new company, the standard ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> tables and pages are created, but there is no data in them.  
  
 In addition, you can apply specific setup data to your company after you initialize it. The information is provided in a configuration package, a .rapidstart file, which delivers content in a compressed format.  
  
 Example configuration packages, including country\/region-specific files, are included with the ADD INCLUDE<!--[!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)]-->. Use the following procedures to use the example configuration package with a new company.  
  
### To use the example BASICCONFIG configuration package  
  
1.  Open ADD INCLUDE<!--[!INCLUDE[demoname](../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/includes/demoname_md.md)]-->  
  
2.  In the **Search** box, enter **Configuration Packages**, and then choose the related link.  
  
3.  Choose the BASICCONFIG package from the list, and on the **Home** tab, in the **Process** group, choose **Export Package**.  
  
 Use the following procedure to create a new company, and use the BASICCONFIG package as part of the process.  
  
### To create a new company  
  
1.  Create a new company. For more information, see [How to: Create Companies](../Topic/How%20to:%20Create%20Companies.md) and information on the <xref:Microsoft.Dynamics.Nav.Management.Cmdlets.New-NAVCompany> cmdlet.  
  
2.  Switch to the ADD INCLUDE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)]--> and initialize the company you have just created. For more information, see [\($ S\_COMPANY How to: Select a Company $\)](../WorkingWithDynamics/-$-s_company-how-to-select-a-company-$-.md).  
  
3.  Restart the ADD INCLUDE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)]--> to refresh your Role Center display.  
  
 You can now import the configuration package that you exported from ADD INCLUDE<!--[!INCLUDE[demo](../ApplicationDesign/includes/demo_md.md)]-->. An easy way to do this is to use the ADD INCLUDE<!--[!INCLUDE[rim](../Roles/includes/rim_md.md)]--> wizard. For more information, see [How to: Configure a Company with the RapidStart Wizard](../SetupAndAdministration/how-to-configure-a-company-with-the-rapidstart-wizard.md). In addition, you can also configure a new company manually. For more information, see [How to: Configure New Companies](../SetupAndAdministration/how-to-configure-new-companies.md).  
  
 After you create a new company, some tables are automatically filled in, even if no company template is applied. For example, you can review the standard codes for posting and batch transactions in the **Source Code** window. If you provide a local version of ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->, you should review this table and consider any local language issues.  
  
## See Also  
 Source Code Setup