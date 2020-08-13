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
    ms.date: 08/13/2020
    ms.author: v-debapd
---
# Tax Engine - Use Case Configuration

This topic provides information about use case configuration.

## Use Cases
Use case describes a business scenario, conditions which need to be met and event which will trigger the calculation of tax. A use case can be enabled or disabled as per the business need.  

Use Case consist of following stages for calculation:

  - **Condition**:

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


   - **Attribute Mapping**:

     This will be defined to map the required attributes with their source.
     Example : In case GST to be calculated on Sales Line, HSN Code will flow from G/L Account table in case type on General Journal Line is G/L Account.

   - **Rate Parameter Mapping**:

     Rate parameter need to be mapped with their source, but this mapping will be done only for column types ‘Range’ and ‘Value’. If an applicable tax rate is found, then system will return ‘component percent’ defined for that tax rate. Example:

      |Type  |Description  |
      |---------|---------|
      |**Date**|This column will be mapped with posting date of sales header and system will analyze whether the posting date comes in the range of ‘Date from’ and ‘Date To’.|
      |**From State**|In case of sales, parameter 'From State' needs to be mapped with state of location code.|
      |**To State**|In case of Sales, parameter 'To State' needs to be mapped with state of customer code.|


   - **Use Case Variables**:

     Variables can be used at the time of computation of an intermediate value or define a validation in a use case. Example: showing alert message on Tax execution.


  - **Computation Script**:

     This is an optional step which will be only used to store values in variables.
     Example: storing value of TDS Amount and adding INR 1000 freight to get the final amount.


   - **Component Formula**:

     Define ‘Component formula’ for the components which are specific to the use case. Example: CGST = {“Line Amount” from “Sales Line”} * {CGST %} /100


  - **Use Case Posting**:

    Map required component of use case with a G/L account from chart of accounts. There is a posting entity where the G/L accounts are configured for the tax type. Based on the filters applied on the posting entity, tax engine points to the record from which components can be mapped to posting accounts. In case of reverse charge, same component is adjusted with its payable or receivable account. Configuration will have “Reverse Charge” flag as true and account can be mapped for same in “Reverse Charge G/L Field Name”.


  - **Tax Ledger Mapping**:

    Calculated tax, which is an output of a use case needs to be mapped to a tax ledger table. Example: On posting of general ledger entry for GST, there will be a new GST Entry created as a tax ledger for the posted transaction.


## How to Attach Use Case to Business Event.

- To attach a use case to a Business Event go to ‘Tax Use Case Events’ from the Search box.

- This will open the list of available ‘Events’, select an ‘Event’, for example “A Sales Document is released” and click on ‘Attach/ De-Attach Rule’, it will open the list of available use cases that can be attached to an event.

- Attached used case can be seen on the fact box.


## How to check Tax Information on Transaction

There are two fact boxes available on transaction page to view calculated tax

- Tax Information 
- Tax Component

Statistics Page, we will show the tax information in Tax Summary Tab.









































