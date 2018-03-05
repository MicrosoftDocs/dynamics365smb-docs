---
    title: How to Configure New Companies using a Cmdlet | Microsoft Docs
    description: In a number of scenarios, you may want to load and import a configuration package without involving your users or using the RapidStart Services user interface. You can do so by using a Windows PowerShell cmdlet. Scenarios where this may be useful include:
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
# Configure New Companies using a Cmdlet
In a number of scenarios, you may want to load and import a configuration package without involving your users or using the RapidStart Services user interface. You can do so by using a Windows PowerShell cmdlet. Scenarios where this may be useful include:  

-   Performing data import across multiple [!INCLUDE[d365fin](includes/d365fin_md.md)] installations without opening each of installation manually.  

-   Configuring additional application areas for multiple customers.  

### To deploy a configuration package using a cmdlet  

1.  Prepare a RapidStart Services package. For example, you can create a package to import certain values and the names of the table and the fields to insert these values into.  

2.  Place the package on a computer where you will run the cmdlet.  

3.  Open the [!INCLUDE[d365fin](includes/d365fin_md.md)] administration shell.  

4.  Enter **Invoke-NAVCodeUnit**, and specify information similar to the following example.  

    ```  
    Invoke-NAVCodeunit -Tenant Default -CompanyName "CRONUS International Ltd." -CodeunitId 8620 -MethodName ImportRapidStartPackage -Argument "C:TEMPRS_CONFIG.rapidstart" -ServerInstance DynamicsNAV71  

    ```  

     The cmdlet imports the package into each company.  

 Users can start to use the new functionality immediately.  

## See Also  
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets]
 [Configure New Companies](admin-how-to-configure-new-companies.md)
