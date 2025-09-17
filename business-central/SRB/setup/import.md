---
title: Import subscription contracts and contract lines
description: You can use import contracts and contract lines in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8013, 8008, 8009
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
---

# Import subscription contracts and contract lines

Before you can set up contracts and contract lines, you must create some data, or import it from another system. In addition to customers, vendors, and items, you must create subscription packages, subscription package lines, and more. You can use configuration packages to import data. The data for customer subscription contracts, contract lines, subscriptions, and subscription lines are imported to tables created specifically for this purpose. Processing the data in these import tables creates the actual data.

## Import master data

To import customers, items, subscription lines, vendor subscription contracts, and so on, create [Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages).

|Name|Table|
|:--|:--|
|Items|27|
|Subscription Package Line Templates|8054|
|Subscription Packages|8055|
|Subscription Package Lines|8056|
|Item Subscription Packages|8058|
|Vendor Contracts|8063|

## Import customer subscription contracts, subscription contract lines, subscriptions, and subscription lines

There are particular import tables for importing customer subscription contracts, contract lines, subscriptions, and subscription lines. After the import, you can view, edit, and use the data to create corresponding records in [!INCLUDE [prod_short](../../includes/prod_short.md)] on the **Imported Customer Subscription Contracts**, **Imported Subscriptions**, and **Imported Subscription Lines** pages. Use the following tables to import and create subscriptions, subscription lines, and contract lines.

|Name|Table|
|:--|:--|
|Imported Customer Subscription Contracts|8010|
|Imported Subscriptions|8008|
|Imported Subscription Lines|8009|

### Import customer subscription contracts

The **Imported Customer Subscription Contracts** page serves as an intermediate step for the data transfer of customer subscription contracts. The imported data displays on this page. Use the **Create Customer Subscription Contracts** action to create the customer subscription contracts (just headers, no lines). The action always processes all rows that aren't processed, regardless of filters and selection.

| Field name | Description | When to fill in the field |
|:--|:--|:--|
|Contract No. (Code20)|Specifies the number of the contracts to create. Contract lines (subscription lines) are assigned using the contract number. The number series must allow manual number assignment.|Always|
|Sell-to Customer No. (Code20)|Indicates the number of the customer who receives the contractual services and is invoiced by default.|Always|
|Sell-to Contact No. (Code20)|Specifies the number of the contact that receives the contractual services. In the contract, the number is the **Sell-to Customer No.** from that customer, if empty.|Optional|
|Bill-to Customer No. (Code20)|Indicates the customer to whom you send the contract invoice. If the field is empty, the contract uses the ***Standard (Customer)**.|Optional|
|Bill-to Contact No. (Code20)|Specifies the number of the contact to whom you send the contract invoice. If the field is empty, the contract uses the ***Standard (Customer)**.|Optional|
|Contract Type (Code10)|Indicates the classification of the contract.|Optional|
|Description (Text200)|Indicates the internal description of the contract.|Optional|
|Your Reference (Text35)|Indicates the reference of the customer. The content of this field prints on the contract invoice.|Optional|
|Salesperson Code (Code20)|Indicates the name of the salesperson assigned to the customer.|Optional|
|Assigned User ID (Code50)|Indicates the ID of the user who is responsible for the document.|Optional|
|Without Contract Deferrals (Boolean)|Specifies whether to generate deferrals for the contract. If selected, no deferrals are generated and the invoices post directly to profit or loss. By default, the field isn't selected.|Optional|
|Detail Overview (Boolean)|Determines whether the billing details for this contract are automatically output with invoices and credit memos. Options: Empty (default), Without prices, Complete|Optional|
|Dimensions from Project No. (Code20)| Specifies the project from which the dimensions for the contract are used.|Optional|

If the processing is successful, a customer subscription contract is created and the **Contract created** checkbox is selected.

* The **Processed by** field shows the user who performed the processing.
* The **Processed on** field shows the date and time of the processing.
* Errors display in the **Error Text** field.

### Import subscriptions

The **Imported Subscriptions** page serves as an intermediate step for the data transfer of subscriptions. The imported data displays on this page. Use the **Create Subscriptions** action to create the subscriptions. The action always processes all lines that aren't processed, regardless of filters and selection.

| Field name | Description | When to fill in the field |
|--|--|--|
|Entry No. (Integer)|System field of the table (consecutive number of records) - is created automatically and is in the background.|Never|
|Subscription No. (Code20)|The subscription is created with this number. To facilitate the assignment of subscription lines, always import this number. The number series must allow manual number assignment.|Always|
|Customer No. (Code20)|Indicates the number of the customer to whom the subscription lines were sold. It's mandatory for the assignment to customer subscription contracts.|Always|
|Item No. (Code20)|Indicates the item number of the subscription. It should be an item with subscription lines or a subscription line item.|Always|
|Description (Text100)|Indicates the description of the subscription. If the description is empty, it uses the item's description when the subscription is created.|Optional|
|Quantity (Decimal)|Indicates the quantity of the subscription.|Always|
|Customer Reference (Text35)|Indicates the reference by which the customer knows the subscription.|Optional|
|Bill-to Cust. No. (Code20)|A different invoice recipient (Customer) can be specified here. Related fields are filled automatically (for example, Bill-to Contact No., and so on).|Optional|
|Bill-to Contact No. (Code20)|A different invoice recipient (Contact) can be specified here.|Optional|
|Ship-to Code (Code10)|A different shipment address can be specified here. Related fields are filled automatically.|Optional|
|Contact No. (Code20)|Can be specified if different from primary contact.|Optional|
|Unit of measure (Code10)|Can be specified if different from the unit of the item.|Optional|
|Serial No. (Code50)|Indicates the serial number of the subscription. Subscriptions with serial number can only have a **Quantity** of **1**.|Optional|
|Provision Start Date (Date)|Indicates the date from which the subscription and the related subscription lines were provided to the customer. It has no relevance for billing.|Optional|
|Provision End Date (Date)|Indicates the date from which the subscription and related subscription lines are no longer available to the customer. It has no relevance for billing.|Optional|
|Key (Text100)|Displays a key in the subscription.|Optional|
|Version (Text100)|Display of the version in the subscription.|Optional|

If the processing is successful, a subscription is created and the **Subscription created** checkbox is selected.

* The **Processed by** field shows the user who performed the processing.
* The **Processed on** field shows the date and time of the processing.
* Errors display in the **Error Text** field.

### Import subscription lines

The **Imported Subscription Lines** page serves as an intermediate step for the data transfer of subscription lines and contract lines. Use the **Create Subscription Lines** action to import and process the data. This action can create comment lines in contracts, subscription lines that aren't billed, and contract lines and subscription lines that are billed. The action always processes all lines that aren't processed, regardless of filters and selection.

| Field name | Description | When to fill in the field |
|---|---|---|
|Entry No. (Integer)| System field of the table (consecutive number of records) - is created automatically and is in the background | Never |
|Subscription No. (Code20)|The created subscription line is assigned to this subscription.|Always|
|Subscription Line Entry No. (Integer)|Indicates the line number of the service in the subscription. If no line number is specified, one is determined automatically.| Optional |
|Partner (Option: Customer, Vendor)|Indicates whether to invoice the subscription lines on the vendor side (purchase invoice) or customer side (sales invoice).|Always|
|Subscription Contract No. (Code20)|Indicates the number of the contract in which the subscription line is to be created as a contract line. Subscription lines with the **Invoicing via** field set to **Sales** can't be called up in contracts.|Optional|
|Contract Line No. (Integer)|Indicates the line number of the contract line. If no line number is specified, one is determined automatically.|Optional|
|Contract Line Type (Option: Comment, Item, G/L Account)|Specifies the type of the contract line.|Always|
|Subscription Package Code (Code20)|Specifies the code of the subscription package. A vendor contract line might have the same subscription and package code as the customer subscription contract line. When that's the case, the customer subscription contract dimension is copied to the vendor contract line.|Optional|
|Template Code (Code20)|Indicates the name of the subscription package line template from which the subscription line was copied to the subscription package. It's just for information purposes.|Optional|
|Description (Text100)|Indicates the description of the subscription lines. If no description is specified, it's filled based on the subscription lines.|Always|
|Subscription Line Start Date (Date)|Indicates from which date the subscription lines is valid and can be charged.|Always|
|Subscription Line End Date (Date)|Indicates until which date the subscription lines is valid.|Optional|
|Next Billing Date (Date)|Indicates the date of the next possible billing. If the field is empty, it's filled automatically by the **Subscription Line Start Date**.|Optional|
|Calculation Base Amount (Decimal)|Indicates the base amount from which the price is calculated. The **Price** field in subscription lines is always calculated and never imported.|**Always**|
|Calculation Base % (Decimal)|Indicates the percentage to use to calculate the subscription line price. 100% means that the price of the subscription line is equal to the calculation base amount.|Always|
|Discount % (Decimal)|Indicates the percentage discount for the subscription lines.|Optional|
|Discount Amount (Decimal)|Indicates the discount amount to apply to the subscription lines. Only **Discount %** or **Discount Amount** must be filled for the import to apply a discount.|Optional|
|Amount (Decimal)|Indicates the amount minus the discount granted. The Amount is calculated from **Calculation Base Amount**, **Calculation Base %**, **Quantity**, and **Discount** if the field is empty.|Optional|
|Calculation Base Period (Dateformula)|Indicates the period to which the amount refers. For **1M**, the amount refers to one month, or **12M** if the amount refers to one year.|Always|
|Invoicing via (Option: Sales, Contract)|Indicates whether the subscription line is invoiced through a contract. Subscription lines with **Invoicing via**=**Sales** aren't invoiced and can't transfer to a contract.|Always|
|Invoicing Item No. (Code20)|Indicates which item is used in the contract invoice for invoicing the periodic subscription lines. It must be an item with the **Subscription Option**=**Invoicing Item**.|Optional|
|Notice Period (Dateformula)|Specifies a dateformula for the lead time that a cancellation must have before the subscription line is ended. The **Subsequent Term** is also used to determine the rate at which **Cancellation Possible Until** and **Term Until** are updated. Thus, for a subsequent term of **1M**, the notice period is recurrently postponed by one month.|Optional|
|Initial Term (Dateformula)|Specifies a dateformula for calculating the minimum term of the subscription line. If the **Initial Term** is filled in and no **Subsequent Term** is entered, the **Subscription Line End Date** is automatically set to the end of the initial term.|Optional|
|Subsequent Term (Dateformula)|Specifies a dateformula for automatic extension after the initial term and the rhythm of updating **Cancellation Possible Until** and **Term Until**. If the field is blank, and either the initial term or the notice period are set at the same time, the subscription line end date is automatically set to the expiration date of the initial term or the notice period.|Always|
|Billing Rhythm (Dateformula)|Specifies the rhythm at which the subscription lines are billed. Via a dateformula, the rhythm can be set to, for example, monthly, quarterly, or yearly calculation.|Always|
|Print Line (Boolean)|Specifies whether a line is output when the sales document is printed.|Optional|
|Formatting (Option: Normal, Bold, Italic)|Specifies whether a line in the sales document is printed bold or italic (default: *Normal*).|Optional|
|Print Discount % (Boolean)|Specifies whether the line discount percentage is printed for the line in the sales document (default: *Yes*).|Optional|
|New Page (Boolean)|Specifies whether a new page should be started with this line in the sales document (default: *No*).|Optional|
|Print Quantity only (Boolean)|Specifies that only the quantity (without sales price) is printed for the corresponding line in the sales document (default: *No*).|Optional |

* Mandatory fields always apply to the creation of billable contract lines. Mandatory fields, for example, for comment lines, differ.

If the processing is successful, subscription lines and contract lines are created and the checkboxes **Subscription Line created** and **Subscription Contract Line created** are selected.

* The **Processed by** field shows the user who performed the processing.
* The **Processed on** field shows the date and time of the processing.
* Errors display in the **Error Text** field.

> [!TIP]
> To create a comments line in a contract, the **Contract No.**, **Description**, and **Invoicing via**=*Contract* must be entered.

The following fields only need to be considered if you use a currency different from the local currency. The contract defines the currency. To avoid the conversion at a different rate, you can import currencies.

| Field name | Description | When to fill in the field |
|:--|:--|:--|
|Discount Amount (MW) (Decimal)|Indicates the discount amount in local currency that applies to the subscription lines.|Optional|
|Amount (MW) (Decimal)|Indicates the amount minus the discount granted in local currency. In the contract, the **Amount** and not the **Amount (MW)** is used for invoicing.|Optional|
|Currency Code (Code10)|Indicates the currency for the subscription lines.|Optional|
|Currency Factor (Decimal)|Indicates the currency factor valid for the subscription lines, which is used to convert the amounts into local currency.|Optional|
|Date Currency Factor (Date)|Indicates the date when the currency factor was last updated.|Optional|
|Calculation Base Amount (MW) (Decimal)|Indicates the basis on which the price in local currency is calculated.|Optional|

The fields in the following table only need to be considered if billing is based on usage data.

| Field name | Description | When to fill in the field |
|:--|:--|:--|
|Usage Based Billing (Boolean)|Indicates whether usage data is used as the basis for invoicing.|Optional|
|Usage Based Pricing (Option: Usage Quantity, Fixed Quantity, Unit Cost Surcharge)|Specifies the method for calculating prices on the customer side.|Optional|
|Pricing Unit Cost Surcharge % (Decimal)|Specifies the surcharge as a percent for the customer price calculation, if you use unit cost surcharge.|Optional|
|Supplier Reference Entry No. (Integer)|Indicates the sequence number of the related reference.|Optional|

## Related information

[General setup](general.md)  
[Subscription contract types](contract-types.md)  
