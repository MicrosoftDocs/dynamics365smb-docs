---
    title: Tax Engine - Tax Configuration
    description: Tax Engine - Tax Configuration
    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 10/06/2020
    ms.author: v-debapd
---
# Tax Engine - Configuration of Tax Type and Tax Rates

This topic provides information about tax types that a tax authority can levy in the same jurisdiction or a different jurisdiction, calculation and posting handling of the same.

## Tax Types

There can be various type of taxes applicable for a company. Examples:

- **GST** : Goods and Services Tax.
- **TDS** : Tax deducted at source.
- **TCS** : Tax collected at source.
- **WHT** : Withholding Tax.


## Tax Entities

These are tables which are specific to a Tax Type. This is defined to restrict the list of tables in a lookup. A Tax Entity can be of type ‘Master’ or ‘Transaction’.

- Master: Customer, Vendor, Location, Item etc.
- Transaction: Purchase Line, Sales Line, Transfer Line, Gen. Journal Line etc.


## Input Parameters

Attributes of tax type are inputs that can be used as a parameter in tax calculation or they can also be used in reporting. For example :

**HSN Code**: It is a parameter to find GST rate of an item and it can also be used as a parameter for filing of online tax to the government.

An attribute can be either linked to a field of an existing table or can be mapped to an existing table as an attribute. (In the same way we have Item Attributes)

Header contains attribute information  

- Attribute Name.
- Datatype of Attribute.
- Visible on Interface (Yes/No) 
- Blocked (Yes/No)

In case the attribute needs to be mapped to a field of a table, then the field needs to be entered in 'Mapping Field Name' else it will be created as an attribute for that entity record. Attribute values can be added or viewed in case the type of attribute is an ‘option’.


## Component

Certain tax type may have components to be computed as part of tax calculation. Following are some examples of tax components:

- CGST: is a component of Tax Type GST.
- SGST: is a component of Tax Type GST.
- TDS: is a component of Tax Type TDS.
- E-Cess: is a component of Tax Type TDS.


## Rate Setup
For each tax type, parameters are defined basis which rate is specified in the setup.

These Parameters can be of following types:

|Type  |Description  |
|---------|---------|
|**Tax Attributes**|When a tax attribute is used as a parameter for tax rate configuration. (example – HSN Code, GST Group Code etc.)|
|**Value**|This will be used where we want to use a value in a tax rate configuration which are not mapped with a table as an attribute. (example – From State, To State etc.)|
|**Range**|This is used to define slabs in a tax rate setup, such as ‘Date from’ and ‘Date To’. As soon as we declare a parameter as range, it creates two parameters in tax rate configuration.|
|**Component**|To define share of tax calculated that will be attributed to the component. For example, 50% of GST will go to CGST and remaining will be SGST.|
|**Output Information**|Numeric values to be part of rate setup. (Example – Threshold Amount)|



## Tax Rates
We can define tax rates on combination of tax parameters defined for a tax type. Rate defined for a combination cannot be repeated.



















