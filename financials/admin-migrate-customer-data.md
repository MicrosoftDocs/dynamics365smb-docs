---
    title: Migrate Customer Data | Microsoft Docs
    description: You can migrate existing customer data from an existing ERP system to ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/rimlong_md.md)]-->. You can use Excel .xlsx files as the data carrier. You can also manually move the data by entering it directly into the company.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/05/2018
    ms.author: sgroespe

---
# Migrating Customer Data
You can migrate existing customer data from an existing ERP system to [!INCLUDE[d365fin](includes/d365fin_md.md)] using the data migration tools of RapidStart Services. You can use Excel .xlsx files as the data carrier. You can also manually move the data by entering it directly into the company.

The **Migration Overview** window and the **Configuration worksheet** provide access to the functions and views to perform all the tasks that relate to data migration. We recommend that you migrate one table at a time, to handle dependencies in your data. In migration, you will also touch the master data tables, which contain information about customers, vendors, items, contacts, and the general ledger.  

> [!WARNING]  
>  The **Apply Template** function overwrites existing data in a record. If this function is used in master data migration, it will overwrite the imported data when you create records.  

The following table describes the sequence of tasks with links to topics that describe them.

|**To**|**See**|  
|------------|-------------|  
|Evaluate default data migration files and determine whether they meet the customer's needs.|[Import Configuration Packages](admin-how-to-import-configuration-packages.md)|  
|Create new customized migration files if the default migration files do not meet the customer's needs.|[Create and Modify the Migration Tables List](admin-how-to-create-and-modify-the-migration-tables-list.md)|  
|Export necessary migration files.|[Export Migration Tables](admin-how-to-export-migration-tables.md)|  
|Automatically or manually capture customer information.|[Migrate Customer Data](admin-how-to-migrate-customer-data.md)|  
|Import customer information into the [!INCLUDE[d365fin](includes/d365fin_md.md)] company.|[Import Customer Data](admin-how-to-import-customer-data.md)|  
|Validate customer information and resolve errors before applying customer information to the [!INCLUDE[d365fin](includes/d365fin_md.md)] database.|[Validate Customer Data](admin-how-to-validate-customer-data.md)|  
|Apply validated customer information to the [!INCLUDE[d365fin](includes/d365fin_md.md)] databas.|[Apply Customer Data](admin-how-to-apply-customer-data.md)|  

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart)  
[Administration](admin-setup-and-administration.md)
