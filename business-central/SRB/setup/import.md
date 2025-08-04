---
title: Data migration
description: You can use import contracts and contract lines in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Import of contracts and contract lines

Before you can set up contracts and contract lines, you must create some data, or import it from another system. In addition to customers, vendors, and items, you must create service commitment packages, service commitment package lines, and more. You use configuration packages to import data. The data for customer contracts, contract lines, service objects, and service commitments imports to tables created specifically for processing the data.

## Import of master data

To import customers, items, service commitments, vendor contracts, and so on, create [Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages).

|Name|Table|
|:--|:--|
|Items|27|
|Service Commitment Templates|70920754|
|Service Commitment Packages|70920755|
|Service Commitment Package Lines|70920756|
|Item Service Commitment Packages|70920758|
|Vendor Contract|70920763|

## Import customer contracts, contract lines, service objects, and service commitments

There are particular import tables for importing customer contracts, contract lines, service objects, and service commitments. After the import, you can view, edit, and use the data to create corresponding records in [!INCLUDE [prod_short](../../includes/prod_short.md)] on the **Imported Customer Contracts**, **Imported Service Objects**, and **Imported Service Commitments** pages. Use the following tables to import and create service objects, service commitments, and contract lines.

|Name|Table|
|:--|:--|
|Imported Customer Contracts|70920710|
|Imported Service Objects|70920708|
|Imported Service Commitments|70920709|

### Import customer contracts

The **Imported Customer Contracts** page serves as an intermediate step for the data transfer of service objects. The imported data displays on this page. Use the **Create Customer Contracts** action to create the customer contracts (just headers, no lines). The action always processes all rows that aren't processed, regardless of filters and selection.

|Name|Description|To fill|
|:--|:--|:--|
|Contract No. (Code20)|Specifies the number of the contracts to create. Contract lines (service commitments) are assigned using the contract number. The number series must allow manual number assignment.|Always|
|Sell-to Customer No. (Code20)|Indicates the number of the customer who receives the contractual services and is invoiced by default.|Always|
|Sell-to Contact No. (Code20)|Specifies the number of the contact that receives the contractual services. In the contract, the number is the **Sell-to Customer No.** from that customer, if empty.|Optional|
|Bill-to Contact No. (Code20)|Indicates the customer to whom you send the contract invoice. If the field is empty, the contract uses the ***Standard (Customer)**.|Optional|
|Contract Type (Code10)|Indicates the classification of the contract.|Optional|
|Description (Text200)|Indicates the internal description of the contract.|Optional|
|Your Reference (Text35)|Indicates the reference of the customer. The content of this field prints on the contract invoice.|Optional|
|Salesperson Code (Code20)|Indicates the name of the salesperson assigned to the customer.|Optional|
|Assigned User ID (Code50)|Indicates the ID of the user who is responsible for the document.|Optional|
|Without Contract Deferrals (Boolean)|Specifies whether to generate deferrals for the contract. If selected, no deferrals are generated and the invoices post directly to profit or loss. By default, the field isn't selected.|Optional|
|Detail Overview (Boolean)|Determines whether the billing details for this contract are automatically output with invoices and credit memos. Options: Empty (default), Without prices, Complete|Optional|
|Dimensions from Project No. (Code20)| Specifies the project from which the dimensions for the contract are used.|Optional|

If the processing is successful, a customer contract is created and **Contract Created** is selected.

* The **Processed by** field shows the user who performed the processing.
* The **Processed on** field shows the date and time of the processing.
* Errors display in the **Error Text** field.

### Import service objects

The **Imported Service Objects** page serves as an intermediate step for the data transfer of service objects. The imported data displays on this page. Use the **Create Service Objects** action to create the service objects. The action always processes all lines that aren't processed, regardless of filters and selection.

| Name | Description | To be filled |
|--|--|--|
|Entry No. (Integer)|System field of the table (consecutive number of records) - is created automatically and is in the background.|*Never*|
|Service Object No. (Code20)|The service object is created with this number. To facilitate the assignment of service commitments, always import this number. The number series must allow manual number assignment.|**Always**|
|Customer No. (Code20)|Indicates the number of the customer to whom the service commitments were sold. It's mandatory for the assignment to customer contracts.|**Always**|
|Item No. (Code20)|Indicates the item number of the service object. It should be an item with service commitments or a service commitment item.|**Always**|
|Description (Text100)|Indicates the description of the service object. If the description is empty, it uses the item's description when the service object is created.|Optional|
|Quantity (Decimal)|Indicates the quantity of the service object.|**Always**|
|Customer Reference (Text35)|Indicates the reference by which the customer knows the service object.|Optional|
|Bill-to Cust. No. (Code20)|A different invoice recipient (Customer) can be specified here. Related fields are filled automatically (for example, Bill-to Contact No., and so on).|Optional|
|Bill-to Contact No. (Code20)|A different invoice recipient (Contact) can be specified here.|Optional|
|Ship-to Code (Code10)|A different shipment address can be specified here. Related fields are filled automatically.|Optional|
|Contact No. (Code20)|Can be specified if different from primary contact.|Optional|
|Unit of measure (Code10)|Can be specified if different from the unit of the item.|Optional|
|Serial No. (Code50)|Indicates the serial number of the service object. Service objects with serial number can only have a **Quantity**=**1**.|Optional|
|Provision Start Date (Date)|Indicates the date from which the service object and the related service commitments were provided to the customer. It has no relevance for billing.|Optional|
|Provision End Date (Date)|Indicates the date from which the service object and related service commitments are no longer available to the customer. It has no relevance for billing.|Optional|
|Key (Text100)|Displays a key in the service object.|Optional|
|Version (Text100)|Display of the version in the service object.|Optional|

If the processing is successful, a service object is created and **Service Object Created** is selected.

* The **Processed by** field shows the user who performed the processing.
* The **Processed on** field shows the date and time of the processing.
* Errors display in the **Error Text** field.

### Import service commitments

The **Imported Services Commitments** page serves as an intermediate step for the data transfer of service commitments and contract lines. Use the **Create Service Commitments** action to import and process the data. This action can create comment lines in contracts, service commitments that aren't billed, and contract lines and service commitments that are billed. The action always processes all lines that aren't processed, regardless of filters and selection.

| Name | Description | To be filled |
|---|---|---|
|Entry No. (Integer)| System field of the table (consecutive number of records) - is created automatically and is in the background | **Never** |
|Service Object No. (Code20)|The created service commitment is assigned to this service object.|**Always**|
|Service Commitment Line No. (Integer)|Indicates the line number of the service in the service object. If no line number is specified, one is determined automatically.| **Optional** |
|Partner (Option: Customer, Vendor)|Indicates whether to invoice the service commitments on the vendor side (purchase invoice) or customer side (sales invoice).|**Always**|
|Contract (Code20)|Indicates the number of the contract in which the service commitment is to be created as a contract line. Service commitments with **Invoicing via**=**Sales** can't be called up in contracts.|**Optional**|
|Contract Line No. (Integer)|Indicates the line number of the contract line. If no line number is specified, one is determined automatically.|Optional|
|Contract Line Type (Option: Comment, Service Commitment)|Specifies the type of the contract line.|**Always**|
|Package Code (Code20)|Specifies the code of the service commitment package. A vendor contract line might have the same service object and package code as the customer contract line. When that's the case, the customer contract dimension is copied to the vendor contract line.|**Optional**|
|Template Code (Code20)|Indicates the name of the service commitment template from which the service commitment was copied to the service commitment package. It's just for information purposes.|**Optional**|
|Description (Text100)|Indicates the description of the service commitments. If no description is specified, it's filled based on the service commitments.|**Always**|
|Service Start Date (Date)|Indicates from which date the service commitments is valid and can be charged.|**Always**|
|Service End Date (Date)|Indicates until which date the service commitments is valid.|Optional|
|Next Billing Date (Date)|Indicates the date of the next possible billing. If the field is empty, it's filled automatically by the **Service Start Date**.|Optional|
|Calculation Base Amount (Decimal)|Indicates the base amount from which the price is calculated. The **Price** field in service commitments is always calculated and never imported.|**Always**|
|Calculation Base % (Decimal)|Indicates the percentage to use to calculate the service commitment price. 100% means that the price of the service commitment is equal to the calculation base amount.|**Always**|
|Discount % (Decimal)|Indicates the percentage discount for the service commitments.|Optional|
|Discount Amount (Decimal)|Indicates the discount amount to apply to the service commitments. Only **Discount %** or **Discount Amount** must be filled for the import to apply a discount.|Optional|
|Service Amount (Decimal)|Indicates the amount minus the discount granted. The Service Amount is calculated from **Calculation Base Amount**, **Calculation Base %**, **Quantity**, and **Discount** if the field is empty.|Optional|
|Calculation Base Period (Dateformula)|Indicates the period to which the service amount refers. For **1M**, the amount refers to one month, or **12M** if the amount refers to one year.|**Always**|
|Invoicing via (Option: Sales, Contract)|Indicates whether the service commitment is invoiced through a contract. Service commitments with **Invoicing via**=**Sales** aren't invoiced and can't transfer to a contract.|**Always**|
|Invoicing Item No. (Code20)|Indicates which item is used in the contract invoice for invoicing the periodic service commitments. It must be an item with the **Service Commitment Option**=**Invoicing Item**.|Optional|
|Notice Period (Dateformula)|Specifies a Dateformula for the lead time that a cancellation must have before the service commitment is ended. The **Subsequent Term** is also used to determine the rate at which **Cancellation Possible Until** and **Term Until** are updated. Thus, for a subsequent term of **1M**, the notice period is recurrently postponed by one month.|Optional|
|Initial Term (Dateformula)|Specifies a Dateformula for calculating the minimum term of the service commitment. If the **Initial Term** is filled in and no **Subsequent Term** is entered, the **Service End Date** is automatically set to the end of the initial term.|Optional|
|Subsequent Term (Dateformula)|Specifies a Dateformula for automatic extension after the initial term and the rhythm of updating **Cancellation Possible Until** and **Term Until**. If the field is blank, and either the initial term or the notice period are set at the same time, the service end date is automatically set to the expiration date of the initial term or the notice period.|**Always**|
|Billing Rhythm (Dateformula)|Specifies the rhythm at which the service commitments are billed. Via a Dateformula, the rhythm can be set to, for example, monthly, quarterly, or yearly calculation.|**Always**|
|Print Line (Boolean)|Specifies whether a line is output when the sales document is printed.|Optional|
|Formatting (Option: Normal, Bold, Italic)|Specifies whether a line in the sales document is printed bold or italic (default: *Normal*).|Optional|
|Print Discount % (Boolean)|Specifies whether the line discount percentage is printed for the line in the sales document (default: *Yes*).|Optional|
|New Page (Boolean)|Specifies whether a new page should be started with this line in the sales document (default: *No*).|Optional|
|Print Quantity only (Boolean)|Specifies that only the quantity (without sales price) is printed for the corresponding line in the sales document (default: *No*).|Optional |

* Mandatory fields always apply to the creation of billable contract lines. Mandatory fields, for example, for comment lines, differ.

If the processing is successful, service commitments and contract lines are created and **Service Object created** is selected.

* The **Processed by** field shows the user who performed the processing.
* The **Processed on** field shows the date and time of the processing.
* Errors display in the **Error Text** field.

> [!TIP]
> To create a comments line in a contract, the **Contract No.**, **Description**, and **Invoicing via**=*Contract* must be entered.

The following fields only need to be considered if you use a currency different from the local currency. The contract defines the currency. To avoid the conversion at a different rate, you can import currencies.

|Name|Description|To be filled|
|:--|:--|:--|
|Discount Amount (MW) (Decimal)|Indicates the discount amount in local currency that applies to the service commitments.|Optional|
|Service Amount (MW) (Decimal)|Indicates the amount minus the discount granted in local currency. In the contract, the **Service Amount** and not the **Service Amount (MW)** is used for invoicing.|Optional|
|Currency Code (Code10)|Indicates the currency for the service commitments.|Optional|
|Currency Factor (Decimal)|Indicates the currency factor valid for the service commitments, which is used to convert the amounts into local currency.|Optional|
|Date Currency Factor (Date)|Indicates the date when the currency factor was last updated.|Optional|
|Calculation Base Amount (MW) (Decimal)|Indicates the basis on which the price in local currency is calculated.|Optional|

The fields in the following table only need to be considered if billing is to take place with usage based billing.

|Name|Description|To be filled|
|:--|:--|:--|
|Usage Based Billing (Boolean)|Indicates whether usage data is used as the basis for invoicing.|Optional|
|Usage Based Pricing (Option: Usage Quantity, Fixed Quantity, Unit Cost Surcharge)|Specifies the method for calculating prices on the customer side.|Optional|
|Pricing Unit Cost Surcharge % (Decimal)|Specifies the surcharge as a percent for the customer price calculation, if you use unit cost surcharge.|Optional|
|Supplier Reference Entry No. (Integer)|Indicates the sequence number of the related reference.|Optional|

## Related information

[General setup](general.md)  
[Contract types](contract-types.md)
