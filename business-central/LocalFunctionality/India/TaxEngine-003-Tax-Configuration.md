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
# Tax Engine - Tax Configuration

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

- Tax Attributes – when a tax attribute is used as a parameter for tax rate configuration. (example – HSN Code, GST Group Code etc.)

- Value – This will be used where we want to use a value in a tax rate configuration which are not mapped with a table as an attribute. (example – From State, To State etc.)

- Range – This is used to define slabs in a tax rate setup, such as ‘Date from’ and ‘Date To’. As soon as we declare a parameter as range, it creates two parameters in tax rate configuration.

- Component – To define share of tax calculated that will be attributed to the component. For example, 50% of GST will go to CGST and remaining will be SGST.

- Output Information – Numeric values to be part of rate setup. (Example – Threshold Amount)


## Tax Rates
We can define tax rates on combination of tax parameters defined for a tax type. Rate defined for a combination cannot be repeated.


## Use Cases
Use case describes a business scenario, conditions which need to be met and event which will trigger the calculation of tax. A use case can be enabled or disabled as per the business need.  

Use Case consist of following stages for calculation:

####  Condition:

This will be the condition which decides whether the use case should be executed or not.

Example of Condition:

|Operator|Value|Condition|Value 2|
|--------------------|-----------------------|-----------------|----------|  
|    |"Applies-to Doc No."|Not Equals|''
|or|"Applies-to ID"|Not Equals|''
|and|"GSt Vendor Type"|Equals|'Unregistered'
|and|"Account Type"|Equals|'Vendor'
|and|"Document Type"|Equals|'Invoice'
|and|"GST Bill-to/Buy-from State Code"|Equals|'Location State Code'
|and|"GST Group Code"|Not Equals|''
|and|"HSN/SAC Code"|Not Equals|''
|and|"GST Reverse Charge"|Equals|'Yes'


#### Attribute Mapping:

This will be defined to map the required attributes with their source.

Example : In case GST to be calculated on Sales Line, HSN Code will flow from G/L Account table in case type on General Journal Line is G/L Account.

#### Rate Parameter Mapping:

Rate parameter need to be mapped with their source, but this mapping will be done only for column types ‘Range’ and ‘Value’. If an applicable tax rate is found, then system will return ‘component percent’ defined for that tax rate. Example:

- Date: This column will be mapped with posting date of sales header and system will analyze whether the posting date comes in the range of ‘Date from’ and ‘Date To’.
- From State: In case of sales, parameter 'From State' needs to be mapped with state of location code.
- To State: In case of Sales, parameter 'To State' needs to be mapped with state of customer code.


#### Use Case Variables:

Variables can be used at the time of computation of an intermediate value or define a validation in a use case. Example: showing alert message on Tax execution.


#### Computation Script:

This is an optional step which will be only used to store values in variables.
Example: storing value of TDS Amount and adding INR 1000 freight to get the final amount.


#### Component Formula:

Define ‘Component formula’ for the components which are specific to the use case. Example: CGST = {“Line Amount” from “Sales Line”} * {CGST %} /100


#### Use Case Posting:

Map required component of use case with a G/L account from chart of accounts. There is a posting entity where the G/L accounts are configured for the tax type. Based on the filters applied on the posting entity, tax engine points to the record from which components can be mapped to posting accounts. In case of reverse charge, same component is adjusted with its payable or receivable account. Configuration will have “Reverse Charge” flag as true and account can be mapped for same in “Reverse Charge G/L Field Name”.


#### Tax Ledger Mapping:

Calculated tax, which is an output of a use case needs to be mapped to a tax ledger table. Example: On posting of general ledger entry for GST, there will be a new GST Entry created as a tax ledger for the posted transaction.


### How to Attach Use Case to Business Event.

- To attach a use case to a Business Event go to ‘Tax Use Case Events’ from the Search box.

- This will open the list of available ‘Events’, select an ‘Event’, for example “A Sales Document is released” and click on ‘Attach/ De-Attach Rule’, it will open the list of available use cases that can be attached to an event.

- Attached used case can be seen on the fact box.


## How to check Tax Information on Transaction

There are two fact boxes available on transaction page to view calculated tax

- Tax Information 
- Tax Component

Statistics Page, we will show the tax information in Tax Summary Tab.









































