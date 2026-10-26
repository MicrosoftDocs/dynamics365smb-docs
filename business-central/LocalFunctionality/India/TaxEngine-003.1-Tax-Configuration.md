---
title: Tax Engine - Use Case Configuration
description: Configure tax use cases, mappings, calculations, and posting behavior with the Tax Engine for the India localization of Business Central.
author: v-debapd 
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax engine configuration, attribute mapping, rate parameter mapping
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Tax engine - Use case configuration

Configure use cases to define when tax is calculated, where input values come from, and how tax amounts are calculated and posted.

## Use cases

A use case describes a business scenario and the conditions for calculating tax. Application events trigger the calculation. You can enable or disable a use case to meet your business needs.

On the **Tax Types** page, select a tax type and choose **Use Cases**. Open a use case to review its configuration. The configuration includes the following elements:

- **Condition**:

  Determines whether the use case should run.

  The following example illustrates conditions for a reverse-charge purchase invoice in a general journal. Blank cells in the last column represent blank values. The example shows individual comparisons, not a complete rule with condition grouping.

  |Operator|Value|Condition|Value 2|
  |--------------------|-----------------------|-----------------|----------|  
  |    |"Applies-to Doc No."|'Not Equals'| |
  |or|"Applies-to ID"|'Not Equals'| |
  |and|"GST Vendor Type"|Equals|'Unregistered'|
  |and|"Account Type"|Equals|'Vendor'|
  |and|"Document Type"|Equals|'Invoice'|
  |and|"GST Bill-to/Buy-from State Code"|Equals|'Location State Code'|
  |and|"GST Group Code"|'Not Equals'| |
  |and|"HSN/SAC Code"|'Not Equals'| |
  |and|"GST Reverse Charge"|'Equals'|'Yes'|

- **Attribute mapping**:

  Maps required attributes to their value sources. For example, when a transaction line refers to a G/L account, an attribute mapping can get the HSN code from that account.

- **Rate parameter mapping**:

  Maps range and value columns to their value sources. If a tax rate matches, the tax engine returns its component percentages and output information. Examples:

  |Type|Description|
  |---------|---------|
  |**Date**|This column is mapped with posting date of sales header and system analyzes whether the posting date comes in the range of ‘Date from’ and ‘Date To’.|
  |**From State**|In case of sales, parameter 'From State' needs to be mapped with state of location code.|
  |**To State**|In case of Sales, parameter 'To State' needs to be mapped with state of customer code.|

- **Use case variables**:

  Variables can be used at the time of computation of an intermediate value or defining validations in a use case. Example: showing alert message on tax execution.

- **Computation script**:

  This is an optional step, which will be used to store values in variables.
  Example: storing value of TDS Amount and adding INR 1000 freight to get the final amount.

- **Component formula**:

  Define ‘Component formula’ for the components, which are specific to the use case. Example: CGST = {“Line Amount” from “Sales Line”} * {CGST %} /100

- **Use case posting**:

  Use **Posting Setup** to select a posting entity and apply filters to find the record that supplies G/L accounts for the tax components. Account mappings can use a field or a lookup. For reverse charge, turn on **Reverse Charge** and map the reversal account. Posting fails if the configured filters don't find a posting setup record.

- **Tax ledger mapping**:

  Map calculated tax and other posting values to the fields of the tax ledger records created during posting. In the component's posting setup, use **Tax Ledger Mapping** to configure the records to insert. Use **Posting Script** for any additional calculations needed during posting.

## Enable a use case

A use case must have **Status** set to **Released** before you can enable it. The tax type must also be enabled for the use case to run. On the **Use Cases** page, use **Enable Selected Cases** or **Disable Selected Cases** to control which use cases are available.

## How to check tax information for a transaction

On supported transaction pages, the **Tax Information** FactBox shows tax attributes and calculated components. Only values configured as visible on the interface are displayed.

On supported statistics pages, the **Tax Summary** section shows the tax component totals.

## Related information

[Tax Engine Lookup](TaxEngine-004-Lookup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
