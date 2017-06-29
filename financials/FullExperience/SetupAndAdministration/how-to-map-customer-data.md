---
title: "How to: Map Customer Data"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 65b74cd1-ef18-4e85-bb4f-b4cdebbf3f29
caps.latest.revision: 5
ms.author: "edupont"
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
# How to: Map Customer Data
You can map values from an existing ERP system into your ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> implementation during the migration of data. There are two ways in which you can do this. In one method, you can have ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> take codes that are missing in ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> and automatically create them. In the other approach, you can take a value that exists in your ERP solution, for example, an option from a list, and map it to an existing valid option that ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> already has.  
  
 In the procedures that follow, you should review in advance which values you want to retain during the migration process. To perform the following procedures, you will need data migration files \(.xls\) that you have exported from ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->. For more information, see [How to: Export Migration Tables](../SetupAndAdministration/how-to-export-migration-tables.md).  
  
### To add additional values to ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->  
  
1.  Open the configuration package for the company.  
  
2.  Select the table for which you want to add additional values, and on the **Tables** FastTab, choose **Table**, and then choose **Fields**.  
  
3.  For the fields for which you want ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> to permit additional values during migration, select the **Create Missing Codes** check box.  
  
4.  Import the customer data. For more information, see [How to: Import Customer Data](../SetupAndAdministration/how-to-import-customer-data.md).  
  
### To map values to be used during import to ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->  
  
1.  Open the configuration package for the company.  
  
2.  Select the table for which you want to map values, and on the **Tables** FastTab, choose **Table**, and then choose **Fields**.  
  
3.  For each field that you want to map, on the **Home** tab, in the **Process** group, choose **Mapping**.  
  
     For more information on how mapping works, see [About Mapping](../SetupAndAdministration/about-mapping.md).  
  
4.  In the **Old Value** field, enter the value that you want to change. In the **New Value** field, enter the value that you want the old value to be changed to. Choose the **OK** button.  
  
5.  Import the customer data. For more information, see [How to: Import Customer Data](../SetupAndAdministration/how-to-import-customer-data.md). In the **No. of Package Errors** field, see if there are any errors reported. If there are, drill down to see the errors. The **Config. Package Records** window opens.  
  
6.  On the **Home** tab, in the **Process** group, choose **Show Error**. You will receive the following error: **\<option\> is not a valid option. Valid options are \<valid option list\>**. Choose the **OK** button.  
  
     To apply the mapping that you have set up, on the **Home** tab, in the **Process** group, choose **Apply Data.**  
  
## See Also  
 Config. Field Mapping   
 Config. Field Mapping   
 [How to: Apply Customer Data](../SetupAndAdministration/how-to-apply-customer-data.md)   
 [How to: Clean Up and Process Data](../SetupAndAdministration/how-to-clean-up-and-process-data.md)   
 Config. Package \- Process