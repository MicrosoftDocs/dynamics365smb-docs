---
title: GoBD filter examples [DE]
description: Learn how to use filter types when you set up your GoBD exports.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: GoBD exports, filter types, German version, set up export record source, table filter, date filter handling
ms.search.form: 11002, 11003, 11004, 11007, 11008, 11009, 11014, 11026, 11027
ms.date: 03/10/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# GoBD filter examples in the German version

This article provides examples of how you can use and combine different filter types when you set up your GoBD exports. Setting the right filters can improve system performance.  

The following examples use the **G/L Entry** and **Cust. Ledger Entry** tables for data. They assume that you specified the following dates in the **Export Business Data** batch job.  

- Start Date = 01/01/2013  
- End Date = 12/31/2013  

## Setting up export record source examples  

### Period Field No. field

The following table describes the setup on the **Data Export Record Source** page.  

|Table No.|Table Name|Period Field No.|Period Field Name|Table Filter|  
|---------------|----------------|----------------------|-----------------------|------------------|  
|**17**|G/L Entry|4|Posting Date|No filter set.|  
|**21**|Cust. Ledger Entry|4|Posting Date|No filter set.|  

Results of the export:

- G/L entries and customer ledger entries with posting dates between 1/1/2013 and 12/31/2013.  

### Table filter field

In this example, in addition to the **Period Field No.** information, you also specify a table filter. This filter is useful when you want to include other filters to specify more criteria, for example, amounts, in addition to starting and ending dates for your export.  

|Table No.|Table Name|Period Field No.|Period Field Name|Table Filter|  
|---------------|----------------|----------------------|-----------------------|------------------|  
|**17**|G/L Entry|4|Posting Date||  
|**21**|Cust. Ledger Entry|||Cust. Ledger Entry: **Posting Date=..31-12-13**|  

Results of the export:

- G/L entries with posting dates between 1/1/2013 and 12/31/2013.  
- Customer ledger entries with posting dates that are earlier than 01/01/2014.  

### Date Filter Field No. and Date Filter handling fields

The following example shows how to set date type **FlowFilters**. If a table has more than one date FlowFilter, you can't specify the one to use. However, you can specify how to handle the date filter.  

|Table No.|Table Name|Period Field No.|Period Field Name|Table Filter|Date Filter Handling|  
|---------------|----------------|----------------------|-----------------------|------------------|--------------------------|  
|**18**|Customer|||Customer: **Net Change (LCY)**=<>0|**Period**|  
|**21**|Cust. Ledger Entry|4|Posting Date|Cust. Ledger Entry: **Remaining Amt. (LCY)**=<>0|**End Date Only**|  

Results of the export:

- Customers that have a **Net Change (LCY)** that is greater or less than **0** in the period from 1/1/2013 and 12/31/2013.  
- Customer ledger entries with posting dates between 01/01/2013 and 12/31/2013 that have a **Remaining Amt. (LCY)** that is greater or less than **0** on 12/31/2013.  

### Date filter handling for the same table

In this example, you set multiple filter definitions for the same table.  

|Table No.|Table Name|Table Filter|Date Filter Handling|  
|---------------|----------------|------------------|--------------------------|  
|**18**|Customer|Customer: **Net Change (LCY)**=<>0|**Period**|  
|**18**|Customer|Customer: **Net Change (LCY)**=<>0|**Start Date Only**|  

Results of the export:

- Customers that have a **Net Change (LCY)** that is greater or less than **0** in the period from 1/1/2013 and 12/31/2013.  
- Customers that have a **Net Change (LCY)** that is greater or less than **0** on the day before the start date.  

## Related information

[Set Up Data Exports for a Digital Audit (GoBD)](how-to-set-up-data-exports-for-digital-audits.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
