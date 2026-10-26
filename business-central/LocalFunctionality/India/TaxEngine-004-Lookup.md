---
title: Tax Engine - Lookup
description: Provides an overview of the Lookup utility in the Tax Engine for fetching values from various sources in Business Central (India).
author: v-debapd  
ms.topic: reference
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax engine lookup
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Tax engine - Lookup

Use a lookup to get a value from a record, a variable, or another supported source for tax configuration.

## Lookup source types

The source type identifies where the lookup gets its value.

### Current record

Gets a field value from the current record, which is the source record for the use case.

### Variable

Gets the value of a variable defined in the use case script.

### Table

Gets a field value or an aggregate from a table. Use filters to define the relationship between that table and the current record. This lookup is similar to a `CalcFormula` in AL.

- Table Name: Specify the table from where the value is to be picked.

- Table Filters: Specify the relationship between the current record and the table from where the value is to be picked.

- Table Sorting: Specifies the fields used to sort records for the **First** and **Last** methods. If no sorting is specified, the table's default key is used. The **Min** and **Max** methods sort by the selected field.

- Field Name: Value is picked from this field based on the method you have selected.

- Method:

  - First: Value is picked from the first record.
  - Last: Value is picked from the last record.
  - Sum: Calculate sum of all values from a selected field after applying table filters.
  - Average: Calculate average value from a selected field after applying table filters.
  - Min: Min value from a selected field after applying table filters.
  - Max: Max value from a selected field after applying table filters.
  - Count: Count of records after applying table filters.
  - Exist: Returns whether any records match the table filters.

### Database

Gets the current `USERID`, `COMPANYNAME`, `SERIALNUMBER`, `TENANTID`, `SESSIONID`, or `SERVICEINSTANCEID` value.

### System

Gets the current `TIME`, `TODAY`, `WORKDATE`, or `CURRENTDATETIME` value.

### Tax attribute

Tax attributes defined with tax type can be picked.

### Component

Gets a calculated tax component amount from the use case. Use **Component percent** to get the percentage from the tax rate instead.

### Record variable

The value of a ‘Record variable’ field used in 'use case' variable can be picked.

### Component percent

‘Tax Component Percent’ captured from ‘Tax Rates’ can be picked.

### Column

Value of ‘Tax Rate Parameter’ captured from ‘Tax Rates’ can be picked.

### Attribute table

Gets an attribute value from a record in another table. Specify the table, the attribute, and the filters used to find the record.

### Posting

Use **Posting Field** to get values available during document posting, such as **Dimension Set ID**, **Gen. Bus. Posting Group**, **Gen. Prod. Posting Group**, or **G/L Entry No.**

## Related information

[Tax Engine Script](TaxEngine-005-Script-Activities.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
