---
title: Tax Engine - Tax Configuration 02
description: Provides details about configuring tax use cases in the Tax Engine for India localization in Business Central.
author: v-debapd 
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax engine configuration, attribute mapping, rate parameter mapping
ms.date: 06/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Tax engine - Use case configuration

This article provides information about use case configuration.

## Use cases

Use case describes a business scenario, conditions, which need to be met and event, which triggers the calculation of tax. A use case can be enabled or disabled as per the business need.  

Use Case consist of following stages for calculation:

- **Condition**

  Condition, which determines whether the use case should be executed or not.

  Example of Condition:

  |Operator|Value|Condition|Value 2|
  |--------------------|-----------------------|-----------------|----------|  
  |    |"Applies-to Doc No."|'Not Equals'|
  |or|"Applies-to ID"|'Not Equals'|
  |and|"GST Vendor Type"|Equals|'Unregistered'|
  |and|"Account Type"|Equals|'Vendor'|
  |and|"Document Type"|Equals|'Invoice'|
  |and|"GST Bill-to/Buy-from State Code"|Equals|'Location State Code'
  |and|"GST Group Code"|'Not Equals'|
  |and|"HSN/SAC Code"|'Not Equals'|
  |and|"GST Reverse Charge"|'Equals'|'Yes'|

- **Attribute Mapping**

  This is defined to map the required attributes with their source of value.
  Example: In case, GST is to be calculated on Sales Line and value of field ‘Type’ on General Journal Line is ‘G/L Account’ then, HSN Code flows from G/L Account table.

- **Rate Parameter Mapping**

  Rate parameter needs to be mapped with their source, but this mapping is done only for column types ‘Range’ and ‘Value’. If an applicable tax rate is found, then system returns ‘component percent’ defined for that tax rate. Example:

  Type  |Description  |
  |---------|---------|
  |**Date**|This column is mapped with posting date of sales header and system analyzes whether the posting date comes in the range of ‘Date from’ and ‘Date To’.|
  |**From State**|In case of sales, parameter 'From State' needs to be mapped with state of location code.|
  |**To State**|In case of Sales, parameter 'To State' needs to be mapped with state of customer code.|

- **Use Case Variables**

  Variables can be used at the time of computation of an intermediate value or defining validations in a use case. Example: showing alert message on tax execution.

- **Computation Script**

  This is an optional step, which will be used to store values in variables.
  Example: storing value of TDS Amount and adding INR 1000 freight to get the final amount.

- **Component Formula**

  Define ‘Component formula’ for the components, which are specific to the use case. Example: CGST = {“Line Amount” from “Sales Line”} * {CGST %} /100

- **Use Case Posting**

  There's a posting entity where the 'G/L Accounts' are configured for the specific 'tax type'. Based on the filters applied on the posting entity, tax engine points to the record from which components can be mapped to posting accounts. In case of reverse charge, same component is adjusted with its payable or receivable account. Configuration has “Reverse Charge” flag as true and account can be mapped for same to “Reverse Charge G/L Field Name”.

- **Tax Ledger Mapping**

  Calculated tax, which is an output of a use case needs to be mapped to a tax ledger table. Example: On posting of general ledger entry for GST, there will be a new GST Entry created as a tax ledger for the posted transaction.

## How to check tax information for a transaction

There are two fact boxes available on transaction page to view calculated tax

- Tax Information
- Tax Component

Statistics Page shows the tax information in Tax Summary Tab.

## Related information

[Tax Engine Lookup](TaxEngine-004-Lookup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
