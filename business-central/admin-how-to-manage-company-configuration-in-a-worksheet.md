---
    title: How to Manage Company Configuration in a Worksheet | Microsoft Docs
    description: The configuration worksheet is the central location in which you can plan, track, and perform your configuration work. You can create a worksheet for each company that you are working with or create a standard configuration worksheet that can be used for configuring multiple identical companies.
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
# Manage Company Configuration in a Worksheet
The configuration worksheet is the central location in which you can plan, track, and perform your configuration work. You can create a worksheet for each company that you are working with or create a standard configuration worksheet that can be used for configuring multiple identical companies.  

The first step in preparing a configuration package is to select a company that you have already set up and modified to suit most of your solution needs. This company serves as the baseline for your configuration work on new companies. In the worksheet, you designate the tables that you want your configuration to control and handle. Since most tables in [!INCLUDE[d365fin](includes/d365fin_md.md)] have relationships and dependencies to other tables, you should also include those related tables as necessary. Together, these tables will then serve as the structure around which you will build a new company. Subsequent steps help you package and then deploy your configuration.  

To aide you in tracking and reviewing your work, use the **Config. Package Table** FactBox to see information about records. Use the **Config. Related Tables** FactBox to monitor table relationships.  

The following procedures demonstrate how to add and customize table information for your configuration.  

## To open the configuration worksheet  
1.  In [!INCLUDE[d365fin](includes/d365fin_md.md)], open the company that is the baseline for configuration, and then open its RapidStart Services Implementer Role Center.  
2.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.  

## To add a table to the worksheet  
1.  On the **Config. Worksheet** page, choose the **Edit List** action.  
2.  On the first line, in the **Line Type** field, select **Table**.  
4.  In the **Table ID** field, select the table that you want to add to your configuration.  
5.  In the **Page ID** field, enter the ID of the page that is associated with the table. For standard tables, this value is automatically filled in. For custom tables, you must provide the ID.
6.  In the **Reference** field, enter the URL of a documentation page, for example in Help, that provides best-practice information or instructions o setting up the table.  
7.  To add related tables, choose the **Get Related Tables** action.  

    > [!NOTE]  
    > Related tables will not be added with the **Get Related Tables** action if either of the following is true:
    > - The relation is conditional.  
    > Example: If you get related tables for the **Customer** table, then the **Location** table will not be added, since it is only conditionally related to the **Customer** table, namely if the **Location Code** field in the **Customer** table is filled in.  
    > - The related table is filtered.  
    > Example: A field in the related table has a WHERE clause. The reason for this is that the involved relations information is stored in the **Field** system table, which is not fully accessible to the application.  
    > You must add such types of tables manually by following step 4 in this procedure.  

8.  To modify the resulting list of tables, select a table that you want to remove, and then choose the **Delete** action.  
9. Repeat the steps for each table that you want to add to the configuration.  
10. To remove duplicate table information that can result from using the **Get Related Tables** action, choose the **Delete Duplicate Lines** action. This will remove duplicate tables that have the same package code.  

## To add multiple tables to the configuration worksheet  
1. Choose the **Get Tables** action. The **Get Config. Tables** batch job page opens.  
2. On the **Options** FastTab, specify the types of tables that you want to add to the configuration, as described in the following table.

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Include with Data Only**|Select the check box to include only those tables that contain data. For example, you may want to include a table that already defines the typical payment terms that your solution supports.|  
    |**Include Related Tables**|Select the check box to include all related tables. To add a subset of related tables, see step 3 in this procedure.|  
    |**Include Dimension Tables**|Select the check box to include dimension tables.|  
    |**Include Licensed Tables Only**|Select the check box to include only those tables for which the license under which you are creating the worksheet allows you access.|

3. On the **Object** FastTab, set filters as appropriate to specify the types of tables you want to include or exclude.  
4. Choose the **OK** button. [!INCLUDE[d365fin](includes/d365fin_md.md)] tables are added to the worksheet. Each entry in the list has a line of type **Table**.  
5. To remove duplicate table information that can result from using the **Get Tables** action, choose the **Delete Duplicate Lines** action. This will remove duplicate tables that have the same package code.  
6. You can add tables to the worksheet that are related to a table you have selected. Review the information in the **Related Tables** FactBox to see whether there are missing tables. To add related tables for a specific table, select the table in the list, and then choose the **Get Related Tables** action.  

    > [!NOTE]  
    > Related tables will not be added with the **Get Related Tables** action if either of the following is true:
    > - The relation is conditional.  
    > Example: If you get related tables for the **Customer** table, then the **Location** table will not be added, since it is only conditionally related to the **Customer** table, namely if the **Location Code** field in the **Customer** table is filled in.  
    > - The related table is filtered.  
    > Example: A field in the related table has a WHERE clause. The reason for this is that the involved relations information is stored in the **Field** virtual table and is not available in pages such as the configuration worksheet for performance reasons.  
    > You must add related tables with such complex relationships manually by following step 4 in [To add a table to the worksheet](admin-how-to-manage-company-configuration-in-a-worksheet.md#to-add-a-table-to-the-worksheet).

7. To delete tables in the resulting list of tables, select a table to remove, and then choose the **Delete** action.  

Use the next procedure to specify which table fields to include. After you make this specification, you can export the table to Excel, and use the table structure as a template for gathering customer data. For more information, see [Prepare to Migrate Customer Data](admin-use-templates-to-prepare-customer-data-for-migration.md).  

## To specify a set of fields and records for a configuration table  
1. Select a table in the list of configuration tables, and then chose the **Edit List** action.  
2. Select a table for which you want to specify field information, and then choose the **Fields** action.  
3. To select just the fields that you want to include, choose the **Clear Included** action. To add all fields, choose the **Set Included** action.  
4. o specify that the field data should not be validated, clear the **Validate Field** check box for the field.  
5. Choose the **OK** button.  
6. To filter to a certain set of records to include in the configuration worksheet, choose the **Filters** action, and then specify the appropriate filter values.

You can create areas of functionality and groups of tables in the worksheet in order to put similar functionality together. For example, in setting up the chart of accounts for your configuration, you may decide to create a group of posting tables. Typically, areas are used to group a set of tables that correspond to a functional area. Each area can contain groups. A group can be used to arrange tables that have a common meaning together.  

The following procedure describes how to add area and group designations, after you have created the initial list of tables. After you have added these categories, you can continue to add and modify your list of tables.  

## To categorize and group functionality in the worksheet  
1. At the beginning of an area, insert a new line in the worksheet.  
2. In the **Line Type** field, choose **Area**. In the **Name** field, enter a name for the area.  
3. At the beginning of a grouping of tables, insert a new line in the worksheet.  
4. In the **Line Type** field, choose **Group**. In the **Name** field, enter a name for the area. The group name is automatically indented.  
5. To move tables to the appropriate category, select a table to move, and then choose the **Move Up** or **Move Down** action. Alternatively, you can delete a worksheet line and insert the table again in the required location.  

Some [!INCLUDE[d365fin](includes/d365fin_md.md)] tables are standard and the data in these is not likely to change from implementation to implementation. Consequently, to help your customer focus, you can remove these tables from the worksheet after you have included them in the configuration package. Once added, the tables remain part of the configuration package.  

## To remove a standard table in the worksheet  
After you have added all necessary tables to a configuration package, determine which tables will not require customer attention.  
1.  Select the tables, and then delete them by choosing the **Delete** action.  

    > [!NOTE]  
    >  The tables remain in the package even though they are deleted from the worksheet.  

## To review and customize existing database data
As you create a configuration package for a solution, you can view and customize the available database data to suit your customer needs. The database table has to have an associated page.  

## To customize data in the database  

1.  On the **Configuration Worksheet** page, identify the tables whose data that you want to view or customize.  

    > [!NOTE]  
    >  Make sure that each table has a page ID assigned to it. For standard [!INCLUDE[d365fin](includes/d365fin_md.md)] tables, this value is automatically filled in. For custom tables, you have to provide the ID.  

2.  Choose the **Database Data** action.  

     The [!INCLUDE[d365fin](includes/d365fin_md.md)] page for the page opens.  

3.  Review the available information. Modify it as necessary by deleting records that are not relevant or by adding new ones.

## See Also  
[Set Up Company Configuration](admin-set-up-company-configuration.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
