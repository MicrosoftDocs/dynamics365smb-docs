---
title: Exporting data for a digital audit [DE]
description: Export business data for auditing purposes following the digital audit process (GoBD/GDPdU) as per German tax regulations. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export business data, digital audit, GoBD, GDPdU, German tax regulations, German version
ms.date: 03/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Walkthrough: Exporting data for a digital audit in the German version

You can export business data for auditing purposes. How the data export is set up is different for all companies, and you should ask your tax advisor and the tax auditor. The following walkthrough describes the end-to-end process, but it's an example only.  

The sample implementation illustrates a scenario where the auditor requests that you export data from your general ledger, and information about your customers and vendors. This isn't an example that is based on actual requirements from a tax auditor, but it serves to illustrate how to export data for a digital audit (GoBD/GDPdU) in [!INCLUDE[prod_short](../../includes/prod_short.md)].  

## About this walkthrough

This walkthrough illustrates the following tasks:  

- Setting up requirements for the data export.  
- Setting up the source for the data export.  
- Exporting data for the tax auditor.  

## Prerequisites

To complete this walkthrough, you need:  

- The German version of [!INCLUDE[prod_short](../../includes/prod_short.md)] with the CRONUS AG demonstration company.
- The *.DTD* file that is required according to the GDPdU. In this scenario, **gdpdu-01-08-2002.dtd**.  

## Story

Cassie, an accountant at CRONUS AG is notified by the company's tax auditor that they want to see a list of purchase and sales transactions in the first quarter of the calendar year 2013. Cassie knows the type of financial data that the auditor wants, but needs the help of Sean to set up the export.  

Sean is a power user with CRONUS AG and understands how the data is set up technically with tables and fields. Therefore, Sean usually helps Cassie set up the data exports for the auditors. From other data exports, Sean knows that the tool that the auditors use has some requirements on what the exported files must contain, but needs the help of Cassie to establish exactly which data is needed.  

## Defining the requirements

Cassie sets up the requirements for the data export. The auditors ask for transactions with customers and vendors. Therefore, Cassie knows that data is needed from the customer ledger, the vendor ledger, and the general ledger.  

### Set up the requirements for a data export  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Export**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Data Exports** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique code for the data export, **AUDIT-Q113**.|  
    |**Description**|The description for the data export, **Data export for Q1 of CY 2013**.|  

    The **AUDIT-Q113** code is a container for the data export.  

    Next, Cassie adds descriptions of the kind of data needed in the export.  

1. On the **Data Exports** page, choose the **Record Definitions** action.  
1. On the **Data Export Record Definitions** page, choose the **Record Code** field, and then, on the page that appears, choose the **New** action.  
1. On the **Data Export Record Types** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the record type, **GLCUSTVEND**.|  
    |**Description**|The description for the record type, **G/L, Cust., Vend.**.|  

1. Choose the **OK** button.  
1. On the **Data Export Record Definitions** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Record Code**|Select the record code, **GLCUSTVEND**.|  
    |**Description**|The description for the record type is added automatically, but you can change this to **General ledger, customers and vendors**, for example.|  
    |**Export Path**|Specify the path where the exported files are stored.<br><br/> In this scenario, **C:Exports**.|  

    If the specified folder doesn't exist, choose the **Yes** button to create it.  

Next, Cassie specifies the source for the data that are exported. Cassie knows from previous exports that data is needed from the following tables:  

- **G/L Account**  
- **Customer**  
- **Vendor**  

### Specify requirements for the source for the data export  

1. On the **Data Export Record Definitions** page, choose the **Record Source** action.  
1. On the **Data Export Record Source** page, in the **Table No.** field, enter **15**.  

   The **Table Name** field is automatically updated with the name of the **G/L Account** table.  

1. In the **Notes** part, choose the link, and then enter the following text:  

    **I need entries that show the affected accounts, the posting date, the balance, and the net change.**  

1. Repeat the two previous steps to add tables 18, **Customer**, and 23, **Vendor** to the data export record source.  

    For these tables, Cassie asks for data about each customer and vendor and detailed information about each transaction based on the customer ledger and the vendor ledger. Cassie also asks for the net change at the start of the period, during the period, and after the period that the data export is for.  

1. Choose the **OK** button.  

Cassie has described the kind of data needed, and requests Sean for help with setting up the data export.  

## Setting up the source for the data export

Cassie and Sean talked about the requirements. Cassie explained the comments made for the first three tables in the record sources. The next day, Sean can complete the setup for the data export source.  

First, Sean adds the required *.dtd* file to the data export record definition.  

### Add a .dtd file to a record definition  

1. On the **Data Exports** page, choose the **AUDIT-Q113** data export, and then choose the **Record Definitions** action.  
1. On the **Data Export Record Definitions** page, choose the line where the **Data Export Record Type Code** field is set to **GLCUSTVEND**, and then choose the **Import** action.  
1. On the **Import** page, navigate to the location of the relevant DTD file, and then choose the **Open** button.  

Next, Sean adds the **G/L Entry** table to the source and then adds fields from that table, and the **G/L Account** table.  

### Add the G/L Entry table to the data export record source  

1. On the **Data Export Record Definitions** page, choose the line where the **Data Export Record Type Code** field is set to **GLCUSTVEND**, and then choose the **Record Source** action.  
1. On the **Data Export Record Source** page, select the line under the line for the **G/L Account** table, and then choose the **New** action.  
1. In the **Table No.** field, enter **17**.  

   The **Table Name** field is automatically updated with the name of the **G/L Entry** table.  

1. Choose the **Indent** action.  

   This indents the **G/L Entry** table under the **G/L Account** table. Next, Sean adds a table relationship between the two tables.  

1. Choose the **Relationships** action.  
1. On the **Data Exp. Table Relationship** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Field No.**|Contains the number of the field in the parent table. In this scenario, the **No.** field on the **G/L Account** table.|  
    |**To Field No.**|Contains the number of the field in the parent table. In this scenario, the **G/L Account No.** field on the **G/L Entry** table.|  

1. Choose the **OK** button.  

### Add fields from the G/L Account and G/L Entry tables to the data export record source  

1. On the **Data Export Record Source** page, select the line for the **G/L Account** table, and then choose the **Add** action.  
1. Choose the following fields, and then choose the **OK** button.  

    |Field number|Field name|  
    |------------------|----------------|  
    |**1**|**No.**|  
    |**2**|**Name**|  
    |**4**|**Account Type.**|  
    |**31**|**Balance at Date**|  
    |**32**|**Net Change**|  

1. On the **Data Export Record Source** page, select the line for the **G/L Entry** table, and then in the **Fields** pane, in the toolbar, choose the **Add** action.  
1. Choose the following fields, and then choose the **OK** button.  

    |Field number|Field name|  
    |------------------|----------------|  
    |**4**|**Posting Date**|  
    |**5**|**Document Type**|  
    |**17**|**Amount**|  

Sean added the **Posting Date** field from the **G/L Entry** table because Cassie needs the data to be filtered based on the posting date. Now, Sean uses the field to specify the field on the **G/L Entry** table that uses to calculate the period for the data export.  

### Add a period filter to a table in a data export source  

1. On the **Data Export Record Source** page, select the line for the **G/L Entry** table, and then choose the **Period Field No.** field.  
1. On the **Data Exp. Field List** page, choose the **Posting Date** field, and then choose the **OK** button.  

   The **Data Exp. Field List** page is filtered to show only the date fields.  

This means that when Cassie exports the data and specifies the start date and the end date for the period that the auditors want, the export includes entries where the **Posting Date** field is between the specified start date and end date.  

Next, Sean adds the **Customer** and **Vendor** tables.  

### Add the Customer table  

1. On the **Data Export Record Source** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|**18**|  
    |**Export Table Name**|**Customer**|  
    |**Export File Name**|**Customer.txt**|  

1. In the **Fields** pane, in the toolbar, choose the **Add** action.  
1. Choose the following fields, and then choose the **OK** button.  

    |Field number|Field name|  
    |------------------|----------------|  
    |**1**|**No.**|  
    |**2**|**Name**|  
    |**21**|**Customer Posting Group**|  
    |**59**|**Balance (LCY)**|  
    |**61**|**Net Change (LCY)**|  

1. Repeat the previous two steps to add the **Balance (LCY)** field again.  
1. Choose the line for the first instance of the **Balance (LCY)** field, and then, in the **Datefilter Handling** field, choose **Startdate**.  
1. Choose the line for the second instance of the **Balance (LCY)** field, and then, in the **Datefilter Handling** field, choose **Enddate**.  
1. Choose the line for the **Net Change (LCY)** field, and then, in the **Datefilter Handling** field, choose **Startdate..Enddate**.  

    The following table describes the field values for the fields on the **Customer** table.  

    |**Field No.**|**Field Name**|**Field Class**|**Datefilter Handling**|**Export Field Name**|  
    |---------------------------------------|----------------------------------------|-----------------------------------------|-------------------------------------------------|------------------------------------------------|  
    |**1**|**No.**|**Normal**||**No**|  
    |**2**|**Name**|**Normal**||**Name**|  
    |**21**|**Customer Posting Group**|**Normal**||**CustomerPostingGroup**|  
    |**59**|**Balance (LCY)**|**FlowField**|**..Startdate**|**StartBalanceLCY**|  
    |**59**|**Balance (LCY)**|**FlowField**|**..Enddate**|**EndBalanceLCY**|  
    |**61**|**Net Change (LCY)**|**FlowField**|**Startdate..Enddate**|**NetChangeLCYPeriod**|  

    > [!TIP]  
    > To change the order of the fields, select a field, and then choose the **Move Up** or the  **Move Down** action.  

Sean added the **Customer** table to the data export source. Now, he adds the **Vendor** table.  

### Add the Vendor table  

1. On the **Data Export Record Source** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|**23**|  
    |**Export Table Name**|**Vendor**|  
    |**Export File Name**|**Vendor.txt**|  

1. Follow the steps in the previous procedure to add fields from the **Vendor** table to the data export source.  

    The following table describes the field values for the fields in the **Vendor** table.  

    |**Field No.**|**Field Name**|**Field Class**|**Datefilter Handling**|**Export Field Name**|  
    |---------------------------------------|----------------------------------------|-----------------------------------------|-------------------------------------------------|------------------------------------------------|  
    |**1**|**No.**|**Normal**||**No**|  
    |**2**|**Name**|**Normal**||**Name**|  
    |**21**|**Vendor Posting Group**|**Normal**||**VendorPostingGroup**|  
    |**59**|**Balance (LCY)**|**FlowField**|**..Startdate**|**StartBalanceLCY**|  
    |**59**|**Balance (LCY)**|**FlowField**|**..Enddate**|**EndBalanceLCY**|  
    |**61**|**Net Change (LCY)**|**FlowField**|**Startdate..Enddate**|**NetChangeLCYPeriod**|  

Sean almost completes the setup, but wants to verify that the data export source meets the technical requirements of the auditors' tool.  

### Validate the data export source  

Choose the **Validate** action.  

Sean now completes the setup of the data export based on the requirements from Cassie. Sean notifies Cassie to start exporting data for the tax auditors.  

## Exporting data for the tax auditors

Cassie wants to export data that can be sent to the tax auditors.  

### Export data  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export Business Data**, and then choose the related link.  
1. On the **Export Business Data** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|The start date. In this scenario, **01-01-2018**.|  
    |**Ending Date**|The end date. In this scenario, **03-31-2018**.|  

1. On the **Data Export Record Definition** FastTab, select filters as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Data Export Code**|In this scenario, **AUDIT-Q113**.|  
    |**Data Exp. Rec. Type Code**|In this scenario, **GLCUSTVEND**.|  

1. To export the data, choose the **OK** button.  

When the export is completed, Cassie is notified, and can now submit the exported files to the tax auditors. First, Cassie examines the files in the C:Exports folder on the computer. There's a file for each table, and the files have the names that Sean specified in the data export source. There's also an *INDEX.XML* file that describes the structure of the data export with the names of the tables and fields that Sean specified.  

## Next steps

When the tax auditors import Cassie's files into their software, they can read the data that was exported. If the auditors need a new version of the same data export, Cassie can run the export again.  

The next time the tax auditors request new data, Cassie, and Sean can collaborate to create a new data export.  

## Related information

- [Process for Digital Audits (GoBD/GDPdU)](process-for-digital-audits.md)  
- [Set Up Data Exports for a Digital Audit (GoBD/GDPdU)](how-to-set-up-data-exports-for-digital-audits.md)  
- [Export Data for a Digital Audit](how-to-export-data-for-a-digital-audit.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
