---
    title: Migrate Customer Data | Microsoft Docs
    description: You can migrate existing customer data from an existing ERP system to Business Central using RapidStart Services. You can use Excel .xlsx files as the data carrier. You can also manually move the data by entering it directly into the company.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Migrate Customer Data
You can migrate existing customer data from an existing ERP system to [!INCLUDE[d365fin](includes/d365fin_md.md)] using the data migration tools of RapidStart Services. You can use Excel files as the data carrier. You can also manually move the data by entering it directly in the company.

> [!NOTE]
> Fields of type Blob cannot be exported/imported using Excel.

The **Migration Overview** and **Config. Worksheet** pages provide access to the functions and views to perform all the tasks that relate to data migration. We recommend that you migrate one table at a time, to handle dependencies in your data. In migration, you will also touch the master data tables, which contain information about customers, vendors, items, contacts, and the general ledger.  

## To import configuration packages
When you create a new company, you can import company settings for the new company. You import the settings from a .rapidstart file, which delivers the package contents in a compressed format. A corresponding set of default data migration tables are imported. The data set contains master data tables and the setup data tables. Your first task in data migration is to evaluate if the default migration setup meets the needs of the new company.

> [!NOTE]  
>  You cannot rename a file that is not already a RapidStart Services configuration package as a .rapidstart configuration package file and then try to import it. If you try to do so, you will receive an error message.  

Before you start, you must make sure that you have permission to run the RapidStart Services objects. For example, you can have the SUPER or D365 RAPIDSTART permission sets. We also recommend that you are on a Role Center with links to RapidStart Services, such as the Administration Role Center. For more information, see [To change the role](ui-change-basic-settings.md#to-change-the-role).  

> [!IMPORTANT]  
> When exporting and importing configuration packages between two company databases, the databases should have the same schema to make sure that all data is transferred successfully. This means that the databases should have the same table and field structure, in which the tables have the same primary keys and fields have the same IDs and data types.  
>
>  You can import a configuration package that has been exported from a database that has a different schema than that target database. However, any tables or fields in the configuration package that are missing in the target database will not be imported.
>
> Tables that have different primary keys and fields that have different data types will also not be successfully imported. For example, if the configuration pack includes table **50000 Customer** that has primary key **Code20** and the database to which you import the pack includes table **50000 Customer Bank Account** that has the primary key **Code20 + Code 20**, data will not be imported.  

1. Open the new company.  
2. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.  
3. Choose the **Import Package** action. Navigate to the .rapidstart package file that you want to import, and then choose the **Open** action. During import, the package contents are decompressed and the package record is created.  

    When the import is complete, you can see the number of configuration tables that have been imported in the **No. of Tables** field.  
4. To review the list of configuration tables, choose the **View** action.  
5. To apply the package, choose the **Apply Package** action.  

    > [!NOTE]  
    >  The data migration information is based on configuration templates, if you specify one. You must update the template first to change the list of fields.  

6.  To review the field selections, select a table, and then, on the **Lines** tab, choose the **Fields** action. Compare and review the number of fields that are available to the number of fields whose data has been applied.  

If the selection of tables does not meet your needs, you can create one or more new data migration files. If the files are sufficient, you can continue with the data migration using Excel or XML files.

## To create a data migration file

You can create new data migration files and customize them to support your business.  

> [!TIP]
> A file can only be used to migrate a field that has its **FieldClass** property set to **Normal**.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Package**, and then choose the related link.  
2. Select and open the package that you want to use to migrate data, and then choose the **Get Tables** action. The **Get Package Table** page opens.  
3. In the **TableID** field, enter a table number or select a table from the list, for example, table 18, **Customer**. The **Table Name** field is automatically filled in.  
4. Select the new migration table, and then, on the **Tables** tab, choose the **Fields** action. The **Migration Fields** page opens.  
5. Clear the **Include Field** check box for any field that you do not want to import, and then choose the **Set Included** or the **Clear Included** action.  

> [!IMPORTANT]  
>  If the **Include Field** check box is selected by default, that field is part of the primary key. The selection should not be cleared, or errors will be introduced and the record cannot be imported.  
>
>  If you include a field that has a relationship with another table, the **Validate Field** check box is automatically selected. Validation can result in the update of other fields in this and other tables and is executed in the order of the field number.  

A new migration table is created.  

## To export data migration files
When you have determined the tables that you want to transfer customer data to, you export the files.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.  
2. Select and open the package that you want to use for export.
3. Select the table or tables that you want to export, and then choose the **Export to Excel** action.
4. Save the exported Excel file.  
5. Repeat this procedure for all the relevant data migration tables. If you select multiple tables at the same time, the export of their data is into a common workbook.  

If the table is empty, the resulting data migration file contains empty cells for the fields you selected when you chose or created migration tables for your new company. If the selected data migration table contains data, it will be exported.  

## To map values to be used during import
When you apply data that you have imported from Excel or from a RapidStart package, [!INCLUDE[d365fin](includes/d365fin_md.md)] treats and handles the mapping based on table relations:  

- If you define a mapping directly for a field in a table, then [!INCLUDE[d365fin](includes/d365fin_md.md)] uses it.  

- If the field has a relation to another table, [!INCLUDE[d365fin](includes/d365fin_md.md)] searches for the mapping defined for the primary key field in the related table. The related table, however, must be part of the configuration package.  

- If mapping information is defined in both places, for the field directly and for the primary key in the related table, then [!INCLUDE[d365fin](includes/d365fin_md.md)] will search for the mapping in both places.  

- If the same mappings are defined directly for a field and in the related table, but have different new values, the mapping that is defined directly for the field takes priority over the mapping that is defined for the table that the field is referencing.  

In the following procedures, you should review in advance which values you want to retain during the migration process. To perform the following procedures, you need data migration files (.xlsx) that you have exported from [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [To export data migration files](admin-migrate-customer-data.md#to-export-data-migration-files).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.
2. Open the package for the company in question.  
3. Select the table for which you want to map values, and then, on the **Tables** tab, choose the **Fields** action.  
4. For each field that you want to map, choose the **Mapping** action.  
5. In the **Old Value** field, enter the value that you want to change. In the **New Value** field, enter the value that you want the old value to be changed to. Choose the **OK** button.  
6. Import the customer data. For more information, see [To import customer data](admin-migrate-customer-data.md#to-import-customer-data).
7. In the **No. of Package Errors** field, see if there are any errors reported. If there are, drill down to see the errors. The **Config. Package Records** page opens.
8. Choose the **Show Error** action. You will receive the following error: **XX is not a valid option. Valid options are: XX**. Choose the **OK** button.  
9. To apply the mapping that you have set up, choose the **Apply Data** action.  

### Mapping Example  
The following example illustrates how [!INCLUDE[d365fin](includes/d365fin_md.md)] implements mapping definitions.  

1. Create a configuration table that has a **Salesperson/Purchaser** table. Define a mapping for the **Code** field.  
2. Add additional tables to the package, for example, **Customer** and **Vendor**. These tables both reference the **Salesperson/Purchaser** table through the **Salesperson Code** and **Purchaser Code** fields respectively.  
3. When you apply data, the mapping that you provided for the **Code** field in the the **Salesperson/Purchaser** table will also be considered during the processing of the **Salesperson Code** and **Purchaser Code** fields.

## To add additional values to [!INCLUDE[d365fin](includes/d365fin_md.md)]  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.  
2. Select the table for which you want to add additional values, and then, on the **Tables** tab, choose the **Fields** action.  
3. For the fields for which you want [!INCLUDE[d365fin](includes/d365fin_md.md)] to permit additional values during migration, select the **Create Missing Codes** check box.  
4. Import the customer data. For more information, see [To import customer data](admin-migrate-customer-data.md#to-import-customer-data).

## To clean up and process data before applying data
In some cases, you may want to clean up customer data and process it before you apply it to the database. To do that, you can use the **Config. Package - Process** batch job to fix issues, such as:  

- Convert dates and decimals to the format required by the regional settings on a user's computer.  
- Remove leading/trailing spaces or special characters.  

When you have run the batch job, use the following procedure to process the data.  

1. Open the configuration package for the company.  
2. Choose the **Process Data** action.  
3. To apply the mapping that you have set up, choose the **Apply Data** action.

## To migrate customer data
When you have exported a migration table, your next step is to enter the customer's legacy data. To simplify your tasks, you can take advantage of the XML manipulation tools that are built into Excel. You can also use Excel built-in functions to help with data formatting and to put data in the correct cell.

For assistance with XML, enable the **Developer** tab of the Excel ribbon, and then choose the **Source** action to see the XML schema of your migration table as represented in Excel.

The following procedure is based on an Excel worksheet that you have created for migration. For more information, see [To export data migration files](admin-migrate-customer-data.md#to-export-data-migration-files).

> [!IMPORTANT]  
> Do not change the columns in the Excel worksheets. If they are moved, changed, or deleted, the worksheet cannot be imported into [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. In Excel, open the exported data file. There is a worksheet with the name of the table.
2. Rename Sheet1 to indicate that the worksheet will be used to transform the data. Copy the header row without its formatting from the exported table to the new worksheet.
3. On a third worksheet, copy all your customer data. Rename the sheet to be called e.g. Legacy Data.
4. Make an Excel formula to map data in the transformation worksheet between the fields in the exported worksheet and customer legacy data.
5. When you have mapped all of the data, copy the range of data onto the table worksheet.
6. Save the file and make sure that you do not change the file type.

You are now ready to import the data migration files that contain customer legacy data into [!INCLUDE[d365fin](includes/d365fin_md.md)].

## To import customer data
When the customer data has been entered in the data migration files in Excel, you import the files into [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. Open the **Config. Package Card** page.
2. Select the table for which you want to import data, and then, on the **Tables** tab, choose the **Import from Excel** action.
3. Locate and open the file that you want to import data from.
4. On the **Config. Package Import Preview** page, review the content that will be imported.

    The **Config. Package Import Preview** page provides an overview of the Excel file content to be imported. It also indicates if a new configuration package is created or the existing one is updated, and if new configuration package lines (tables) are created or existing ones are updated.    
5. Choose the **Import** action

Data from the file is imported into the configuration package tables. In the **No. of Package Records** field, you can see the number of records that have been imported. In addition, you can see the number of migration errors.

## To validate customer data
Customer data must be validated before you apply the records to the [!INCLUDE[d365fin](includes/d365fin_md.md)] database.  

> [!NOTE]  
>  In most cases, invalid data is not created in the database. However, the application can occasionally be blocked if an imported migration table contains errors.  

1. On the **Migration Overview** page, review the **No. of Migration Errors** field to see whether any errors occurred during import.  
2. If there are errors, select the migration table, and then, on the **Tables** tab, choose the **Errors** action. The **Invalid** check box is selected for each record that has an error.  
3. To review errors, select a line, and then choose the **Show Error** action.  

    The **Error Text** field contains the reason for the error. The **Field Caption** field contains the caption of the field that contains the error.  
4.  To correct an error or otherwise make an update, on the **Migration Overview** page, choose the **Migration Record** action, and then, on the **Migration Record** page, correct the record with the error.  

When you make a correction, the record is removed from the list of records on the **Migration Data Errors** page.  

You are now ready to apply the customer's data to the database.  

## To apply customer data
When you have imported all data migration records that are valid and have no errors, you can apply the records to the [!INCLUDE[d365fin](includes/d365fin_md.md)] database.  

1. Open the **Configuration Packages** page.  
2. Select the table for the data migration file that you want to apply, and then choose the **Apply Data** action.

You can see the number of database records that have been created in the **No. of Database Records** field. You can verify that the correct records have been created by choosing the link in the **No. of Database Records** field.  

The customer's company database is now set up and basic data is imported. Your next steps in the implementation process are to train users, define processes, create additional data, customize reports, and so on.

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
