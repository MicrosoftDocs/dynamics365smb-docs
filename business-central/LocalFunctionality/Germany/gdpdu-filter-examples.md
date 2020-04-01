---
    title: GDPdU Filter Examples
    description: The following topic provides examples of how you can use and combine different filter types when you set up your GPDdU exports. By setting filters appropriately, you can improve performance.
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
# GDPdU Filter Examples
The following topic provides examples of how you can use and combine different filter types when you set up your GPDdU exports. By setting filters appropriately, you can improve performance.  

The following examples use the G/L Entry and Cust. Ledger Entry tables for data. They assume that you have specified the following date in the **Export Business Data** batch job.  

Start Date = 01/01/2013  

End Date = 12/31/2013  

## Setting Up Export Record Source Examples  

### Period Field No.  
On the **Data Export Record Source** page, the set up is as described in the following table.  

|Table No.|Table Name|Period Field No.|Period Field Name|Table Filter|  
|---------------|----------------|----------------------|-----------------------|------------------|  
|17|G/L Entry|4|Posting Date|No filter set.|  
|21|Cust. Ledger Entry|4|Posting Date|No filter set.|  

**Export Results**  

- G/L Entries with Posting Date between 1/1/2013 and 12/31/2013.  
- Cust. Ledger Entries with Posting Date between 1/1/2013 and 12/31/2013.  

### Table Filter  
In this example, in addition to Period Field No. information, you also specify a table filter. This is useful when you want to not only include a starting date and ending date for your export, but also include an additional filter to specify other criteria, for example, amounts.  

|Table No.|Table Name|Period Field No.|Period Field Name|Table Filter|  
|---------------|----------------|----------------------|-----------------------|------------------|  
|17|G/L Entry|4|Posting Date||  
|21|Cust. Ledger Entry|||Cust. Ledger Entry: **Posting Date=..31-12-13**|  

**Export Results**  

- G/L Entries with Posting Date between 1/1/2013 and 12/31/2013.  
- Cust. Ledger Entries with Posting Date earlier than 01/01/2014.  

### Date Filter Field No. and Date Filter Handling  
The following example demonstrates setting Date type FlowFilters. If a table has more than one date FlowFilter, you cannot specify one to use, but you can specify how the date filter should be handled.  

|Table No.|Table Name|Period Field No.|Period Field Name|Table Filter|Date Filter Handling|  
|---------------|----------------|----------------------|-----------------------|------------------|--------------------------|  
|18|Customer|||Customer: **Net Change (LCY)**=<>0|**Period**|  
|21|Cust. Ledger Entry|4|Posting Date|Cust. Ledger Entry: **Remaining Amt. (LCY)**=<>0|**End Date Only**|  

**Export Results**  

- Customers that have Net Change (LCY) <> 0 in the period from 1/1/2013 and 12/31/2013.  
- Cust. Ledger Entries with Posting Date between 01/01/2013 and 12/31/2013 that have Remaining Amt. (LCY) <> 0 at 12/31/2013.  

### Date Filter Handling for the Same Table  
In this example, you set multiple filter definitions for the same table.  

|Table No.|Table Name|Table Filter|Date Filter Handling|  
|---------------|----------------|------------------|--------------------------|  
|18|Customer|Customer: **Net Change (LCY)**=<>0|**Period**|  
|18|Customer|Customer: **Net Change (LCY)**=<>0|**Start Date Only**|  

**Export Results**  

- Customers that have Net Change (LCY) <> 0 in the period from 1/1/2013 and 12/31/2013.  
- Customers that have Net Change (LCY) <> 0 on the day before the start date.  

## See Also  
 [Set Up Data Exports for GDPdU](how-to-set-up-data-exports-for-gdpdu.md)
