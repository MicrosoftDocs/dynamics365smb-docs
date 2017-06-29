---
title: "How to: Configure New Companies"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, configuring companies"
ms.assetid: 37966db3-275a-440f-b73f-f1ac811e01c0
caps.latest.revision: 9
ms.author: "solsen"
manager: "terryaus"
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
# How to: Configure New Companies
You can configure and customize a new company that you have created. To fine tune your implementation, you proceed in three phases to complete your configuration. In the first phase, you import the configuration package, which is a .rapidstart file that you have saved. The file contains configuration information. In the second phase, you modify the configuration information, and then apply it to your new company. In the final phase, you review and fix errors.  
  
 The following procedures assume that you have created and saved a configuration package. For more information, see [How to: Create a Configuration Package](../SetupAndAdministration/how-to-create-a-configuration-package.md).  
  
> [!NOTE]  
>  Before implementing the following procedures, make sure that you have initialized and opened your new company and are on the FIX INCLUDE HERE<!--[!INCLUDE[rim](../Roles/includes/rim_md.md)] --> Role Center. To change your Role Center home page, see [How to: Change Role Centers](../GettingStarted/how-to-change-role-centers.md). Choose the RapidStart Profile ID.  
  
### To import a configuration package  
  
1.  Open the new company in the FIX INCLUDE HERE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] -->.  
  
2.  In the **Search** box, enter **Configuration Packages**, and then select the related link.  
  
3.  On the **Actions** tab, in the **Package** group, choose **Import Package**.  
  
4.  Navigate to the location where you have saved the .rapidstart configuration package file. Choose the **Open** button.  
  
5.  In the **Search** box, enter **Company Information**, and then choose the related link. Enter information about the company in the company information card. Include information, such as bank details. You can also provide a logo for the company.  
  
 All the tables that you have designated for inclusion in the new company are imported. At this point, you can apply the package data to the database, or adjust and modify the table data to meet your customer specifications.  
  
### To apply package data  
  
1.  In the **Search** box, enter **Configuration Worksheet**, and then select the related link.  
  
2.  Select a table for which you want to modify data, and on the **Actions** tab, in the **Functions** group, choose **Apply Data**. Choose **Yes** to confirm the application.  
  
3.  To confirm that the data is now in the database and that the application has succeeded, return to the **Worksheet** window. On the **Actions** tab, in the **Show** group, choose **Database Data**.  
  
    > [!NOTE]  
    >  After you apply data, you can only see it in the database. It is no longer in the package.  
  
### To modify and apply package data  
  
1.  In the **Search** box, enter **Configuration Worksheet**, and then select the related link.  
  
2.  Select a table for which you want to modify data, and on the **Actions** tab, in the **Show** group, choose **Package Data**.  
  
3.  The **Config. Package Records** window opens. Make your modifications. For example, you can delete options that do not apply.  
  
4.  On the **Home** tab, in the **Process** group, choose **Apply Data**. Choose the **OK** button.  
  
5.  To confirm that the data is now in the database and that the application has succeeded, return to the **Worksheet** window. On the **Actions** tab, in the **Show** group, choose **Database Data**.  
  
 There are certain types of errors that may occur when you apply data to a database. The most common error is not to include all related tables that are required. To fix this, you return to the configuration worksheet.  
  
### To locate and identify a configuration error  
  
1.  In the **Search** box, enter **Configuration Packages**, and then select the related link.  
  
2.  Select the package you want to review from the list. On the **Home** tab, in the **Manage** group, choose **Edit**.  
  
     Any table that has errors is highlighted. The number of package errors is displayed in the **No. of Package Errors** field.  
  
3.  Choose the **No. of Package Errors** field to open the **Config. Package Records** window.  
  
     The records with errors are listed.  
  
### To fix an error  
  
1.  Open the company on which you based your configuration package.  
  
2.  In the **Search** box, enter **Configuration Worksheet**, and then select the related link.  
  
3.  Fix errors and add missing related tables to the worksheet.  
  
4.  Add the tables to the existing configuration package, or create a new package that only contains the new tables. For more information, see [How to: Create a Configuration Package](../SetupAndAdministration/how-to-create-a-configuration-package.md).  
  
5.  Reopen the new company for which you are implementing the configuration.  
  
6.  Import the configuration package.  
  
    > [!NOTE]  
    >  If you import the same package again, you may overwrite any data modifications that you have already made. For that reason, you may want to add any new tables in a new package, and import that instead.  
  
7.  Apply the data to the database.  
  
## See Also  
 [Apply Configuration to New Companies](../SetupAndAdministration/apply-configuration-to-new-companies.md)   
 [How to: Copy Data to New Companies](../SetupAndAdministration/how-to-copy-data-to-new-companies.md)   
 [Configure the User Interface](../SetupAndAdministration/configure-the-user-interface.md)