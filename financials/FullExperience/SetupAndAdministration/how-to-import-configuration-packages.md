---
title: "How to: Import Configuration Packages"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, migrating data"
ms.assetid: ffa6973a-bf8d-4793-9c21-61b7f2fad6f6
caps.latest.revision: 18
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
# How to: Import Configuration Packages
When you create a new company, you can import company settings for the new company. You import the settings from a .rapidstart file, which delivers the package contents in a compressed format. A corresponding set of default data migration tables are imported. The data set contains master data tables and the setup data tables. Your first task in data migration is to evaluate if the default migration setup meets the needs of the new company.  
  
> [!NOTE]  
>  You cannot rename a file that is not already a FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[rim](../Roles/includes/rim_md.md)] --> --> --> configuration package as a .rapidstart configuration package file and then try to import it into FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> -->. If you try to do so, you will receive an error message.  
  
 The [!INCLUDE[rim](../Roles/includes/rim_md.md)] migration tools can be applied to any [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] table. Use the migration tools for fast and accurate data transfer.  
  
 Before you start, make sure that you are on the [!INCLUDE[rim](../Roles/includes/rim_md.md)] Role Center page. It provides the correct context for your configuration work. To change your Role Center home page, see [How to: Change Role Centers](../GettingStarted/how-to-change-role-centers.md). Choose the RapidStart Profile ID.  
  
> [!IMPORTANT]  
>  When exporting and importing configuration packages between two company databases, the databases should have the same schema to make sure that all data is transferred successfully. This means that the databases should have the same table and field structure, in which the tables have the same primary keys and fields have the same IDs and data types.  
>   
>  You can import a configuration package that has been exported from a database that has a different schema than that target database. However, any tables or fields in the configuration package that are missing in the target database will not be imported. Tables that have different primary keys and fields that have different data types will also not be successfully imported. For example, if the configuration pack includes table **50000 Customer** that has primary key **Code20** and the database to which you import the pack includes table **50000 Customer Bank Account** that has the primary key **Code20 \+ Code 20**, data will not be imported.  
  
### To import a configuration package for data migration  
  
1.  Open the new company.  
  
2.  Open the **Configuration Packages** window.  
  
3.  On the **Home** tab, in the **Process** group, choose **Import Package**. Navigate to the .rapidstart package file that you want to import. Choose **Open**. During import, the package contents are decompressed and the package record is created.  
  
     After import is complete, you can see the number of configuration tables that have been imported in the **No. of Tables** field.  
  
4.  To review the list of configuration tables, on the **Home** tab, in the **Manage** group, choose **View**.  
  
5.  To apply the package, on the **Home** tab, in the **Process** group, choose **Apply Package**.  
  
    > [!NOTE]  
    >  The data migration information is based on configuration templates, if you specify one. You must update the template first to change the list of fields.  
  
6.  To review the field selections, select a table. On the **Lines** toolbar, on the **Tables** menu, choose  **Fields**. Compare and review the number of fields that are available to the number of fields whose data has been applied.  
  
 If the selection of tables does not meet your needs, you can create one or more new data migration files. If the files are sufficient, you can continue with the data migration using .xls or .xml files.  
  
## See Also  
 [How to: Create and Modify the Migration Tables List](../SetupAndAdministration/how-to-create-and-modify-the-migration-tables-list.md)   
 [How to: Import Customer Data](../SetupAndAdministration/how-to-import-customer-data.md)   
 [How to: Create and Modify the Migration Tables List](../SetupAndAdministration/how-to-create-and-modify-the-migration-tables-list.md)   
 [How to: Create a Configuration Package](../SetupAndAdministration/how-to-create-a-configuration-package.md)