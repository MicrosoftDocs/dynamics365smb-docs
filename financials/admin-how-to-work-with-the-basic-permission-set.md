---
    title: How to Work with the BASIC Permission Set | Microsoft Docs
    description: When a user creates a new database, that user is assigned only one permission set automatically.
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
# Work with the BASIC Permission Set
When a user creates a new database, that user is assigned only one permission set automatically: the SUPER permission set. As you create and define permission sets in a new database and companies, remember to always assign the BASIC permission set, which grants users access to required system tables and other fundamental tables, to all users.  

 The BASIC permission set primarily functions as a prerequisite to open the client and show all pages.  

 The BASIC permission set and permissions, as well as other permission sets, are provided in an XML file, examples of which are included with the [!INCLUDE[d365fin](includes/d365fin_md.md)]. If you want to extend them with new permission sets or permissions, you can modify them.  

> [!NOTE]  
>  Another prerequisite permission set is the FOUNDATION permission set.  
>   
>  If you want to use the UI Elements Removal feature to automatically remove UI elements according to user permissions, it is recommended that you use the FOUNDATION permission set together with the relevant application permission sets. For more information, see [Removing Elements from the User Interface According to Permissions](admin-removing-elements-from-the-user-interface-according-to-permissions.md).  

## Modifying the BASIC Permission Set with Default Permissions  
 Before beginning the following procedure, you have to install [!INCLUDE[d365fin](includes/d365fin_md.md)].  

#### To modify permission sets with default permissions using RapidStart Services  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Packages**, and then choose the related link.  

2.  On the **Home** tab, in the **Manage** group, choose **New** to create a new package.  

3.  Enter a appropriate values in the **Package Code** and **Description** fields.  

4.  On the **Tables** lines, add the following tables.  

    |Table name|Table number|  
    |----------------|------------------|  
    |Permission Set|2000000004|  
    |Permission|2000000005|  

5.  Select both lines, and on the **Tables** toolbar, choose **Excel**, and then choose **Export to Excel**.  

6.  Navigate to the RapidStart Services package. Choose **Open**.  

     The package contains all permission sets, including the Basic permission set. You can modify the permission settings in Excel. Save your changes.  

7.  On the **Tables** toolbar, choose **Excel**, and then choose **Import from Excel**.  

8.  In the configuration packages list, select the .xlsx file.  

9. On the **Home** tab, in the **Process** group, choose **Apply Package**.  

You can also modify permission sets directly in the Microsoft Dynamics NAV Windows client. For more information, see How to: Create or Modify Permission Sets. In addition, if you are upgrading from an earlier version of [!INCLUDE[d365fin](includes/d365fin_md.md)], you can upgrade permissions and roles as part of the upgrade process. For more information, see Upgrading Data Common to All Companies.

## See Also  
