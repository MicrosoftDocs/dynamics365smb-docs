---
title: "Migrate Customer Data"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "data migration, about"
  - "RapidStart Services, migrating data"
  - "migrating, about"
ms.assetid: 17f61157-23a5-479d-989c-cb73afc81a5a
caps.latest.revision: 22
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
# Migrate Customer Data
You can migrate existing customer data from an existing ERP system to [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] using the data migration tools of [!INCLUDE[rimlong](../SetupAndAdministration/includes/rimlong_md.md)]. You can use Excel .xlsx files as the data carrier. You can also manually move the data by entering it directly into the company.  
  
 The **\($ N\_8614 Migration Overview $\)** window and the **Configuration worksheet** provide access to the functions and views to perform all the tasks that relate to data migration. We recommend that you migrate one table at a time, to handle dependencies in your data. In migration, you will also touch the master data tables, which contain information about customers, vendors, items, contacts, and the general ledger.  
  
> [!WARNING]  
>  The **Apply Template** function overwrites existing data in a record. If this function is used in master data migration, it will overwrite the imported data when you create records.  
  
 The following table describes the sequence of tasks with links to topics that describe them. These tasks are listed in the order in which you generally perform them.  
  
|**To**|**See**|  
|------------|-------------|  
|Evaluate default data migration files and determine whether they meet the customer's needs.|[How to: Import Configuration Packages](../SetupAndAdministration/how-to-import-configuration-packages.md)|  
|Create new customized migration files if the default migration files do not meet the customer's needs.|[How to: Create and Modify the Migration Tables List](../SetupAndAdministration/how-to-create-and-modify-the-migration-tables-list.md)|  
|Export necessary migration files.|[How to: Export Migration Tables](../SetupAndAdministration/how-to-export-migration-tables.md)|  
|Automatically or manually capture customer information.|[How to: Migrate Customer Data](../SetupAndAdministration/how-to-migrate-customer-data.md)|  
|Import customer information into the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] company.|[How to: Import Customer Data](../SetupAndAdministration/how-to-import-customer-data.md)|  
|Validate customer information and resolve errors before applying customer information to the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database.|[How to: Validate Customer Data](../SetupAndAdministration/how-to-validate-customer-data.md)|  
|Apply validated customer information to the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database.|[How to: Apply Customer Data](../SetupAndAdministration/how-to-apply-customer-data.md)|  
  
## See Also  
 [How to: Create and Modify the Migration Tables List](../SetupAndAdministration/how-to-create-and-modify-the-migration-tables-list.md)