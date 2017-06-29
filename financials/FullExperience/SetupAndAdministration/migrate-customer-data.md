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
# Migrate Customer Data
You can migrate existing customer data from an existing ERP system to ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> using the data migration tools of ADD INCLUDE<!--[!INCLUDE[rimlong](../SetupAndAdministration/includes/rimlong_md.md)]-->. You can use Excel .xlsx files as the data carrier. You can also manually move the data by entering it directly into the company.  
  
 The **Migration Overview** window and the **Configuration worksheet** provide access to the functions and views to perform all the tasks that relate to data migration. We recommend that you migrate one table at a time, to handle dependencies in your data. In migration, you will also touch the master data tables, which contain information about customers, vendors, items, contacts, and the general ledger.  
  
> [!WARNING]  
>  The **Apply Template** function overwrites existing data in a record. If this function is used in master data migration, it will overwrite the imported data when you create records.  
  
 The following table describes the sequence of tasks with links to topics that describe them. These tasks are listed in the order in which you generally perform them.  
  
|**To**|**See**|  
|------------|-------------|  
|Evaluate default data migration files and determine whether they meet the customer's needs.|[How to: Import Configuration Packages](../SetupAndAdministration/how-to-import-configuration-packages.md)|  
|Create new customized migration files if the default migration files do not meet the customer's needs.|[How to: Create and Modify the Migration Tables List](../SetupAndAdministration/how-to-create-and-modify-the-migration-tables-list.md)|  
|Export necessary migration files.|[How to: Export Migration Tables](../SetupAndAdministration/how-to-export-migration-tables.md)|  
|Automatically or manually capture customer information.|[How to: Migrate Customer Data](../SetupAndAdministration/how-to-migrate-customer-data.md)|  
|Import customer information into the ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> company.|[How to: Import Customer Data](../SetupAndAdministration/how-to-import-customer-data.md)|  
|Validate customer information and resolve errors before applying customer information to the ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> database.|[How to: Validate Customer Data](../SetupAndAdministration/how-to-validate-customer-data.md)|  
|Apply validated customer information to the ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> database.|[How to: Apply Customer Data](../SetupAndAdministration/how-to-apply-customer-data.md)|  
  
## See Also  
 [How to: Create and Modify the Migration Tables List](../SetupAndAdministration/how-to-create-and-modify-the-migration-tables-list.md)