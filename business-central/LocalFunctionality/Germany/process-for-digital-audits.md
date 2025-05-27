---
title: Digital audits (GoBD/GDPdU)
description: Export data according to the digital audit process (GoBD/GDPdU) based on German tax law.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: article
ms.search.keywords: data export, digital audit process, GoBD, GDPdU, German tax law, German version
ms.search.form: 11002, 11003, 11004, 11007, 11008, 11009, 11014, 11026, 11027
ms.date: 05/04/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Process for digital audit (GoBD/GDPdU)

You can export data from [!INCLUDE[prod_short](../../includes/prod_short.md)] according to the process for digital audit (GoBD/GDPdU), which is based on German tax law.  

## Overview  

Section 146 and 147 of the German Fiscal Code (Abgabenordnung, AO) allows tax authorities to assess the data of electronic accounting systems digitally. They may do this with a data storage device submitted to them or by direct or indirect access to the system. In the data storage device scenario, the tax liable company (or the person or entity entrusted with accounting and tax duties) must provide appropriate data storage devices with the data in computer-readable form. This means for the tax authorities that they'll be able to access at will all stored data, including the master data and connections with sort and filter functions. To provide data that can be used and evaluated in this manner, you must define and standardize the file formats for submission by data storage device.  

Tax authorities in Germany use analysis software, IDEA, which imports data from ASCII files. The IDEA software can import data in variable length or fixed length format. It requires an XML file, *index.xml*, that describes the structure of the data files.

## Defining GDPdU export data  

You can configure [!INCLUDE[prod_short](../../includes/prod_short.md)] to export data to meet your needs. You can export large sets of data, and you can export small sets of data. You can export data from a single table or a table and related tables.  

For each data export, you define the tables and fields that you want to export. This depends on the auditor's requests. The selected information is exported to the ASCII files. A corresponding XML file, *INDEX.XML*, is also created to describe the ASCII file structure.  

The elements in the *INDEX.XML* file define the names of the tables and fields that are exported. Because the current auditing tool has restrictions on these field names, such as the length and the characters that are used, [!INCLUDE[prod_short](../../includes/prod_short.md)] removes spaces and special characters and then truncates the names to match the 20 character limitation. You can change the suggested table and field names when you add fields to a table definition.  

In most cases, you set up GDPdU data export one time, and then a person in your company can run the export when the auditor requests new data. It's recommended that the setup is handled by people with an understanding of the database structure and the technical hardware in your company, but also in collaboration with people who understand the business data, such as the accountant.  

## Configuration  

You can set up different GDPdU data exports depending on the type of data that you want to be able to export. For example, you can create two GDPdU data exports:  

- One exports high-level information about all general ledger entries, customer ledger entries, vendor ledger entries, and VAT entries.  
- The other exports detailed information about the general ledger entries.  

> [!NOTE]  
> How to set up the GDPdU data exports depends on your company’s needs and the auditor’s requests.  

[Walkthrough: Exporting Data for a Digital Audit](walkthrough-exporting-data-for-a-digital-audit.md) provides an example of how to set up data exports for GDPdU.  

### Data export filters  

When you set up a data export, you can filter data on different levels as described in the following table.  

|Filter level|Description|  
|------------------|---------------------------------------|  
|**Period filters**|You can specify a start date and end date for the data that is exported. You can then use this period filter to filter the data. For example, if you set a period filter for the export, you can then set table filters that use the period.|  
|**Table filters**|You can set filters on each table in the export. For example, you can include only open ledger entries, or entries that have a posting date in the specified filter. For example, you can also set a filter that is based on FlowFields, such as **Net Change (LCY)**, to only export customers where there's a change.<br><br>**Important:**  You can't set a table filter that is based on a FlowFilter.<br><br/> When you add table filters, you can increase performance by specifying the fields that the exported data will be sorted by the value of the **Key No.** field for the record definition. Which keys to use depends on the table. For example, if the table only has two key fields and relatively few entries, then the sort order doesn't affect the speed of the export. But for a table such as G/L Entry, the export is faster if you specify the key in advance, such as the `G/L Account No.,Posting Date` key. If you don't specify a key, then the primary key is used, which might not be the best choice.<br><br/>Other tables in which it can be useful to specify the key include the **Cust. Ledger Entry** and **Vendor Ledger Entry** tables.|  
|**FlowField filters**|You can include FlowFields in the export and set filters based on the period. For example, you can apply the period filter to the **Balance at Date** field on the **G/L Account** table.|  

If you include a FlowField such as the **Net Change (LCY)** field on the **Customer** table, you can specify that the entries must be filtered based on the remaining amount at the end date of the GDPdU period. If you add this as a field filter, then the calculation formulas are based on the dates that are specified during the export.

Learn more in [GDPdU Filter Examples](gdpdu-filter-examples.md).

## Export performance  

If you want to export large sets of data, it can take a long time. We recommend that you set up data exports based on advice from your tax advisor to establish your business needs, and the requirements of the tax auditor. The number of records in a table is also something that you should consider.  

## Related information

- [Set Up Data Exports for Digital Audits](how-to-set-up-data-exports-for-digital-audits.md)  
- [Export Data for a Digital Audit](how-to-export-data-for-a-digital-audit.md)  
- [Walkthrough: Exporting Data for a Digital Audit](walkthrough-exporting-data-for-a-digital-audit.md)  
- [Germany Local Functionality](germany-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
