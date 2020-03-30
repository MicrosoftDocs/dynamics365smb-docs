---
    title: Set Up Data Exports for a Digital Audit
    description: You must set up data export record sources to be able to export data for a digital audit.
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
# Set Up Data Exports for a Digital Audit
You must set up data export record sources to be able to export data for a digital audit. For each data export type, you must define one or more record sources, where each source is a table from which you want to export data.  

## To set up a data export  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Exports**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **Data Exports** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the unique code for the data export, such as **Export-1**.|  
    |**Description**|Specify the description for the data export.|  

You must add record definitions to the data export. Each record definition represents a set of data that will be exported.  

## To add a record definition to a digital audit definition group  

1.  On the **Data Exports** page, choose the **Record Definitions** action.  
2.  On the **Data Export Record Definitions** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Data Export Code**|Select the data export code.<br /><br /> If no data export code exists, you can create a new one.|  
    |**Description**|Specify the description for the record definition.|  
    |**Export Path**|Specify the path where the exported files will be stored.|  

    Next, you must add the relevant .dtd file that is required according to the GDPdU, such as **gdpdu-01-08-2002.dtd**. If you must import a new DTD file to replace an existing file, you must first export the existing DTD file.  

3.  Choose the **Import** action.  
4.  On the **Import** page, navigate to the location of the relevant DTD file, and then choose the **Open** button.  

Next, you must specify the source for the data that will be exported.  

## To add source tables to a data export  

1.  On the **Data Export Record Definitions** page, choose the **Record Source** action.  
2.  On the **Data Export Record Source** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|Select the number of the main table to export data from.<br /><br /> When you enter a value in the **Table No.** field, the **Table Name** field is updated.|  
    |**Export Table Name**|Optional. Change the suggested name of the table to be used in the INDEX.XML file during the export.<br /><br /> The value of the **Export Table Name** field is used to generate the INDEX.XML file during the GDPdU data export. The default name is the name of the table without special characters due to the requirements of the auditors’ tool.<br /><br /> **Tip:** In most cases, the **Export Table Name** and **Export File Name** fields are based on the same value.<br /><br /> There may be cases where you specify exporting the same table more than once. You can choose different Export Table Names for each table entry, and the Export File Name will be automatically adjusted to match. You can then change the Export File Name as long as it is unique.<br /><br /> [!INCLUDE[d365fin](../../includes/d365fin_md.md)] automatically names the files as follows.<br /><br /> **Table Name:** G/L Account<br /><br /> **Export Table Name**: GLAccount<br /><br /> **Export File Name:** GLAccount.txt<br /><br /> **Table Name:** G/L Account<br /><br /> **Export Table Name:** GLAccount1<br /><br /> **Export File Name:** GLAccount1.txt|  
    |**Period Field No.**|Specify a filter for which date field will be used in setting the start date and end date of the report.<br /><br /> For example, if you select the **G/L Entry** table as your data export source, you can select one of the date fields that are available in that table.|  
    |**Table Filter**|Specify a field on which you want to set a filter.<br /><br /> On the **Table Filter** page, enter filter settings in the **Field Filter** column.<br /><br /> For example, you can specify a field that conveys information about the amount. You can also specify a date field and set a filter for it if you want to filter on a time period other than Start Date .. End Date. However, you cannot specify a date field and set a filter for it if the same field is already used in the Period Field No.|  
    |**Date Filter Field No.**|Specify a date filter field if the table has one.<br /><br /> If the table has more than one date filter, do not specify one in this field.|  
    |**Date Filter Handing**|Specify how the date filter is to be handled:<br /><br /> * <blank>: No filter is set.<br /><br /> * Period: Use the specified Start Date and End Date.<br /><br /> * End Date Only: Use the batch job's End Date.<br /><br /> * Start Date Only: Use the batch job's Start Date - 1.|  
    |**Export File Name**|Specify the name of the file that data from this table will be exported to.<br /><br /> For example, if the table is the **G/L Account** table, the value of the **Export Table Name** can be **GLAccount**, and the value of the **Export File Name** field can be **GLAccount.txt**.|  
    |**Key No.**|Optional. Specify the key field.|

    For more information, see [GDPdU Filter Examples](gdpdu-filter-examples.md).  

    Next, you must specify the fields that data will be exported from.  

3.  In the **Fields** pane, choose the **Add** action.  
4.  On the **Data Exp. Field List** page, select one or more fields that you want to export, and then choose the **OK** button.  

    1. To change the order of the fields, choose the **Move Up** or the **Move Down** action.  
    2. To remove a field from the list of selected fields, choose the **Delete** action.  

You have added the main table from which to export. Optionally, you can add one or more related tables.  

## To add related tables to a data export source  

1.  On the **Data Export Record Source** page, in the line below the line for the main table, add the related table.  
2.  Choose the **Indent** action.  
3.  Select the indented table, and then choose the **Relationships** action.  
4.  On the **Data Export Table Relation** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Field No.**|Contains the number of the field in the parent table. You can specify that this field is related to a field in the subordinate table.|  
    |**To Field No.**|Contains the number of the field in the subordinate table. You can specify that a field in the parent table is related to this field.|  

    > [!NOTE]  
    >  The **From Field Name** and the **To Field Name** fields are populated automatically.  

5.  Choose the **OK** button.  

After you have added tables and fields, you must validate that the structure of the data export source is correct.  

## To validate the data export source  

On the **Data Exp. Record Source** page, choose the **Validate** action.  

This validates the list of fields against the keys for the tables. If you select a primary key after you select a secondary key, an error message displays, and you must change the order of the fields in the **Fields** pane.

## See Also  
[Process for Digital Audits (GoBD/GDPdU)](process-for-digital-audits.md)   
[Export Data for a Digital Audit](how-to-export-data-for-a-digital-audit.md)
