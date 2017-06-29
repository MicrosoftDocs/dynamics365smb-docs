---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Set Up Statutory Reports
The Russian federal tax authorities require companies to submit statutory reports in electronic formats such as XML or as Microsoft Excel documents. In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you must set up the templates, formats, XML schemas, and other prerequisites so that you can generate the required files.  
  
 After you have set up a report and specified the required information, you can export the report to Excel, and then print the report.  
  
 For more information, see [Statutory Reporting Directives](http://go.microsoft.com/fwlink/?LinkId=216143) and [Statutory Reporting Software](http://go.microsoft.com/fwlink/?LinkId=216142) on the Federal Tax Service website.  
  
 First, you must set up general information that applies to all statutory reports.  
  
### To set up general information about statutory reports  
  
1.  In the **Search** box, enter **Statutory Report Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields to describe XML formatting, file locations, and so on.  
  
3.  On the **Numbering** FastTab, fill in the fields to describe the number series to use for data export and data import logs.  
  
 The following procedure is optional. It allows you to set up groups in which to group different types of reports.  
  
### To set up statutory report groups  
  
1.  In the **Search** box, enter **Statutory Report Groups**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**. In the **Code** field, enter a code for the group, and in the **Description** field, enter a description of the purpose of the group.  
  
 Next, you must set up report versions.  
  
### To set up report versions  
  
1.  In the **Search** box, enter **Format Versions**, and then choose the related link.  
  
2.  Fill in the fields to describe the format version of the statutory report.  
  
3.  On the **Home** tab, in the **Process** group, choose to import an Excel Template or and XML schema.  
  
     Depending on the type of report, you can import Microsoft Excel templates as .xls files or you can import XML schemas as .xml or .xsd files. You can also define the start date for when the statutory report must be used.  
  
 When a new version of a report is announced, you can add it to the version list in this window.  
  
## Defining Statutory Reports  
 Next, you must define each statutory report.  
  
#### To define a statutory report  
  
1.  In the **Search** box, enter **Statutory Reports**, and then choose the related link.  
  
2.  Optionally, you can create one or more rows that group a range of statutory reports, such as reports for VAT reporting or reports for property tax. To specify a row as an internal grouping, enter information in the **Code** and **Description** fields, and the select the **Header** check box. Leave the other fields blank.  
  
3.  To specify a row as a statutory report, create a new entry and fill in the fields to describe the statutory report.  
  
     For each statutory report, in the **Format Version Code** field, you can specify the current version to use for this kind of report.  
  
4.  For each statutory report, choose **Navigate**, and in the **Setup** group, choose **Tables**.  
  
    1.  In the **Statutory Report Tables** window, fill in the fields to describe each table that must be created in the Microsoft Excel workbook. This includes specifying the name of the worksheet.  
  
         For example, a statutory report can require that you submit a Microsoft Excel workbook with a separate table for each section of the report.  
  
    2.  For each table, specify the table rows and table columns.  
  
         You can also specify individual requisites. Close the table windows.  
  
5.  For each statutory report, choose **Navigate**, and in the **Setup** group, choose **XML Element Lines**.  
  
    -   In the **XML Element Lines** window, fill in the fields to describe the XML structure of the file that you will export. You can use expressions to calculate values, or you can use table data directly.  
  
         You can link each XML element line to a table that you defined in the **Statutory Report Tables** window for that statutory report.  
  
6.  Optionally, if you want to define a statutory report that resembles an existing report, you can copy the existing report.  
  
    1.  In the **Statutory Reports** window, create an entry by entering a code in the **Code** field.  
  
    2.  Choose **Navigate**, and in the **Setup** group, choose **Copy Report**.  
  
    3.  In the **Copy Statutory Report** window, in the **Copy From Report Code** field, select the existing report, and then choose the **OK** button.  
  
         This creates a copy of the existing report with the tables and XML element lines. Now, you can make the appropriate changes as described earlier in this section.  
  
 You can now use the defined statutory reports to generate and submit reports to the authorities. For more information, see [How to: Create Statutory Report Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-statutory-report-data.md).  
  
## See Also  
 [Statutory Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/statutory-reports.md)   
 [How to: Create Statutory Report Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-statutory-report-data.md)