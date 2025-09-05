---
title: Tax Engine - Lookup
description: Provides an overview of the Lookup utility in the Tax Engine for fetching values from various sources in Business Central (India).
author: v-debapd  
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax engine lookup
ms.date: 06/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Tax engine - Lookup

Lookup is a utility to fetch value from the system or from a variable.

## Source type

Source type is to specify the source of value.

### Current record

If value of a field is to be picked from the current record (that is source table of the rule).

### Variable

If value of a variable is to be picked. Variables of a rule can be created or viewed from the rule editor card.

### Table

If value of a field is to be picked from a table that is related to the current record / source table. This is very much like CALCFORMULA in AL.

- Table Name: Specify the table from where the value is to be picked.

- Table Filters: Specify the relationship between the current record and the table from where the value is to be picked.

- Table Sorting: Sorting to be applied on table records. If sorting is specified, records are sorted on Primary Key.

- Field Name: Value is picked from this field based on the method you have selected.

- Method:

  - First: Value is picked from the first record.
  - Last: Value is picked from the last record.
  - Sum: Calculate sum of all values from a selected field after applying table filters.
  - Average: Calculate average value from a selected field after applying table filters.
  - Min: Min value from a selected field after applying table filters.
  - Max: Max value from a selected field after applying table filters.
  - Count: Count of records after applying table filters.

### Database

USERID, COMPANYNAME, SERIALNUMBER, TENANTID, SESSIONID, SERVICEINSTANCEID values can be picked from the current database.

### System

TIME, TODAY, WORKDATE, CURRENTDATETIME values can be picked from the current database.

### Tax attribute

Tax attributes defined with tax type can be picked.

### Component

Tax Component amounts computed can be picked from Tax Rates.

### Record variable

The value of a ‘Record variable’ field used in 'use case' variable can be picked.

### Component percent

‘Tax Component Percent’ captured from ‘Tax Rates’ can be picked.

### Column

Value of ‘Tax Rate Parameter’ captured from ‘Tax Rates’ can be picked.

### Attribute table

Value of an attribute from existing table can be picked.

### Posting

To get the helpers that can be used in posting of a document. (Ex- Dimension Set, General Posting Group’s, GL Entry No. of Tax ledger Entry).

## Related information

[Tax Engine Script](TaxEngine-005-Script-Activities.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
