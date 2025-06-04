---
title: Glossary 
description: Explore terminology in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: glossary
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Glossary

The most important terms can be looked up in this glossary.

## A

* **Additional Service Commitments** <br/> Service commitments that can be selected in addition to the standard service commitments.

## B

* **Billing Base Period** <br/> The period of time to which the Service Amount applies. For example, enter 1M here if the amount refers to one month or 12M if the amount refers to one year.
* **Billing Date** <br/> The cut-off date by which service commitments to be billed are considered.
* **Billing line** <br/> Shows the history of billing contract lines. When you post recurring bills, they're created from the billing proposal lines.
* **Billing Proposal** <br/> The billing lines created using one or more billing templates become a billing proposal. The proposal is the basis for creating the contract invoices.
* **Billing Proposal Lines** <br/> Proposal lines are a preview of the billing lines. Lines for the same contract line and different billing periods are combined in the invoice.
* **Billing Rhythm** <br/> Specifies the rhythm at which the service commitments are billed. A Dateformula can be used to set the rhythm to, for example, monthly, quarterly or annual calculation.
* **Billing Template** <br/> The Default name used to determine the service commitments to be billed.

## C

* **Calculation Base %** <br/> The percentage for calculating the price of the service commitment. 100% means that the price of the service is equal to the Calculation Base Amount.
* **Calculation Base Amount** <br/> The base amount for calculating the price.
* **Calculation Base Type** <br/> Indicates how the service commitment price is calculated. "Item Price" uses the list price that is stored on the item. "Document Price" uses the price from the sales document. **Document Price and Discount** uses the price and discount from the sales document.
* **Contract** <br/> Contract refers to customer and vendor contracts.
* **Contract Deferrals** <br/> Costs and revenues that are posted in a specific period but relate to a future period can be deferrals. These deferrals can be displayed across the board or per contract.
* **Contract line** <br/> Services commitments assigned to a contract automatically create contract lines that you bill via the **Recurring Billing** page.
* **Contract Type** <br/> Indicates the classification of the contract.
* **Contractor** <br/> Customer or supplier for whom the contract is created.
* **Credit Memo Preview** <br/> Function for creating a print preview for an unposted credit memo.
* **Customer Contract** <br/> Customer Contracts can be used to retrieve and process customer-side service commitments before you bill customers.

## D

* **Detail Overview** <br/> Specifies whether the billing details for the contract are automatically output with invoices and credit memos.

## E

* **End User** <br/> The end user is the customer to whom the service commitments were sold. You specify end users for service objects.

## I

* **Initial Term** <br/> The Dateformula used to calculate the minimum term of service commitment. If the **Initial Term** is specified but you don't enter a **Subsequent Term**, the **Service End Date** is set to the end of the **Initial Term**.
* **Invoice Preview** <br/> Action to create a print preview for an unposted invoice.
* **Invoicing Item** <br/> An item so identified is used to bill extra service commitments sold for another item.
* **Invoicing Item No.** <br/> Indicates which item in the contract invoice is used to bill for the periodic service in a service commitment package line.
* **Invoicing via** <br/> Indicates whether the service is billed via a contract or sales document in a service commitment package line.

## N

* **Next Billing Date** <br/> Indicates the date of the next possible billing in service commitments and contract lines.

## P

* **Posting document** <br/> These documents are invoices or credit notes that aren't posted.
* **Price Group** <br/> Specifies the customer price group (for example, in the service commitment package) that is considered in pricing the service commitments.

## R

* **Recurring Billing** <br/> This page first creates the billing proposal and then the posting documents.
* **Released** <br/> Revenues and costs for contracts are deferred by default under certain conditions. If the deferrals were released, this is marked accordingly.

## S

* **Sales Service Commitment** <br/> Services that are part of a line in the quote or order.
* **Service Amount** <br/> Indicates the amount of a service commitment minus the discount granted.
* **Service Commitment** <br/> Service commitments represent obligations to customers and vendors.
* **Service Commitment Item** <br/> Can be used in sales documents, but are charged exclusively through contracts.
* **Service Commitment Option** <br/> Indicates whether a service commitment can be deposited for an item or whether it's an item for billing services.
* **Service Commitment Package** <br/> Use to bundle service commitment package lines and manage price groups. Assign service commitment packages to items.
* **Service Commitment Package Line** <br/> Specifications for service commitments are defined using the service commitment package line. When the item is entered in a quote or order, the specifications from the service commitment package line are applied to the service.
* **Service Commitment Start Formula** <br/> Specifies the date from which a service commitment is valid using a formula. By using this Dateformula, the validity can be automatically set to, for example, the first of the following month. If the field remains empty, the service commitment is valid from delivery.
* **Service Commitment Template** <br/> Serves as the default for a service commitment and can be selected in the service commitment package line.
* **Service End Date** <br/> Indicates the date until which the service commitment is valid.
* **Service Object** <br/> service objects represent a history of products sold to a customer. Service commitments are created in service objects.
* **Service Start Date** <br/> The date from which the service commitments are valid and charged.
* **Subsequent Term** <br/> Specifies a Dateformula for automatic renewal after the Initial Term and the rate at which "Cancellation Possible Until" and "Term Until" are updated. If the field is blank and either the Initial Term or the Notice Period is set at the same time, the Service End Date is automatically set to the expiration date of the Initial Term or the Notice Period.

## U

* **Update Service Dates** <br/> This action updates the cancellation dates.

## V

* **Vendor Contract** <br/> Vendor Contracts can be used to retrieve and process vendor-side service commitments before creating vendor posting documents.

## Related information

[Overview of subscription billing](welcome.md)  
[Overview of usage based billing](../UBB/welcome.md)
