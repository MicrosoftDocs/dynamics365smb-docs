---
    title: Modify Permission Sets with Default Permissions Using RapidStart Services | Microsoft Docs
    description: When a user creates a new database, that user is assigned only one permission set automatically, the SUPER permission set.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/06/2018
    ms.author: sgroespe

---
# Modify Permission Sets with Default Permissions Using RapidStart Services
When a user creates a new database, that user is assigned only one permission set automatically: the SUPER permission set. As you create and define permission sets in a new database and companies, remember to always assign the BASIC permission set, which grants users access to required system tables and other fundamental tables, to all users. For more information, see [Manage Users and Permissions](ui-how-users-permissions.md).

The Essential BASIC permission set primarily functions as a prerequisite to open the client and show all pages.  

The BASIC permission set and permissions, as well as other permission sets, are provided in an XML file, examples of which are included with the [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you want to extend them with new permission sets or permissions, you can modify them.  

## To modify a permission set with default permissions using RapidStart Services  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Packages**, and then choose the related link.  
2. Choose the **New** action to create a new package.  
3. Enter a appropriate values in the **Package Code** and **Description** fields.  
4. On the **Tables** lines, add the following tables.  

    |Table Name|Table Number|  
    |----------------|------------------|  
    |Permission Set|2000000004|  
    |Permission|2000000005|  

5. Select both lines, and then, on the **Tables** tab, choose the **Excel** action, and then choose the **Export to Excel** action.  
6. Navigate to the RapidStart Services package, and choose the **Open** button.  

    The package contains all permission sets, including the Basic permission set. You can modify the permission settings in Excel.

7. On the **Tables** tab, , choose the **Excel** action, and then choose the **Import from Excel** action.  
8. In the configuration packages list, select the .xlsx file.  
9. Choose the **Apply Package** action.  

You can also modify permission sets directly in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Manage Users and Permissions](ui-how-users-permissions.md).

## See Also
[Set Up Company Configuration](admin-set-up-company-configuration.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
