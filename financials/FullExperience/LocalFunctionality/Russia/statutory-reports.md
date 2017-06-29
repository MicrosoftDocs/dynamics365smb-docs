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
# Statutory Reports
ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> lets you set up statutory reports so that you can import and export data for electronic tax reporting and other required documents.  
  
 After you have set up a report and specified the required information, you can export the report to Excel, and then print the report.  
  
## Getting Started with Statutory Reports  
 Use the windows based on the following key tables to set up and create statutory reports.  
  
|Tables|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|------------|---------------------------------------|  
|Statutory Report Setup|Specifies information that is used to set up statutory reports including templates, formats, number series, and export destinations.|  
|Format Version|Specifies setup information about the different report formats. This includes when to use which report, the XML schema to use, and the required data format.|  
|Statutory Report|Specifies a list of statutory reports with detailed information, such as type, format version, and if the statutory report is currently active. From this window, you can define statutory report tables, requisites groups, the XML element lines, and you can export data.|  
|Statutory Report Table|Specifies information that is required to set up reporting tables including scalability limits, templates, and standard text.<br /><br /> From this window, you can define table rows, columns, individual requisites, and data source mapping.|  
|Stat. Report Table Row|Allows you to define row formats and functions for your statutory report tables.|  
|Stat. Report Table Column|Allows you to define column formats for your statutory report tables.|  
|Stat. Report Requisites Group|Specifies the conditions used to format and process statutory reports including export type, Microsoft Excel mapping, and cell quantity.|  
  
## Data for Statutory Reports  
 The statutory reports are based on account schedules and tax registers. For each statutory report that you set up in the **Statutory Reports** window, you define how the data maps to fields on tables in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> by creating table mappings. In the **Statutory Report Tables** window, in the **Int. Source Type** field, you specify the area that the data comes from as described in the following table.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|----------------------------------|---------------------------------------|  
|**Acc. Schedule**|The data is based on an account schedule.|  
|**Tax Register**|The data is based on a tax register. For more information, see [Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-registers.md).|  
|**Tax Difference**|The data is based on a tax difference. For more information, see [Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-differences.md).|  
|**Payroll Analysis Report**|The data is based on payroll analysis.|  
  
## See Also  
 Excel Template   
 [Tax Accounting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-accounting.md)   
 [Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-differences.md)   
 [Selecting the Report Data Source](assetId:///79db2621-6067-4421-8fe6-3ef2baba1ecc)