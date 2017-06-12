---
title: "Walkthrough: Exporting GDPdU Data"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "GDPdU, walkthrough"
ms.assetid: 839c69b3-dccb-477c-bbdd-e46850526ac6
caps.latest.revision: 10
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# Walkthrough: Exporting GDPdU Data
You can export business data for auditing purposes. How the data export is set up is different for all companies, and you should ask your tax advisor and the tax auditor. The following walkthrough describes the end\-to\-end process, but it is an example only.  
  
 The sample implementation illustrates a scenario where the auditor has requested that you export data from your general ledger, and information about your customers and vendors. This is not an example that is based on actual requirements from a tax auditor, but it serves to illustrate how to export data according to the process for data access and testability of digital documents \(GDPdU\) in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)].  
  
## About This Walkthrough  
 This walkthrough illustrates the following tasks:  
  
-   Setting up requirements for the data export.  
  
-   Setting up the source for the data export.  
  
-   Exporting data for the tax auditor.  
  
## Prerequisites  
 To complete this walkthrough, you will need:  
  
-   The German version of [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] with the [!INCLUDE[demo](../../ApplicationDesign/includes/demo_md.md)] AG installed. For more information, see [Demo Option](../Topic/Demo%20Option.md).  
  
-   The .DTD file that is required according to the GDPdU. In this scenario, **gdpdu\-01\-08\-2002.dtd**.  
  
## Story  
 Cassie is an accountant at [!INCLUDE[demo](../../ApplicationDesign/includes/demo_md.md)] AG. She has been notified by the company’s tax auditor that they want to see a list of purchase and sales transactions in the first quarter of the calendar year 2013. Cassie knows the type of financial data that the auditor wants, but she needs the help of Sean to set up the export.  
  
 Sean is a power user with [!INCLUDE[demo](../../ApplicationDesign/includes/demo_md.md)] AG. He understands how the data is set up technically with tables and fields. Therefore he usually helps Cassie set up the data exports for the auditors. From other data exports, he knows that the tool that the auditors use has some requirements on what the exported files must contain, but he needs the help of Cassie to establish exactly which data is needed.  
  
## Defining the Requirements  
 Cassie sets up the requirements for the data export. The auditors have asked her for transactions with customers and vendors. Therefore she knows that she needs data from the customer ledger, the vendor ledger, and the general ledger.  
  
#### To set up the requirements for a data export  
  
1.  In the **Search** box, enter **Data Export**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **\($ N\_11002 Data Exports $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11002\_1 Code $\)**|The unique code for the data export, **AUDIT\-Q113**.|  
    |**\($ T\_11002\_2 Description $\)**|The description for the data export, **Data export for Q1 of CY 2013**.|  
  
     The **AUDIT\-Q113** code is a container for the data export.  
  
     Next, Cassie adds descriptions of the kind of data that she needs in the export.  
  
4.  In the **\($ N\_11002 Data Exports $\)** window, on the **Home** tab, choose **Record Definitions**.  
  
5.  In the **\($ N\_11003 Data Export Record Definitions $\)** window, choose the **\($ T\_11003\_1 Record Code $\)** field, and then, in the window that appears, choose **New**.  
  
6.  In the **\($ N\_11014 Data Export Record Types $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11007\_1 Code $\)**|The code for the record type, **GLCUSTVEND**.|  
    |**\($ T\_11007\_2 Description $\)**|The description for the record type, **G\/L, Cust., Vend.**.|  
  
7.  Choose the **OK** button.  
  
8.  In the **\($ N\_11003 Data Export Record Definitions $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11003\_1 Record Code $\)**|Select the record code, **GLCUSTVEND**.|  
    |**\($ T\_11003\_3 Description $\)**|The description for the record type is added automatically, but you can change this to **General ledger, customers and vendors**, for example.|  
    |**\($ T\_11003\_4 Export Path $\)**|Specify the path where the exported files will be stored.<br /><br /> In this scenario, **C:\\Exports**.|  
  
     If the specified folder does not exist, choose the **Yes** button to create it.  
  
 Next, Cassie specifies the source for the data that will be exported. She knows from previous exports that she wants data from the following tables:  
  
-   **\($ T\_15 G\/L Account $\)**  
  
-   **\($ T\_18 Customer $\)**  
  
-   **\($ T\_23 Vendor $\)**  
  
#### To specify requirements for the source for the data export  
  
1.  In the **\($ N\_11003 Data Export Record Definitions $\)** window, on the **Home** tab, in the **Record Definition** group, choose **Record Source**.  
  
2.  In the **\($ N\_11004 Data Export Record Source $\)** window, in the **\($ T\_11004\_3 Table No. $\)** field, enter **15**.  
  
     The **\($ T\_11004\_4 Table Name $\)** field is automatically updated with the name of the **\($ T\_15 G\/L Account $\)** table.  
  
3.  In the **Notes** part, choose the link, and then enter the following text:  
  
     **I need entries that show the affected accounts, the posting date, the balance, and the net change.**  
  
4.  Repeat the two previous steps to add tables 18, **\($ T\_18 Customer $\)**, and 23, **\($ T\_23 Vendor $\)** to the data export record source.  
  
     For these tables, Cassie asks for data about each customer and vendor and detailed information about each transaction based on the customer ledger and the vendor ledger. She also asks for the net change at the start of the period, during the period, and after the period that the data export is for.  
  
5.  Choose the **OK** button.  
  
 Cassie has described the kind of data that she needs, and she notifies Sean that she wants his help is setting up the data export.  
  
## Setting Up the Source for the Data Export  
 Cassie and Sean have talked about the requirements. Cassie has explained what she means with the comments she has made for the first three tables in the record sources. The next day, Sean can complete the setup for the data export source.  
  
 First, Sean adds the required .dtd file to the data export record definition.  
  
#### To add a .dtd file to a record definition  
  
1.  In the **\($ N\_1002 Data Exports $\)** window, choose the **AUDIT\-Q113** data export. On the **Home** tab, choose **Record Definitions**.  
  
2.  In the **\($ N\_11003 Data Export Record Definitions $\)** window, choose the line where the **\($ T\_11003\_2 Data Export Record Type Code $\)** field is set to **GLCUSTVEND**. On the **Home** tab, in the **DTD File** group, choose **Inport**.  
  
3.  In the **Import** window, navigate to the location of the relevant DTD file, and then choose the **Open** button.  
  
 Next, Sean adds the **\($ T\_17 G\/L Entry $\)** table to the source. Then he adds fields from that table and the **\($ T\_15 G\/L Account $\)** table.  
  
#### To add the \($ T\_17 G\/L Entry $\) table to the data export record source  
  
1.  In the **\($ N\_11003 Data Export Record Definitions $\)** window, choose the line where the **\($ T\_11003\_2 Data Export Record Type Code $\)** field is set to **GLCUSTVEND**, and then, on the **Home** tab, in the **Record Definition** group, choose **Record Source**.  
  
2.  In the **\($ N\_11004 Data Export Record Source $\)** window, select the line under the line for the **\($ T\_15 G\/L Account $\)** table, and then on the **Home** tab, choose **New**.  
  
3.  In the **\($ T\_11004\_3 Table No. $\)** field, enter **17**.  
  
     The **\($ T\_11004\_4 Table Name $\)** field is automatically updated with the name of the **\($ T\_17 G\/L Entry $\)** table.  
  
4.  On the **Home** tab, in the **Indentation** group, choose **Indent**.  
  
     This indents the **\($ T\_17 G\/L Entry $\)** table under the **\($ T\_15 G\/L Account $\)** table. Next, Sean adds a table relationship between the two tables.  
  
5.  On the **Home** tab, in the **Indentation** group, choose  **Relationships**.  
  
6.  In the **\($ N\_11007 Data Exp. Table Relationship $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11006\_5 From Field No. $\)**|Contains the number of the field in the parent table. In this scenario, the **\($ T\_15\_1 No. $\)** field on the **\($ T\_15 G\/L Account $\)** table.|  
    |**\($ T\_11006\_9 To Field No. $\)**|Contains the number of the field in the parent table. In this scenario, the **\($ T\_17\_3 G\/L Account No. $\)** field on the **\($ T\_17 G\/L Entry $\)** table.|  
  
7.  Choose the **OK** button.  
  
#### To add fields from the \($ T\_15 G\/L Account $\) and \($ T\_17 G\/L Entry $\) tables to the data export record source  
  
1.  In the **\($ N\_11004 Data Export Record Source $\)** window, select the line for the **\($ T\_15 G\/L Account $\)** table, and then in the **Fields** pane, in the toolbar, choose **Add**.  
  
2.  Choose the following fields, and then choose the **OK** button.  
  
    |Field number|Field name|  
    |------------------|----------------|  
    |1|**\($ T\_15\_1 No. $\)**|  
    |2|**\($ T\_15\_2 Name $\)**|  
    |4|**\($ T\_15\_4 Account Type. $\)**|  
    |31|**\($ T\_15\_31 Balance at Date $\)**|  
    |32|**\($ T\_15\_32 Net Change $\)**|  
  
3.  In the **\($ N\_11004 Data Export Record Source $\)** window, select the line for the **\($ T\_17 G\/L Entry $\)** table, and then in the **Fields** pane, in the toolbar, choose **Add**.  
  
4.  Choose the following fields, and then choose the **OK** button.  
  
    |Field number|Field name|  
    |------------------|----------------|  
    |4|**\($ T\_17\_4 Posting Date $\)**|  
    |5|**\($ T\_17\_5 Document Type $\)**|  
    |17|**\($ T\_17\_17 Amount $\)**|  
  
 Sean added the **\($ T\_17\_4 Posting Date $\)** field from the **\($ T\_17 G\/L Entry $\)** table because Cassie needs the data to be filtered based on the posting date. Now, Sean will use the field to specify the field on the **\($ T\_17 G\/L Entry $\)** table that will be used to calculate the period for the data export.  
  
#### To add a period filter to a table in a data export source  
  
1.  In the **\($ N\_11004 Data Export Record Source $\)** window, select the line for the **\($ T\_17 G\/L Entry $\)** table, and then choose the **\($ T\_11004\_9 Period Field No. $\)** field.  
  
2.  In the **\($ N\_11009 Data Exp. Field List $\)** window, choose the **\($ T\_17\_4 Posting Date $\)** field, and then choose the **OK** button.  
  
     The **\($ N\_11009 Data Exp. Field List $\)** window is filtered to show only the date fields.  
  
 This means that when Cassie exports the data and specifies the start date and the end date for the period that the auditors want, the export will include entries where the **\($ T\_17\_4 Posting Date $\)** field is between the specified start date and end date.  
  
 Next, Sean adds the **\($ T\_18 Customer $\)** and **\($ T\_23 Vendor $\)** tables.  
  
#### To add the \($ T\_18 Customer $\) table  
  
1.  In the **\($ N\_11004 Data Export Record Source $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11004\_3 Table No. $\)**|**18**|  
    |**\($ T\_11004\_50 Export Table Name $\)**|**Customer**|  
    |**\($ T\_11004\_13 Export File Name $\)**|**Customer.txt**|  
  
2.  In the **Fields** pane, in the toolbar, choose **Add**.  
  
3.  Choose the following fields, and then choose the **OK** button.  
  
    |Field number|Field name|  
    |------------------|----------------|  
    |1|**\($ T\_18\_1 No. $\)**|  
    |2|**\($ T\_18\_2 Name $\)**|  
    |21|**\($ T\_18\_21 Customer Posting Group $\)**|  
    |59|**\($ T\_18\_59 Balance \(LCY\) $\)**|  
    |61|**\($ T\_18\_61 Net Change \(LCY\) $\)**|  
  
4.  Repeat the previous two steps to add the **\($ T\_18\_59 Balance \(LCY\) $\)** field again.  
  
5.  Choose the line for the first instance of the **\($ T\_18\_59 Balance \(LCY\) $\)** field, and then, in the **\($ T\_11005\_9 Datefilter Handling $\)** field, choose **Startdate**.  
  
6.  Choose the line for the second instance of the **\($ T\_18\_59 Balance \(LCY\) $\)** field, and then, in the **\($ T\_11005\_9 Datefilter Handling $\)** field, choose **Enddate**.  
  
7.  Choose the line for the **\($ T\_18\_61 Net Change \(LCY\) $\)** field, and then, in the **\($ T\_11005\_9 Datefilter Handling $\)** field, choose **Startdate..Enddate**.  
  
     The following table describes the field values for the fields on the **\($ T\_18 Customer $\)** table.  
  
    |**\($ T\_11005\_5 Field No. $\)**|**\($ T\_11005\_6 Field Name $\)**|**\($ T\_11005\_8 Field Class $\)**|**\($ T\_11005\_9 Datefilter Handling $\)**|**\($ T\_11005\_50 Export Field Name $\)**|  
    |---------------------------------------|----------------------------------------|-----------------------------------------|-------------------------------------------------|------------------------------------------------|  
    |1|**\($ T\_18\_1 No. $\)**|**Normal**||**No**|  
    |2|**\($ T\_18\_2 Name $\)**|**Normal**||**Name**|  
    |21|**\($ T\_18\_21 Customer Posting Group $\)**|**Normal**||**CustomerPostingGroup**|  
    |59|**\($ T\_18\_59 Balance \(LCY\) $\)**|**FlowField**|**..Startdate**|**StartBalanceLCY**|  
    |59|**\($ T\_18\_59 Balance \(LCY\) $\)**|**FlowField**|**..Enddate**|**EndBalanceLCY**|  
    |61|**\($ T\_18\_61 Net Change \(LCY\) $\)**|**FlowField**|**Startdate..Enddate**|**NetChangeLCYPeriod**|  
  
    > [!TIP]  
    >  To change the order of the fields, select a field, and then, in the toolbar, choose **Move Up** or **Move Down**.  
  
 Sean has added the **\($ T\_18 Customer $\)** table to the data export source. Now, he adds the **\($ T\_23 Vendor $\)** table.  
  
#### To add the \($ T\_23 Vendor $\) table  
  
1.  In the **\($ N\_11004 Data Export Record Source $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11004\_3 Table No. $\)**|**23**|  
    |**\($ T\_11004\_50 Export Table Name $\)**|**Vendor**|  
    |**\($ T\_11004\_13 Export File Name $\)**|**Vendor.txt**|  
  
2.  Follow the steps in the previous procedure to add fields from the **\($ T\_23 Vendor $\)** table to the data export source.  
  
     The following table describes the field values for the fields in the **\($ T\_23 Vendor $\)** table.  
  
    |**\($ T\_11005\_5 Field No. $\)**|**\($ T\_11005\_6 Field Name $\)**|**\($ T\_11005\_8 Field Class $\)**|**\($ T\_11005\_9 Datefilter Handling $\)**|**\($ T\_11005\_50 Export Field Name $\)**|  
    |---------------------------------------|----------------------------------------|-----------------------------------------|-------------------------------------------------|------------------------------------------------|  
    |1|**\($ T\_23\_1 No. $\)**|**Normal**||**No**|  
    |2|**\($ T\_23\_2 Name $\)**|**Normal**||**Name**|  
    |21|**\($ T\_23\_21 Vendor Posting Group $\)**|**Normal**||**VendorPostingGroup**|  
    |59|**\($ T\_23\_59 Balance \(LCY\) $\)**|**FlowField**|**..Startdate**|**StartBalanceLCY**|  
    |59|**\($ T\_23\_59 Balance \(LCY\) $\)**|**FlowField**|**..Enddate**|**EndBalanceLCY**|  
    |61|**\($ T\_23\_61 Net Change \(LCY\) $\)**|**FlowField**|**Startdate..Enddate**|**NetChangeLCYPeriod**|  
  
 Sean has almost completed the setup, but he wants to verify that the data export source meets the technical requirements of the auditors’ tool.  
  
#### To validate the data export source  
  
-   On the **Home** tab, in the **Process** group, choose **Validate**.  
  
 Sean has now completed the setup of the data export based on the requirements from Cassie. He notifies her that she can start exporting data for the tax auditors.  
  
## Exporting Data for the Tax Auditors  
 Cassie wants to export data that she can then send to the tax auditors.  
  
#### To export data  
  
1.  In the **Search** box, enter **\($ B\_11015 GDPdU Export $\)**, and then choose the related link.  
  
2.  In the **\($ B\_11015 GDPdU Export $\)** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_11015\_N\_2\_1140000 Starting Date $\)**|The start date. In this scenario, **01\-01\-2013**.|  
    |**\($ B\_11015\_N\_2\_1140002 Ending Date $\)**|The end date. In this scenario, **03\-31\-2013**.|  
  
3.  On the **GDPdU Record Definition** FastTab, select filters as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11003\_1 Data Export Code $\)**|In this scenario, **AUDIT\-Q113**.|  
    |**\($ T\_11003\_2 Data Exp. Rec. Type Code $\)**|In this scenario, **GLCUSTVEND**.|  
  
4.  To export the data, choose the **OK** button.  
  
 When the export is completed, Cassie is notified. She can now submit the exported files to the tax auditors. First, she examines the files in the C:\\Exports folder on her computer. There is a file for each table, and the files have the names that Sean specified in the data export source. There is also an INDEX.XML file that describes the structure of the data export with the names of the tables and fields that Sean specified.  
  
## Next Steps  
 When the tax auditors import Cassie’s files into their software, they can read the data that she exported. If the auditors need a new version of the same data export, Cassie can run the export again.  
  
 The next time the tax auditors request new data, Cassie and Sean can collaborate to create a new data export.  
  
## See Also  
 [Process for Data Access and Testability of Digital Documents \(GDPdU\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/process-for-data-access-and-testability-of-digital-documents-gdpdu-.md)   
 [How to: Set Up Data Exports for GDPdU](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-set-up-data-exports-for-gdpdu.md)   
 [How to: Export GDPdU Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-export-gdpdu-data.md)