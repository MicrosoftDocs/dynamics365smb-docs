---
title: "How to: Create and Modify the Migration Tables List"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "RapidStart Services, migrating data"
ms.assetid: 4c9f9061-cf03-4a11-899d-c6a3be91078c
caps.latest.revision: 12
ms.author: "edupont"
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
# How to: Create and Modify the Migration Tables List
You can create new data migration files and customize them to support your business. However, a file can only be used to migrate a field that has its **FieldClass** property set to **Normal**. For more information, see [FieldClass Property](../Topic/FieldClass%20Property.md).  
  
 To learn more about using the configuration process, see [How to: Manage Company Configuration in a Worksheet](../SetupAndAdministration/how-to-manage-company-configuration-in-a-worksheet.md).  
  
### To create a data migration file  
  
1.  In the **Search** box, enter **Configuration Package**, and then choose the related link.  
  
2.  Select and open the package that you want to use to migrate data. On the **Actions** tab, choose **Get Tables**. The **Get Package Table** window opens.  
  
3.  In the **TableID** field, enter a table number or select a table from the list, for example, table 18, **Customer**. The **Table Name** field is automatically filled in.  
  
4.  Select the new migration table, and on the **Tables** toolbar, on the **Table** menu, choose **Fields** to open the **Migration Fields** window.  
  
5.  Clear the **Include Field** check box for any field that you do not want to import. On the **Actions** tab, you can also choose **Set Included** or **Clear Included**.  
  
    > [!IMPORTANT]  
    >  If the **Include Field** check box is selected by default, that field is part of the primary key. The selection should not be cleared, or errors will be introduced and the record cannot be imported.  
  
    > [!IMPORTANT]  
    >  If you include a field that has a relationship with another table, the **Validate Field** check box is automatically selected. Validation can result in the update of other fields in this and other tables and is executed in the order of the field number.  
  
     A new migration table is created.  
  
## See Also  
 [How to: Export Migration Tables](../SetupAndAdministration/how-to-export-migration-tables.md)