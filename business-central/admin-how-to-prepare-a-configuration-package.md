---
    title: How to Prepare a Configuration Package | Microsoft Docs
    description: When you configure a new company, table relations are recognized and processed. Data is imported and applied in the correct order. Dimension tables are also imported if they are included in the configuration package.
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
# Prepare a Configuration Package
When you configure a new company, table relations are recognized and processed. Data is imported and applied in the correct order. Dimension tables are also imported if they are included in the configuration package. For more information, see [To import customer data](admin-migrate-customer-data.md#to-import-customer-data). 

To help your customer use the configuration package, you may want to add a questionnaire or a set of questionnaires to the package. The questionnaire can help the customer in understanding the various setup options. Typically, questionnaires are created for the major setup tables where a customer may require additional guidance about how to select an appropriate setting. For more information, see [Gather Customer Setup Values](admin-gather-customer-setup-values.md).

## Before You Create a Configuration Package
There are some things to consider before you create a configuration package because they will impact you or your customer's ability to import it. 

### Tables That Contain Posted Entries
You cannot import data to tables that contain posted entries, such as the tables for customer, vendor, and item ledger entries, so you should not include this data in your configuration package. You can add entries to these tables after you import the configuration package by using journals to post the entries. For more information, see [Posting Documents and Journals](ui-post-documents-journals.md).

### Licensing
Your license must include the tables you are updating. If you are unsure, the **Configuration Worksheet** page can help. If your license includes the table, the **Licensed Table** check box is chosen.  

### Permissions
The process of creating and importing a configuration package involves the following effective permissions for all tables in the package: 

* The user who exports data for the configuration package must have **Read** effective permissions.
* The user who imports the configuration package must have **Insert** and **Modify** effective permissions.

### Database Schema
When exporting and importing configuration packages between two company databases, the databases should have the same schema to ensure that all data is transferred successfully. This means that the databases should have the same table and field structure, in which the tables have the same primary keys and fields have the same IDs and data types.  

You can import a configuration package that has been exported from a database that has a different schema than that target database. However, any tables or fields in the configuration package that are missing in the target database will not be imported. Tables with different primary keys and fields with different data types will also not successfully import. For example, if the configuration pack includes table **50000, Customer** that has primary key **Code20** and the database to which you import the pack includes table **50000, Customer Bank Account** that has the primary key **Code20 + Code 20**, then data will not be imported.  

## To create a configuration package  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.  
2. Choose the **New** action.  
3. On the **General** FastTab, fill in the fields as appropriate. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. To exclude the configuration questionnaires, configuration templates, and configuration worksheet tables from the package, select the **Exclude Configuration Tables** check box. Otherwise, these tables will be added to the list of package tables automatically when you export the package.  
5. Choose the **Get Tables** action. The **Get Package Tables** batch job page opens.  
6. Choose the **Select Tables** field. The **Config. Selection** page opens.  
7. Choose the **Select All** action to add all tables to the package, or select the **Selected** check box for each table in the list that you want to add.
8. Choose the **OK** button. The count of tables that you have selected is indicated in the **Select Tables** field. Specify additional options, and then choose the **OK** button. [!INCLUDE[d365fin](includes/d365fin_md.md)] tables are added to the lines of the **Config. Package** page.  

    > [!NOTE]  
    >  You can also do this in the configuration worksheet. Select the tables you want to include in the package, and then choose the **Assign Package** action.

9. To select the fields that you want to include from a table, select the table, and then, on the **Lines** tab, choose the **Fields** action.
Specify which fields are included in the package. By default, all fields are included.

    - To select just the fields you want to include, choose the **Clear Included** action. To add all fields, choose the **Set Included** action.  
    - To specify that the field data should not be validated, clear the **Validate Field** check box for the field.  

10. Determine whether you have introduced potential errors, by choosing the **Validate Package** action. This can occur when you do not include tables that your configuration relies on.  
11. Choose the **OK** button.  

After you have refined the list of fields to include from a table, you can check your results in Excel.  

### To filter and review your dataset  
1. To filter to a certain set of records to include in the package, on the **Lines** tab, choose the **Filters** action, and then specify the appropriate filter values.  
2. On the package card, on the **Lines** tab, choose the **Export to Excel** action.  
3. Confirm the messages that enable the export of data to Excel. The named .xlsx file opens. Review the records that have been exported.  
4. Close Excel.  

### To include a template for application to a table  
For certain tables, such a table that will contain master data, you can specify a template to apply to the data. The template can include the required fields that you want to apply to all master data and that you never want to vary. For example, you can create a template that can be used with customer data. The template can contain all the required fields, which then enables consistent import of standardized information. Information that cannot be standardized, such as customer name, is then treated when you do an import of customer data.

1. On the **Config. Package Card** page, select a table, and then choose the **Data Template** field. A list of templates based on the table is displayed.
2. Select a template, and then choose the **OK** button.  

After the package is complete, follow the next procedure to save the package to a file. You can then give the package to a customer or partner to use.

### To save and export a configuration package  
- On the **Config. Package Card** page, choose the **Export Package** action.  

The package is created in a .rapidstart file, which delivers the package contents in a compressed format. Configuration questionnaires, configuration templates, and the configuration worksheet are added to the package automatically unless you specifically decide to exclude them.  

You can save the file with a name that is meaningful to you, but you cannot change the extension of the file. It must be .rapidstart.  

### To copy a configuration package  
After you have created a package that meets most of your needs, you can use it as a basis for creating similar packages. This can speed up implementation time and enhances the repeatability of RapidStart Services.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.  
2. Select a package from the list, and then choose the **Copy Package** action.  
3. In the **New Package Code** field, enter a code for the new package.  
4. Select the **Copy Data** check box if you also want to copy database data from the existing package.  
5. Choose the **OK** button.

## To customize a configuration package
Use the configuration worksheet to gather and categorize the information that you want to use to configure a new company, and arrange tables in a logical way. Formatting in the worksheet is based on a simple hierarchy: Areas contain groups, which in turn contain tables. Areas and groups are optional, but are necessary to enable an overview of the configuration process on the RapidStart Services Role Center.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.  
2.  In the **Line Type** field, choose **Area**. In the **Name** field, enter a descriptive name.  
3.  In the **Line Type** field, choose **Group**. In the **Name** field, enter a descriptive name.  
4.  In the **Line Type** field, choose **Table**. In the **Table ID** field, select the table you want to include in the worksheet.  

You can now assign the tables to specific configuration packages that you have created or plan to create. For more information, see [To assign a table to a configuration package](admin-how-to-prepare-a-configuration-package.md#to-assign-a-table-to-a-configuration-package).

## To work with promoted tables  
1. Select the **Promoted Table** check box to indicate a table that is frequently used during the setup process by a typical customer, for example, the **G/L Account** table. When a table has this designation, a customer will be able to easily filter his worksheet to see just the list of promoted tables that require attention.  
2. To see the filtered view, choose the **Promoted Only** action. The list of tables contains only those tables that have the check box selected.  

## To assign a table to a configuration package  
After you have defined the tables that you want to treat as part of your configuration, you can easily assign the tables to configuration packages. You can assign a table to one package only. In the following procedure, you assign the package from within configuration worksheet.  

> [!NOTE]  
>  You can also create a package directly, and add tables to it. For more information, see [To create a configuration package](admin-how-to-prepare-a-configuration-package.md#to-create-a-configuration-package).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.
2. In the configuration worksheet, select a line or group of lines that you want to assign to a configuration package, and then choose the **Assign Package** action.  
3.  Select a package from the list, or choose the **New** action to create a new package, and then choose the **OK** button.  

    If a table is not already included in the package, it will now be added. The package code field on the worksheet line will be filled in with the code of the package that the table is assigned to.  
4. If you choose an existing package, you can see how many tables are already in the package by reviewing the information in the **No. of Tables** field.

## To review or customize existing database data
As you create a configuration package for a solution, you can view and customize the available database data to suit your customer needs. The database table must have an associated page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.
2. In the configuration worksheet, identify the tables whose data that you want to view or customize.  

    > [!NOTE]  
    >  Make sure that each table has a page ID assigned to it. For standard [!INCLUDE[d365fin](includes/d365fin_md.md)] tables, this value is automatically filled in. For custom tables, you must provide the ID.

3. Choose the **Database Data** action. The page for the related page opens.
4. Review the available information. Modify it as necessary by deleting records that are not relevant or by adding new ones.    

## To copy data from a test environment to a production environment  
After you have vetted and tested all your setup information, you can proceed to copy data to your production environment. You create a new company in the same database.

1. Open and initialize the new company.  
2. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.  
3. Choose the **Copy Data from the Company** action.  
4. On the **Copy Company Data** page, choose the **Copy From** field. The **Companies** page opens.  
5. Select the company from which you want to copy data, and then choose the **OK** button. A list of tables selected on the configuration worksheet opens. Only tables that contain records are included in this list.
6. Select the tables that you want to copy data from, and then choose the **Copy Data** action. On the **Copy Company Data** page, choose the **OK** button.  

## See Also  
[Gather Customer Setup Values](admin-gather-customer-setup-values.md)  
[Set Up Company Configuration](admin-set-up-company-configuration.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
