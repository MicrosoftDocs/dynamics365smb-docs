---
title: "How to: Set Up Data Exports for GDPdU"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "data export, setting up GDPdU"
  - "GDPdU, setting up"
  - "export data, setting up"
ms.assetid: 9c7bcb2f-613f-4805-94c3-cb5e6c4473c8
caps.latest.revision: 49
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Set Up Data Exports for GDPdU
You must set up data export record sources to be able to export Grundsätze zum Datenzugriff und zur Prüfkbarkeit digtaler Unterlagen \(GDPdU\) data. For each data export type, you must define one or more record sources, where each source is a table from which you want to export data.  
  
### To set up a GDPdU data export  
  
1.  In the **Search** box, enter **Data Exports**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **Data Exports** window, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> --> --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> --> --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the unique code for the data export, such as **Export\-1**.|  
    |**Description**|Specify the description for the data export.|  
  
 You must add record definitions to the data export. Each record definition represents a set of data that will be exported.  
  
### To add a record definition to a GDPdU definition group  
  
1.  In the **Data Exports** window, on the **Home** tab, choose **Record Definitions**.  
  
2.  In the **Data Export Record Definitions** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Data Export Code**|Select the data export code.<br /><br /> If no data export code exists, you can create a new one.|  
    |**Description**|Specify the description for the record definition.|  
    |**Export Path**|Specify the path where the exported files will be stored.|  
  
     Next, you must add the relevant .dtd file that is required according to the GDPdU, such as **gdpdu\-01\-08\-2002.dtd**. If you must import a new DTD file to replace an existing file, you must first export the existing DTD file.  
  
3.  On the **Home** tab, in the **DTD File** group, choose **Import**.  
  
4.  In the **Import** window, navigate to the location of the relevant DTD file, and then choose the **Open** button.  
  
 Next, you must specify the source for the data that will be exported.  
  
### To add source tables to a data export  
  
1.  In the **Data Export Record Definitions** window, on the **Home** tab, choose **Record Source**.  
  
2.  In the **Data Export Record Source** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|Select the number of the main table to export data from.<br /><br /> When you enter a value in the **Table No.** field, the **Table Name** field is updated.|  
    |**Export Table Name**|Optional. Change the suggested name of the table to be used in the INDEX.XML file during the export.<br /><br /> The value of the **Export Table Name** field is used to generate the INDEX.XML file during the GDPdU data export. The default name is the name of the table without special characters due to the requirements of the auditors’ tool.<br /><br /> **Tip:** In most cases, the **Export Table Name** and **Export File Name** fields are based on the same value.<br /><br /> There may be cases where you specify exporting the same table more than once. You can choose different Export Table Names for each table entry, and the Export File Name will be automatically adjusted to match. You can then change the Export File Name as long as it is unique.<br /><br /> FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> automatically names the files as follows.<br /><br /> **Table Name:** G\/L Account<br /><br /> **Export Table Name**: GLAccount<br /><br /> **Export File Name:** GLAccount.txt<br /><br /> **Table Name:** G\/L Account<br /><br /> **Export Table Name:** GLAccount1<br /><br /> **Export File Name:** GLAccount1.txt|  
    |**Period Field No.**|Specify a filter for which date field will be used in setting the start date and end date of the report.<br /><br /> For example, if you select the **G\/L Entry** table as your data export source, you can select one of the date fields that are available in that table.|  
    |**Table Filter**|Specify a field on which you want to set a filter.<br /><br /> In the **Table Filter** window, enter filter settings in the **Field Filter** column.<br /><br /> For example, you can specify a field that conveys information about the amount. You can also specify a date field and set a filter for it if you want to filter on a time period other than Start Date .. End Date. However, you cannot specify a date field and set a filter for it if the same field is already used in the Period Field No.|  
    |**Date Filter Field No.**|Specify a date filter field if the table has one.<br /><br /> If the table has more than one date filter, do not specify one in this field.|  
    |**Date Filter Handing**|Specify how the date filter is to be handled:<br /><br /> \* \<blank\>: No filter is set.<br /><br /> \* Period: Use the specified Start Date and End Date.<br /><br /> \* End Date Only: Use the batch job's End Date.<br /><br /> \* Start Date Only: Use the batch job's Start Date \- 1.|  
    |**Export File Name**|Specify the name of the file that data from this table will be exported to.<br /><br /> For example, if the table is the **G\/L Account** table, the value of the **Export Table Name** can be **GLAccount**, and the value of the **Export File Name** field can be **GLAccount.txt**.|  
    |**Key No.**|Optional. Specify the key field.|  
  
     For more information on setting filters, see [GDPdU Filter Examples](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/gdpdu-filter-examples.md).  
  
     Next, you must specify the fields that data will be exported from.  
  
3.  In the **Fields** pane, choose **Add**.  
  
4.  In the **Data Exp. Field List** window, select one or more fields that you want to export, and then choose the **OK** button.  
  
    1.  To change the order of the fields, choose **Move Up** or **Move Down**.  
  
    2.  To remove a field from the list of selected fields, choose **Delete**.  
  
 You have added the main table from which to export. Optionally, you can add one or more related tables.  
  
### To add related tables to a data export source  
  
1.  In the **Data Export Record Source** window, in the line below the line for the main table, add the related table.  
  
2.  On the **Home** tab, in the **Indentation** group, choose **Indent**.  
  
3.  Select the indented table, and then on the **Home** tab, in the **Indentation** group, choose **Relationships**.  
  
4.  In the **GDPdU Table Relation** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**From Field No.**|Contains the number of the field in the parent table. You can specify that this field is related to a field in the subordinate table.|  
    |**To Field No.**|Contains the number of the field in the subordinate table. You can specify that a field in the parent table is related to this field.|  
  
    > [!NOTE]  
    >  The **From Field Name** and the **To Field Name** fields are populated automatically.  
  
5.  Choose the **OK** button.  
  
 After you have added tables and fields, you must validate that the structure of the data export source is correct.  
  
### To validate the data export source  
  
-   In the **Data Exp. Record Source** window, on the **Home** tab, in the **Process** group, choose **Validate**.  
  
     This validates the list of fields against the keys for the tables. If you select a primary key after you select a secondary key, an error message displays, and you must change the order of the fields in the **Fields** pane.  
  
## See Also  
 [Process for Data Access and Testability of Digital Documents \(GDPdU\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/process-for-data-access-and-testability-of-digital-documents-gdpdu-.md)   
 [How to: Export GDPdU Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-export-gdpdu-data.md)   
 [GDPdU Filter Examples](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/gdpdu-filter-examples.md)