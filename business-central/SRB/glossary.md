---
title: Glossary 
description: Explore terminology in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Glossary

The most important terms can be looked up in this glossary.

## A
* **Additional Service Commitments** <br/> Service Commitments that can be selected in addition to the standard Service Commitments.

## B
* **Billing Base Period** <br/> The period of time to which the Service Amount applies. For example, enter 1M here if the amount refers to one month or 12M if the amount refers to 1 year.
* **Billing Date** <br/> The cut-off date by which Service Commitments to be billed will be considered.
* **Billing line** <br/> Shows the history of billing contract lines. When posting recurring bills, they are created from the Billing Proposal Lines.
* **Billing Proposal** <br/> The billing lines created using one or more Billing Templates form a Billing Proposal. This is the basis for creating the contract invoices.
* **Billing Proposal Lines** <br/> Are a preview of billing lines. Lines for the same contract line and different billing periods are combined in the invoice.
* **Billing Rhythm** <br/> Specifies the rhythm at which the Service Commitments will be billed. A Dateformula can be used to set the rhythm to, for example, monthly, quarterly or annual calculation.
* **Billing Template** <br/> The Default name used to determine the Service Commitments to be billed.
* **Bundle** <br/> A bundle is a combination of individual components into a stand-alone product.

## C
* **Calculation Base %** <br/> The percentage at which the price of the Service Commitments is calculated. 100% means that the price of the service is equal to the Calculation Base Amount.
* **Calculation Base Amount** <br/> The basis on which the price is calculated.
* **Calculation Base Type** <br/> Indicates how the Service Commitments price is calculated. "Item Price" uses the list price that is stored on the item. "Document Price" uses the price from the sales document. "Document Price And Discount" uses the price *and* discount from the sales document.
* **Contract** <br/> This refers to customer and vendor contracts.
* **Contract Deferrals** <br/> Costs and revenues that are posted in a specific period but relate to a future period can be deferrals. These deferrals can be displayed across the board or per contract.
* **Contract line** <br/> Services Commitments assigned to a contract automatically create contract lines. These are billed via Recurring Billing.
* **Contract Type** <br/> Indicates the classification of the contract.
* **Contractor** <br/> Customer or supplier for whom the contract is created.
* **Credit Memo Preview** <br/> Function for creating a print preview for an unposted credit memo.
* **Customer Contract** <br/> Customer Contracts can be used to retrieve and process customer-side Service Commitments before they are subsequently billed to the appropriate customers.

## D
* **Detail Overview** <br/> Specifies whether the billing details for the contract are automatically output with invoices and credit memos.

## E
* **End User** <br/> The End User is the customer to whom the Service Commitments were sold. This can be entered in the Service Object.

## I
* **Initial Term** <br/> The Dateformula used to calculate the minimum term of the Service Commitments. If the Initial Term is filled and no Subsequent Term is entered, the Service End Date will automatically be set to the end of the Initial Term.
* **Invoice Preview** <br/> Function to create a print preview for an unposted invoice.
* **Invoicing Item** <br/> An item so identified is used for billing additional Service Commitments sold for another item.
* **Invoicing Item No.** <br/> Indicates (in the Service Commitment Package Line) which item in the contract invoice is used to bill for the periodic service.
* **Invoicing via** <br/> Indicates (in the Service Commitment Package Line) whether the service is billed via a contract or sales document.

## N
* **Next Billing Date** <br/> Indicates (in the Service Commitments and contract lines) the date of the next possible billing.

## P
* **Position Number** <br/> A number or designation can be entered in each position in sales documents. The Position Numbers will be printed.
* **Posting document** <br/> This is an invoice or credit note that has not yet been posted.
* **Price Group** <br/> Specifies the customer price group (e.g., in the Service Commitment Package) that will be considered in pricing the Service Commitments.

## R
* **Recurring Billing** <br/> This page will first create the Billing Proposal and then the posting documents.
* **Released** <br/> Revenues and costs for contracts are deferred by default (and under certain conditions). If the deferrals were released this is marked accordingly.
* **Report Configurations** <br/> Used to configure for the document footer.
* **Role Center** <br/> Home page in Microsoft Dynamics 365 Business Central

## S
* **Sales Service Commitment** <br/> This refers to services that are part of a line in the quote or order.
* **Service Amount** <br/> Indicates the amount of a Service Commitments minus the discount granted.
* **Service Commitment** <br/> Service Commitments represent obligations to customers and vendors.
* **Service Commitment Item** <br/> ...may be used in sales documents, but are charged exclusively through contracts.
* **Service Commitment Option** <br/> Indicates whether a Service Commitments can be deposited for an item or whether it is an item for billing services.
* **Service Commitment Package** <br/> This is used to bundle Service Commitment Package lines and manage price groups. Service Commitment Packages can be stored on items.
* **Service Commitment Package Line** <br/> Specifications for Service Commitments are defined using the Service Commitment Package Line. When the item is entered in a quote or order, the specifications from the Service Commitment Package Line are applied to the service.
* **Service Commitment Start Formula** <br/> Specifies the date from which a Service Commitments is valid using a formula. Using this Dateformula, the validity can be automatically set to, for example, the first of the following month. If the field remains empty, the Service Commitments is valid from delivery.
* **Service Commitment Template** <br/> Serves as the Default for a Service Commitment and can be selected in the Service Commitment Package Line.
* **Service End Date** <br/> Indicates the date until which the Service Commitments is valid.
* **Service Object** <br/> Service Objects represent a history of products sold to a customer. Service Commitments are created in Service Objects.
* **Service Start Date** <br/> The date from which the Service Commitments are valid and charged.
* **Subsequent Term** <br/> Specifies a Dateformula for automatic renewal after the Initial Term and the rate at which "Cancellation Possible Until" and "Term Until" are updated. If the field is blank and either the Initial Term or the Notice Period is set at the same time, the Service End Date is automatically set to the expiration date of the Initial Term or the Notice Period.

## U
* **Update Service Dates** <br/> This action updates the cancellation dates.

## V
* **Vendor Contract** <br/> Vendor Contracts can be used to retrieve and process vendor-side Service Commitments before subsequently creating vendor posting documents.