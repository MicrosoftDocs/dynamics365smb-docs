---
title: Set Up Data Exports for a Digital Audit [DE]
description: Set up data export record sources to export data for a digital audit according to GDPdU requirements.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: GDPdU, data export, digital audit, German version
ms.date: 03/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up data exports for a digital audit (GoBD/GDPdU) in the German Version

You must set up data export record sources to be able to export data for a digital audit according to the Grundsätze zum Datenzugriff und zur Prüfbarkeit digitaler Unterlagen (GDPdU). For each data export type, you must define one or more record sources, where each source is a table from which you want to export data.

> [!NOTE]  
> When someone opens **Data Exports** page for the first time, three data export records with predefined settings are created with the codes **GLAcc 2022**, **FAAcc 2022**, and **Item 2022**. Consider these data export records ready-made templates for exporting data from [!INCLUDE[prod_short](../../includes/prod_short.md)] according to government requirements.
>
> - **GLAcc 2022** can be used to export data related to G/L and personal data.
> - **FAAcc 2022** can be used to export data related to fixed asset data.
> - **Item 2022** can be used to export data related to item and invoice data.

## Set up a data export  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exports**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Data Exports** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Code**|Specify the unique code for the data export, such as **Export-1**.|  
    |**Description**|Specify the description for the data export.|  

You must add record definitions to the data export. Each record definition represents a set of data that is exported.  

## Add a record definition to a digital audit definition group  

1. On the **Data Exports** page, choose the **Record Definitions** action.  
1. On the **Data Export Record Definitions** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Data Export Code**|Select the data export code.<br><br/> If no data export code exists, you can create a new one.|  
    |**Description**|Specify the description for the record definition.|  
    |**Export Path**|Specify the path where the exported files are stored.|  

    Next, you must add the relevant *.dtd* file that is required according to the GDPdU, such as **gdpdu-01-08-2002.dtd**. If you must import a new DTD file to replace an existing file, you must first export the existing DTD file.  

1. Choose the **Import** action.  
1. On the **Import** page, navigate to the location of the relevant DTD file, and then choose the **Open** button.  

Next, you must specify the source for the data that is exported.  

## Add source tables to a data export  

1. On the **Data Export Record Definitions** page, choose the **Record Source** action.  
1. On the **Data Export Record Source** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|Select the number of the main table to export data from.<br><br/> When you enter a value in the **Table No.** field, the **Table Name** field is updated.|  
    |**Export Table Name**|Optional. An archive file with the necessary data is created, containing an *INDEX.XML* file. You can change the suggested name of the table to be used in the `INDEX.XML` file during the export. The default name is the name of the table without special characters due to the requirements of the auditors' tool.<br><br/> **Tip:** In most cases, the **Export Table Name** and **Export File Name** fields are based on the same value.<br><br/> There may be cases where you specify exporting the same table more than once. You can choose different Export Table Names for each table entry, and the Export File Name is automatically adjusted to match. You can then change the Export File Name as long as it's unique.<br><br/> [!INCLUDE[prod_short](../../includes/prod_short.md)] automatically names the files as follows.<br><br/> **Table Name:** G/L Account<br><br/> **Export Table Name**: GLAccount<br><br/> **Export File Name:** GLAccount.txt<br><br/> **Table Name:** G/L Account<br><br/> **Export Table Name:** GLAccount1<br><br/> **Export File Name:** GLAccount1.txt|  
    |**Period Field No.**|Specify a filter for which date field is used in setting the start date and end date of the report.<br><br/> For example, if you select the **G/L Entry** table as your data export source, you can select one of the date fields that are available in that table.|  
    |**Table Filter**|Specify a field on which you want to set a filter.<br><br/> On the **Table Filter** page, enter filter settings in the **Field Filter** column.<br><br/> For example, you can specify a field that conveys information about the amount. You can also specify a date field and set a filter for it if you want to filter on a time period other than Start Date .. End Date. However, you can't specify a date field and set a filter for it if the same field is already used in the **Period Field No.**|  
    |**Date Filter Field No.**|Specify a date filter field if the table has one.<br><br/> If the table has more than one date filter, don't specify one in this field.|  
    |**Date Filter Handing**|Specify how the date filter is to be handled:<br><br/> - \<blank\>: No filter is set.<br><br/> - Period: Use the specified Start Date and End Date.<br><br/> - End Date Only: Use the batch job's End Date.<br><br/> - Start Date Only: Use the batch job's Start Date - 1.|  
    |**Export File Name**|Specify the name of the file that data from this table is exported to.<br><br/> For example, if the table is the **G/L Account** table, the value of the **Export Table Name** can be **GLAccount**, and the value of the **Export File Name** field can be **GLAccount.txt**.|  
    |**Key No.**|Optional. Specify the key field.|

    > [!NOTE]  
    > The INDEX.XML file contains table and field names in English based on the names of tables and fields. The names of tables and fields are defined in `<Name>` tags, and captions are defined in `<Description>` tags in the *INDEX.xml* file.
    > [!NOTE]  
    > Table and field names is written as-is, including any spaces, dots, parentheses, and so on. The only characters that are removed from the names are *&*, *'* (single quote), *"* (double quote), *<* (less-than sign), and *>* (greater-than sign).

    Learn more in [GDPdU Filter Examples](gdpdu-filter-examples.md).  

    Next, you must specify the fields that data is exported from.  

1. In the **Fields** pane, choose the **Add** action.  
1. On the **Data Exp. Field List** page, select one or more fields that you want to export, and then choose the **OK** button.  

    1. To change the order of the fields, choose the **Move Up** or the **Move Down** action.  
    1. To remove a field from the list of selected fields, choose the **Delete** action.  

You added the main table from which to export. Optionally, you can add one or more related tables.  

## Add related tables to a data export source  

1. On the **Data Export Record Source** page, in the line below the line for the main table, add the related table.  
1. Choose the **Indent** action.  
1. Select the indented table, and then choose the **Relationships** action.  
1. On the **Data Export Table Relation** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Field No.**|Contains the number of the field in the parent table. You can specify that this field is related to a field in the subordinate table.|  
    |**To Field No.**|Contains the number of the field in the subordinate table. You can specify that a field in the parent table is related to this field.|  

    > [!NOTE]  
    > The **From Field Name** and the **To Field Name** fields are populated automatically.  

1. Choose the **OK** button.  

After you added tables and fields, you must validate that the structure of the data export source is correct.  

## Validate the data export source  

On the **Data Exp. Record Source** page, choose the **Validate** action.  

This validates the list of fields against the keys for the tables. If you select a primary key after you select a secondary key, an error message displays, and you must change the order of the fields in the **Fields** pane.

## Related information

- [Process for Digital Audits (GoBD/GDPdU)](process-for-digital-audits.md)  
- [Export Data for a Digital Audit](how-to-export-data-for-a-digital-audit.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
