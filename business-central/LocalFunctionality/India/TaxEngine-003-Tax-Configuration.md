---
title: Tax Engine - Configuration of Tax Type and Tax Rates
description: Provides details on configuring tax types, tax entities, input parameters, components, and rate setup in the Tax Engine for India localization in Business Central.
author: v-debapd
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax type configuration, tax rate configuration, tax entities, input parameters, rate setup
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Tax engine - Configuration of tax type and tax rates

Configure tax types, their input parameters, components, and rates to support tax calculation and posting to G/L accounts.

## Tax types

Different taxes can apply to a company. Examples of tax types include:

- **GST**: Goods and Services Tax.
- **TDS**: Tax deducted at source.
- **TCS**: Tax collected at source.
- **WHT**: Withholding tax.

## Tax entities

Tax entities are tables associated with a tax type. They restrict the list of tables available in tax configuration lookups. A tax entity can be a master table or a transaction table.

- Examples of master tables: Customer, Vendor, Location, and Item.
- Examples of transaction tables: Purchase Line, Sales Line, Transfer Line, and Gen. Journal Line.

## Input parameters

Tax attributes are input parameters for tax calculation or reporting. For example:

**HSN Code**: It's a parameter to find GST rate of an item and it can also be used as a parameter for filing of online tax to the government.

You can link an attribute to an existing table field or assign it to an entity as a generic attribute. Generic attributes work similarly to item attributes.

An attribute includes the following information:

- **Name**.
- **Type**: Option, Text, Integer, Decimal, Boolean, or Date.
- **Visible on Interface**: Controls whether the attribute appears in the **Tax Information** FactBox.

To map an attribute to a table field, specify **Mapping Field Name** for the entity mapping. Without a field mapping, the value is stored as a generic attribute for the entity record. For attributes of type **Option**, you can add or view the available values.

## Tax components

Tax types can have components that are computed during tax calculation. Examples include:

- CGST: is a component of Tax Type GST.
- SGST: is a component of Tax Type GST.
- TDS: is a component of Tax Type TDS.
- E-Cess: is a component of Tax Type TDS.

## Rate setup

For each tax type, define the columns used to find a tax rate and the values returned by that rate.

Rate columns can have the following types:

|Type  |Description  |
|---------|---------|
|**Tax Attributes**|Uses a tax attribute, such as HSN Code or GST Group Code, to find a rate.|
|**Value**|Uses a value mapped in the use case, such as From State or To State, to find a rate.|
|**Range From and Range To**|Defines a range with a lower and upper bound, such as a date range. The rate setup displays separate From and To values. **Range From** and **Range To** support one-sided ranges.|
|**Component**|Stores the component percentage returned by the rate. Component formulas use these percentages to calculate tax amounts.|
|**Output Information**|Stores additional values returned by the rate, such as a threshold amount.|

> [!NOTE]
> Use **Allow Blank** when a rate column can be blank. A blank value can provide a fallback when an exact match isn't found. For example, you can configure a GST rate without an HSN/SAC code when several HSN/SAC codes in one GST group share the same rate.

## Tax rates

Define tax rates for combinations of the parameters in **Rate Setup** for a tax type. You can't create duplicate rate setups for the same combination.

To review the setup, open **Tax Types**, select a tax type, and choose **Rate Setup** or **Tax Rates**. In **Rate Setup**, use **Sequence** to control the order of columns and **Visible on Interface** to control whether a column appears in the **Tax Information** FactBox.

## Related information

[Tax Engine Configuration of Use Case](TaxEngine-003.1-Tax-Configuration.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
