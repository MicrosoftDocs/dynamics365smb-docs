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
To use RapidStart Services tables and pages are created, but there is no data in them.  

 In addition, you can apply specific setup data to your company after you initialize it. The information is provided in a configuration package, a .rapidstart file, which delivers content in a compressed format.  

 Example configuration packages, including country/region-specific files, are included with the ADD INCLUDE<!--[!INCLUDE[demolong](../../includes/demolong_md.md)]-->. Use the following procedures to use the example configuration package with a new company.  

### To use the example BASICCONFIG configuration package  

1.  Open ADD INCLUDE<!--[!INCLUDE[demoname](../../includes/demoname_md.md)]-->  

2.  In the **Search** box, enter **Configuration Packages**, and then choose the related link.  

3.  Choose the BASICCONFIG package from the list, and on the **Home** tab, in the **Process** group, choose **Export Package**.  

 Use the following procedure to create a new company, and use the BASICCONFIG package as part of the process.  

### To create a new company  

1.  Create a new company. For more information, see [How to: Create Companies](../How%20to:%20Create%20Companies.md) and information on the <xref:Microsoft.Dynamics.Nav.Management.Cmdlets.New-NAVCompany> cmdlet.  

2.  Switch to the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/-$-s_company-how-to-select-a-company-$-.md).  

3.  Restart the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> to refresh your Role Center display.  

 You can now import the configuration package that you exported from ADD INCLUDE<!--[!INCLUDE[demo](../../includes/how-to-configure-new-companies.md).  

 After you create a new company, some tables are automatically filled in, even if no company template is applied. For example, you can review the standard codes for posting and batch transactions in the **Source Code** window. If you provide a local version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you should review this table and consider any local language issues.  

## See Also  
 Source Code Setup
