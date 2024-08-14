---
title: Data migration
description: You can use import contracts and contract lines in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Import of contracts and contract lines

Before Contracts and Contract lines can be set up, some data must first be created or imported. In addition to Customers, Vendors, and Items, you need to create Service Commitment Packages, Service Commitment Package lines, and more. The import is done via configuration packages. The Customer Contracts, Contract lines, Service Objects and Service Commitments are imported into tables created specifically for processing the data.


## Import of master data
For importing Customers, Items, Service Commitments, Vendor Contracts etc., [Configuration Packages](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) can be created.

|Name|Table|
|:--|:--|
|Items|27|
|Service Commitment Templates|70920754|
|Service Commitment Packages|70920755|
|Service Commitment Package Lines|70920756|
|Item Service Commitment Packages|70920758|
|Vendor Contract|70920763|


## Import of Customer Contracts, Contract lines, Service Objects and Service Commitments
There are particular import tables for importing Customer Contracts, Contract lines, Service Objects and Service Commitments. After the import, the user can view, edit and use the data to create corresponding records in Business Central in the pages **Imported Customer Contracts**, **Imported Service Objects** and **Imported Service Commitments**. Please use the following tables to import and create Service Objects, Service Commitments and Contract lines.

|Name|Table|
|:--|:--|
|Imported Customer Contracts|70920710|
|Imported Service Objects|70920708|
|Imported Service Commitments|70920709|


### Imported Customer Contracts
The **Imported Customer Contracts** page serves as an intermediate step for the data transfer of Service Objects. The imported data is displayed in this page. The **Create Customer Contracts** action is used to create the Customer Contracts (just headers, no lines). The action always processes all rows that have not yet been processed, regardless of filters and selection.

|Name|Description|To fill|
|:--|:--|:--|
|Contract No. (Code20)|Specifies the number of the contracts to be created. The Contract lines (Service Commitments) are assigned by means of the Contract No. Note: Before processing, the number series must be set to allow manual number assignment.|**Always**|
|Sell-to Customer No. (Code20)|Indicates the number of the customer who receives the contractual services and is invoiced by default.|**Always**|
|Sell-to Contact No. (Code20)|Specifies the number of the contact that receives the contractual services. In the contract, it is filled by the Sell-to Customer No. from that customer if empty.|Optional|
|Bill-to Contact No. (Code20)|Indicates the customer to whom you send the Contract invoice. If empty the *Standard (Customer)* will be used in the contract.|Optional|
|Contract Type (Code10)|Indicates the classification of the contract.|Optional|
|Description (Text200)|Indicates the internal description of the contract.|Optional|
|Your Reference (Text35)|Indicates the reference of the customer. The content of this field will be printed on the Contract invoice.|Optional|
|Salesperson Code (Code20)|Indicates the name of the salesperson assigned to the customer.|Optional|
|Assigned User ID (Code50)|Indicates the ID of the user who is responsible for the document.|Optional|
|Without Contract Deferrals (Boolean)|Specifies whether deferrals should be generated for the contract. If the field is checked (yes), no deferrals will be generated and the invoices will be posted directly to profit or loss. Default value is *No*.|Optional|
|Detail Overview (Boolean)|Determines whether the billing details for this contract are automatically output with invoices and credit memos. Options: empty (default), Without prices, Complete|Optional|
|Dimensions from Project No. (Code20)| Specifies the Project No. from which the dimensions for the contract are to be used.|Optional|

If the processing is successful, a Customer Contract is created and **Contract Created** is set to *Yes*. In **Processed by**, the user who performed the processing is automatically entered. In **Processed on**, the date and time of the processing are shown. Errors are displayed in the **Error Text** field.


### Imported Service Objects
The **Imported Service Objects** page serves as an intermediate step for the data transfer of Service Objects. The imported data is displayed in this page. The **Create Service Objects** action is used to create the Service Objects. The action will always process all lines that have not yet been processed, regardless of filters and selection.

|Name|Description|To be filled|
|:--|:--|:--|
|Entry No. (Integer)|System field of the table (consecutive number of records) - is created automatically and is in the background|*Never*|
|Service Object No. (Code20)|The Service Object is created with this number. To facilitate the assignment of Service Commitments, this number should always be imported. Note: Before processing, the number series must be set to allow manual number assignment.|**Always**|.
|Customer No. (Code20)|Indicates the number of the customer to whom the Service Commitments were sold. It is mandatory for the assignment to Customer Contracts.|**Always**|
|Item No. (Code20)|Indicates the Item No. of the Service Object. It should be an item with Service Commitments or a Service Commitment Item.|**Always**|
|Description (Text100)|Indicates the description of the Service Object. If the description is empty, it will be filled by the item when the Service Object is created.|Optional|
|Quantity (Decimal)|Indicates the quantity of the Service Object.|**Always**|
|Customer Reference (Text35)|Indicates the reference by which the customer knows the Service Object.|Optional|
|Bill-to Cust. No. (Code20)|A different invoice recipient (Customer) can be specified here. Related fields will be filled automatically (e.g. Bill-to Contact No. etc.).|Optional|
|Bill-to Contact No. (Code20)|A different invoice recipient (Contact) can be specified here.|Optional|
|Ship-to Code (Code10)|A different shipment address can be specified here. Related fields will be filled automatically.|Optional|
|Contact No. (Code20)|Can be specified if different from primary contact.|Optional|
|Unit of measure (Code10)|Can be specified if different from the unit of the item.|Optional|
|Serial No. (Code50)|Indicates the serial number of the Service Object. Service Objects with serial number can only have a **Quantity**=*1*.|Optional|
|Provision Start Date (Date)|Indicates the date from which the Service Object and the related Service Commitments were provided to the customer. It has no relevance for billing.|Optional|
|Provision End Date (Date)|Indicates the date from which the Service Object and related Service Commitments are no longer available to the customer. It has no relevance for billing.|Optional|
|Key (Text100)|Displays a key in the Service Object.|Optional|
|Version (Text100)|Display of the version in the Service Object.|Optional|

If the processing is successful, a Service Object is created and **Service Object Created** is set to *Yes*. In **Processed by**, the user who performed the processing is automatically entered. In **Processed on**, the date and time of the processing are shown. Errors are displayed in the **Error** field.


### Imported Service Commitments
The **Imported Services Commitments** page serves as an intermediate step for the data transfer of Service Commitments and Contract lines. The data is imported into this page and processed using the **Create Service Commitments** action. This can be used to create comment lines in Contracts, Service Commitments that are not billed, as well as Contract lines and Service Commitments that are billed. The action will always process all lines that have not yet been processed, regardless of filters and selection.

|Name|Description|To be filled|
|:--|:--|:--|
|Entry No. (Integer)|System field of the table (consecutive number of records) - is created automatically and is in the background|*Never*|
|Service Object No. (Code20)|The created Service Commitment will be assigned to this Service Object.|**Always**|
|Service Commitment Line No. (Integer)|Indicates the line number of the service in the Service Object. If no line number is specified, one will be determined automatically.|Optional|
|Partner (Option: Customer, Vendor)|Indicates if the Service Commitments should be invoiced vendor-side (Purchase Invoice) or customer-side (Sales Invoice).|**Always**|
|Contract (Code20)|Indicates the number of the contract in which the Service Commitment is to be created as a Contract line. Service Commitments with **Invoicing via**=*Sales* cannot be called up in Contracts.|Optional|
|Contract Line No. (Integer)|Indicates the line number of the Contract line. If no line number is specified, one will be determined automatically.|Optional|
|Contract Line Type (Option: Comment, Service Commitment)|Specifies the type of the Contract line.|**Always**|
|Package Code (Code20)|Specifies the code of the Service Commitment Package. If a Vendor Contract line has the same Service Object and Package code as the Customer Contract line, the Customer Contract dimension will be copied to the Vendor Contract line.|Optional|
|Template Code (Code20)|Indicates the name of the underlying Service Commitment Template from which the Service Commitment was copied to the Service Commitment Package. It has a purely informative character.|Optional|
|Description (Text100)|Indicates the description of the Service Commitments. If no description is specified, it will be filled based on the Service Commitments.|**Always**|.
|Service Start Date (Date)|Indicates from which date the Service Commitments is valid and will be charged.|**Always**|
|Service End Date (Date)|Indicates until which date the Service Commitments is valid.|Optional|
|Next Billing Date (Date)|Indicates the date of the next possible billing. If the field is empty, it will be filled automatically by the Service Start Date.|Optional|
|Calculation Base Amount (Decimal)|Indicates the base amount from which the price will be calculated. *Note: The field **Price** (in Service Commitments) is always calculated and* never *imported*.|**Always**|
|Calculation Base % (Decimal)|Indicates with which percentage the Service Commitment price is calculated. 100 % means that the price of the Service Commitment is equal to the Calculation Base Amount.|**Always**|
|Discount % (Decimal)|Indicates the percentage discount for the Service Commitments.|Optional|
|Discount Amount (Decimal)|Indicates the discount amount that will be applied to the Service Commitments. Only Discount % or Discount Amount must be filled for the import to apply a discount.|Optional|
|Service Amount (Decimal)|Indicates the amount minus the discount granted. The Service Amount is calculated from Calculation Base Amount, Calculation Base %, Quantity, and Discount if the field is not filled.|Optional|
|Calculation Base Period (Dateformula)|Indicates the period to which the Service Amount refers. For 1M the amount refers to one month or 12M if the amount refers to 1 year.|**Always**|
|Invoicing via (Option: Sales, Contract)|Indicates whether the Service Commitment is invoiced via a Contract. Service Commitments with **Invoicing via**=*Sales* are not invoiced and cannot be transferred to a Contract.|**Always**|
|Invoicing Item No. (Code20)|Indicates which item is used in the Contract invoice for invoicing the periodic Service Commitments. It must be an item with the **Service Commitment Option**=*Invoicing Item*.|Optional|
|Notice Period (Dateformula)|Specifies a Dateformula for the lead time that a cancellation must have before the Service Commitment is terminated. The Subsequent Term is also used to determine the rate at which **Cancellation Possible Until** and **Term Until** are updated. Thus, for a Subsequent Term of 1M, the notice period is recurrently postponed by one month.|Optional|
|Initial Term (Dateformula)|Specifies a Dateformula for calculating the minimum term of the Service Commitment. If the Initial Term is filled and no Subsequent Term is entered, the Service End Date is automatically set to the end of the Initial Term.|Optional|
|Subsequent Term (Dateformula)|Specifies a Dateformula for automatic extension after the Initial Term and the rhythm of updating **Cancellation Possible Until** and **Term Until**. If the field is blank and either the Initial Term or the Notice Period is set at the same time, the Service End Date is automatically set to the expiration date of the Initial Term or the Notice Period.|**Always**|.
|Billing Rhythm (Dateformula)|Specifies the rhythm at which the Service Commitments will be billed. Via a Dateformula the rhythm can be set to e.g. monthly, quarterly or yearly calculation.|**Always**|
|Print Line (Boolean)|Specifies whether a line is output when the sales document is printed.|Optional|
|Formatting (Option: Normal, Bold, Italic)|Specifies whether a line in the sales document is printed bold or italic (default: *Normal*).|Optional|
|Print Discount % (Boolean)|Specifies whether the line discount percentage is printed for the line in the sales document (default: *Yes*).|Optional|
|New Page (Boolean)|Specifies whether a new page should be started with this line in the sales document (default: *No*).|Optional|
|Print Quantity only (Boolean)|Specifies that only the quantity (without sales price) is printed for the corresponding line in the sales document (default: *No*).|Optional|
*Mandatory fields (always) apply to the creation of billable Contract lines. Mandatory fields e.g. for comment lines differ.

If the processing is successful, Service Commitments and Contract lines are created and **Service Object created** is set to *Yes*. In **Processed by**, the user who performed the processing is automatically entered. In **Processed on**, the date and time of processing are shown. Errors are displayed in the **Error** field.

:::tip Tip
To create a comments line in a contract, the **Contract No.**, **Description** and **Invoicing via**=*Contract* must be entered.
:::


The following fields only need to be considered if a currency different from the local currency is used. The currency is defined by the contract. To avoid the conversion at a different rate, currencies can be imported.

|Name|Description|To be filled|
|:--|:--|:--|
|Discount Amount (MW) (Decimal)|Indicates the discount amount in local currency that will be applied to the Service Commitments.|Optional|
|Service Amount (MW) (Decimal)|Indicates the amount minus the discount granted in local currency. In the Contract, the Service Amount and not the Service Amount (MW) in is used for invoicing.|Optional|
|Currency Code (Code10)|Indicates the currency for the Service Commitments.|Optional|
|Currency Factor (Decimal)|Indicates the currency factor valid for the Service Commitments, which is used to convert the amounts into local currency.|Optional|
|Date Currency Factor (Date)|Indicates the date when the currency factor was last updated.|Optional|
|Calculation Base Amount (MW) (Decimal)|Indicates the basis on which the price in local currency is calculated.|Optional|

The following fields only need to be considered if billing is to take place with **[DYCE Usage Based Billing](/docs/ubb/welcome.md)**:

|Name|Description|To be filled|
|:--|:--|:--|
|Usage Based Billing (Boolean)|Indicates whether usage data is used as the basis for invoicing.|Optional|
|Usage Based Pricing (Option: Usage Quantity, Fixed Quantity, Unit Cost Surcharge, Consumed Quantity)|Specifies the method for calculating prices on the Customer side.|Optional|
|Pricing Unit Cost Surcharge % (Decimal)|Specifies the surcharge in percent for the Customer price calculation, if Unit Cost Surcharge is to be used.|Optional|
|Supplier Reference Entry No. (Integer)|Indicates the sequence number of the related reference.|Optional|