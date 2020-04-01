---
    title: Walkthrough - Exporting Data for a Digital Audit
    description: You can export business data for auditing purposes according to the process for digital audits (GoBD/GDPdU). The following walkthrough describes the end-to-end process, but it is an example only.
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
# Walkthrough: Exporting Data for a Digital Audit
You can export business data for auditing purposes. How the data export is set up is different for all companies, and you should ask your tax advisor and the tax auditor. The following walkthrough describes the end-to-end process, but it is an example only.  

The sample implementation illustrates a scenario where the auditor has requested that you export data from your general ledger, and information about your customers and vendors. This is not an example that is based on actual requirements from a tax auditor, but it serves to illustrate how to export data for a digital audit (GoBD/GDPdU) in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

## About This Walkthrough  
This walkthrough illustrates the following tasks:  

- Setting up requirements for the data export.  
- Setting up the source for the data export.  
- Exporting data for the tax auditor.  

## Prerequisites  
To complete this walkthrough, you will need:  

- The German version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)] with the CRONUS AG demonstraltion company.
- The .DTD file that is required according to the GDPdU. In this scenario, **gdpdu-01-08-2002.dtd**.  

## Story  
Cassie is an accountant at CRONUS AG. She has been notified by the company’s tax auditor that they want to see a list of purchase and sales transactions in the first quarter of the calendar year 2013. Cassie knows the type of financial data that the auditor wants, but she needs the help of Sean to set up the export.  

Sean is a power user with CRONUS AG. He understands how the data is set up technically with tables and fields. Therefore he usually helps Cassie set up the data exports for the auditors. From other data exports, he knows that the tool that the auditors use has some requirements on what the exported files must contain, but he needs the help of Cassie to establish exactly which data is needed.  

## Defining the Requirements  
Cassie sets up the requirements for the data export. The auditors have asked her for transactions with customers and vendors. Therefore she knows that she needs data from the customer ledger, the vendor ledger, and the general ledger.  

### To set up the requirements for a data export  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Export**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **Data Exports** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The unique code for the data export, **AUDIT-Q113**.|  
    |**Description**|The description for the data export, **Data export for Q1 of CY 2013**.|  

    The **AUDIT-Q113** code is a container for the data export.  

    Next, Cassie adds descriptions of the kind of data that she needs in the export.  

4.  On the **Data Exports** page, choose the **Record Definitions** action.  
5.  On the **Data Export Record Definitions** page, choose the **Record Code** field, and then, on the page that appears, choose the **New** action.  
6.  On the **Data Export Record Types** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the record type, **GLCUSTVEND**.|  
    |**Description**|The description for the record type, **G/L, Cust., Vend.**.|  

7.  Choose the **OK** button.  
8.  On the **Data Export Record Definitions** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Record Code**|Select the record code, **GLCUSTVEND**.|  
    |**Description**|The description for the record type is added automatically, but you can change this to **General ledger, customers and vendors**, for example.|  
    |**Export Path**|Specify the path where the exported files will be stored.<br /><br /> In this scenario, **C:Exports**.|  

    If the specified folder does not exist, choose the **Yes** button to create it.  

Next, Cassie specifies the source for the data that will be exported. She knows from previous exports that she wants data from the following tables:  

- **G/L Account**  
- **Customer**  
- **Vendor**  

### To specify requirements for the source for the data export  

1.  On the **Data Export Record Definitions** page, choose the **Record Source** action.  
2.  On the **Data Export Record Source** page, in the **Table No.** field, enter **15**.  

    The **Table Name** field is automatically updated with the name of the **G/L Account** table.  

3.  In the **Notes** part, choose the link, and then enter the following text:  

    **I need entries that show the affected accounts, the posting date, the balance, and the net change.**  

4.  Repeat the two previous steps to add tables 18, **Customer**, and 23, **Vendor** to the data export record source.  

    For these tables, Cassie asks for data about each customer and vendor and detailed information about each transaction based on the customer ledger and the vendor ledger. She also asks for the net change at the start of the period, during the period, and after the period that the data export is for.  

5.  Choose the **OK** button.  

Cassie has described the kind of data that she needs, and she notifies Sean that she wants his help is setting up the data export.  

## Setting Up the Source for the Data Export  
Cassie and Sean have talked about the requirements. Cassie has explained what she means with the comments she has made for the first three tables in the record sources. The next day, Sean can complete the setup for the data export source.  

First, Sean adds the required .dtd file to the data export record definition.  

### To add a .dtd file to a record definition  

1.  On the **Data Exports** page, choose the **AUDIT-Q113** data export, and then choose the **Record Definitions** action.  
2.  On the **Data Export Record Definitions** page, choose the line where the **Data Export Record Type Code** field is set to **GLCUSTVEND**, and then choose the **Import** action.  
3.  On the **Import** page, navigate to the location of the relevant DTD file, and then choose the **Open** button.  

Next, Sean adds the **G/L Entry** table to the source. Then he adds fields from that table and the **G/L Account** table.  

### To add the G/L Entry table to the data export record source  

1.  On the **Data Export Record Definitions** page, choose the line where the **Data Export Record Type Code** field is set to **GLCUSTVEND**, and then choose the **Record Source** action.  
2.  On the **Data Export Record Source** page, select the line under the line for the **G/L Account** table, and then choose the **New** action.  
3.  In the **Table No.** field, enter **17**.  

    The **Table Name** field is automatically updated with the name of the **G/L Entry** table.  

4.  Choose the **Indent** action.  

    This indents the **G/L Entry** table under the **G/L Account** table. Next, Sean adds a table relationship between the two tables.  

5.  Choose the **Relationships** action.  
6.  On the **Data Exp. Table Relationship** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Field No.**|Contains the number of the field in the parent table. In this scenario, the **No.** field on the **G/L Account** table.|  
    |**To Field No.**|Contains the number of the field in the parent table. In this scenario, the **G/L Account No.** field on the **G/L Entry** table.|  

7.  Choose the **OK** button.  

### To add fields from the G/L Account and G/L Entry tables to the data export record source  

1.  On the **Data Export Record Source** page, select the line for the **G/L Account** table, and then choose the **Add** action.  
2.  Choose the following fields, and then choose the **OK** button.  

    |Field number|Field name|  
    |------------------|----------------|  
    |1|**No.**|  
    |2|**Name**|  
    |4|**Account Type.**|  
    |31|**Balance at Date**|  
    |32|**Net Change**|  

3.  On the **Data Export Record Source** page, select the line for the **G/L Entry** table, and then in the **Fields** pane, in the toolbar, choose the **Add** action.  
4.  Choose the following fields, and then choose the **OK** button.  

    |Field number|Field name|  
    |------------------|----------------|  
    |4|**Posting Date**|  
    |5|**Document Type**|  
    |17|**Amount**|  

Sean added the **Posting Date** field from the **G/L Entry** table because Cassie needs the data to be filtered based on the posting date. Now, Sean will use the field to specify the field on the **G/L Entry** table that will be used to calculate the period for the data export.  

### To add a period filter to a table in a data export source  

1.  On the **Data Export Record Source** page, select the line for the **G/L Entry** table, and then choose the **Period Field No.** field.  
2.  On the **Data Exp. Field List** page, choose the **Posting Date** field, and then choose the **OK** button.  

    The **Data Exp. Field List** page is filtered to show only the date fields.  

This means that when Cassie exports the data and specifies the start date and the end date for the period that the auditors want, the export will include entries where the **Posting Date** field is between the specified start date and end date.  

Next, Sean adds the **Customer** and **Vendor** tables.  

### To add the Customer table  

1.  On the **Data Export Record Source** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|**18**|  
    |**Export Table Name**|**Customer**|  
    |**Export File Name**|**Customer.txt**|  

2.  In the **Fields** pane, in the toolbar, choose the **Add** action.  
3.  Choose the following fields, and then choose the **OK** button.  

    |Field number|Field name|  
    |------------------|----------------|  
    |1|**No.**|  
    |2|**Name**|  
    |21|**Customer Posting Group**|  
    |59|**Balance (LCY)**|  
    |61|**Net Change (LCY)**|  

4.  Repeat the previous two steps to add the **Balance (LCY)** field again.  
5.  Choose the line for the first instance of the **Balance (LCY)** field, and then, in the **Datefilter Handling** field, choose **Startdate**.  
6.  Choose the line for the second instance of the **Balance (LCY)** field, and then, in the **Datefilter Handling** field, choose **Enddate**.  
7.  Choose the line for the **Net Change (LCY)** field, and then, in the **Datefilter Handling** field, choose **Startdate..Enddate**.  

    The following table describes the field values for the fields on the **Customer** table.  

    |**Field No.**|**Field Name**|**Field Class**|**Datefilter Handling**|**Export Field Name**|  
    |---------------------------------------|----------------------------------------|-----------------------------------------|-------------------------------------------------|------------------------------------------------|  
    |1|**No.**|**Normal**||**No**|  
    |2|**Name**|**Normal**||**Name**|  
    |21|**Customer Posting Group**|**Normal**||**CustomerPostingGroup**|  
    |59|**Balance (LCY)**|**FlowField**|**..Startdate**|**StartBalanceLCY**|  
    |59|**Balance (LCY)**|**FlowField**|**..Enddate**|**EndBalanceLCY**|  
    |61|**Net Change (LCY)**|**FlowField**|**Startdate..Enddate**|**NetChangeLCYPeriod**|  

    > [!TIP]  
    >  To change the order of the fields, select a field, and then choose the **Move Up** or the  **Move Down** action.  

Sean has added the **Customer** table to the data export source. Now, he adds the **Vendor** table.  

### To add the Vendor table  

1.  On the **Data Export Record Source** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table No.**|**23**|  
    |**Export Table Name**|**Vendor**|  
    |**Export File Name**|**Vendor.txt**|  

2.  Follow the steps in the previous procedure to add fields from the **Vendor** table to the data export source.  

     The following table describes the field values for the fields in the **Vendor** table.  

    |**Field No.**|**Field Name**|**Field Class**|**Datefilter Handling**|**Export Field Name**|  
    |---------------------------------------|----------------------------------------|-----------------------------------------|-------------------------------------------------|------------------------------------------------|  
    |1|**No.**|**Normal**||**No**|  
    |2|**Name**|**Normal**||**Name**|  
    |21|**Vendor Posting Group**|**Normal**||**VendorPostingGroup**|  
    |59|**Balance (LCY)**|**FlowField**|**..Startdate**|**StartBalanceLCY**|  
    |59|**Balance (LCY)**|**FlowField**|**..Enddate**|**EndBalanceLCY**|  
    |61|**Net Change (LCY)**|**FlowField**|**Startdate..Enddate**|**NetChangeLCYPeriod**|  

Sean has almost completed the setup, but he wants to verify that the data export source meets the technical requirements of the auditors’ tool.  

### To validate the data export source  

Choose the **Validate** action.  

Sean has now completed the setup of the data export based on the requirements from Cassie. He notifies her that she can start exporting data for the tax auditors.  

## Exporting Data for the Tax Auditors  
Cassie wants to export data that she can then send to the tax auditors.  

### To export data  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export Business Data**, and then choose the related link.  
2.  On the **Export Business Data** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|The start date. In this scenario, **01-01-2018**.|  
    |**Ending Date**|The end date. In this scenario, **03-31-2018**.|  

3.  On the **Data Export Record Definition** FastTab, select filters as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Data Export Code**|In this scenario, **AUDIT-Q113**.|  
    |**Data Exp. Rec. Type Code**|In this scenario, **GLCUSTVEND**.|  

4.  To export the data, choose the **OK** button.  

When the export is completed, Cassie is notified. She can now submit the exported files to the tax auditors. First, she examines the files in the C:Exports folder on her computer. There is a file for each table, and the files have the names that Sean specified in the data export source. There is also an INDEX.XML file that describes the structure of the data export with the names of the tables and fields that Sean specified.  

## Next Steps  
When the tax auditors import Cassie’s files into their software, they can read the data that she exported. If the auditors need a new version of the same data export, Cassie can run the export again.  

The next time the tax auditors request new data, Cassie and Sean can collaborate to create a new data export.  

## See Also  
 [Process for Digital Audits](process-for-digital-audits.md)   
 [Set Up Data Exports for Digital Audits](how-to-set-up-data-exports-for-digital-audits.md)   
 [Export Data for a Digital Audit](how-to-export-data-for-a-digital-audit.md) 
 
