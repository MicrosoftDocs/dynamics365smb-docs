---
title: Controlling
description: You can use controlling in subscription billing.
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

# Controlling

## Dimension value for customer subscription contracts

In the [General setup](setup/general.md), **Autom. Insert Cust. Contr. Dimension Value** controls whether the customer subscription contract number is automatically created as a new dimension value for each new customer subscription contract. This is then automatically assigned to the respective contract.


## Dimension Value for Customers

In the **Sales & Receivables Setup** it is controlled via **Autom. Insert Cust. Dimension Value** whether the customer number is automatically created as a new dimension value for each new customer. This is then automatically assigned to the respective customer.


## Other dimensions
* **Customer Subscription Contract** <br/>
    The **Dimensions from Project No.** field can be used to fetch the dimensions from the specified project into the respective customer subscription contract via a lookup.
* **Customer Subscription Contract Line** <br/>
    * Dimensions are basically stored on the subscription lines, but are accessible via the contract lines. When assigning subscription lines to a customer subscription contract, the dimensions of the customer subscription contract header are passed to the subscription lines. Additional dimensions are added and Dimension Values of existing dimensions are overwritten. However, no dimensions are deleted.
    * In addition, when assigning services to a customer subscription contract and updating the dimensions at the subscription lines a check is performed whether there are any vendor subscription lines that refer to the same Subscription package line template. If such a vendor Service Commitment is found, the dimensions of the customer subscription contract Header are also passed to the vendor Service Commitment(s).
    * When deleting a contract line, the dimensions of the customer subscription contract header are removed in the related subscription lines.
    * When changing a dimension in the customer subscription contract header (changing a dimension value, adding a dimension, removing a dimension), the change transfers to the subscription lines in the same way as for sales documents.
* **Vendor Subscription Contract Line** <br/>
    * When assigning services commitments to a vendor contract, the dimensions of the vendor contract header are transferred to the subscription lines. Additional dimensions are added and dimension values of existing dimensions are overwritten. However, no dimensions are deleted.
    * When deleting a contract line, the dimensions of the vendor contract header are removed in the related subscription lines.
    * When changing a dimension in the Vendor Subscription Contract Header (changing a dimension value, adding a dimension, removing a dimension), this change passes to the subscription lines on demand.
* **Subscription** <br/>
    * The item to be used for billing (i.e. the Service Commitment Item itself or an Invoicing Item) is stored in the Service Commitment. The dimensions that this item brings are transferred to the Service Commitment.
    * Since the Service Commitment is kept in sync with the contract line, changes to the Service Commitment are also made to the contract line.
* **Sales Subscription Lines** <br/>
    * The item to be used for billing, for example, the service commitment item itself or an invoicing item, is stored in the sales subscription lines. The dimensions that this item brings are transferred to the Sales subscription lines on shipment.
    * The remaining dimensions are copied from the sales line to the Subscription Lines on shipment. If there is a dimension conflict, the dimensions of the item in the Service Commitment have higher priority.
* **Recurring Billing** <br/>
    * There are no dimensions on the lines in **Recurring Billing**. However, the **Contract Line Dimensions** call can be used to access the dimensions of the related contract line.
    * When Posting Documents are created, the dimensions of the respective contract line are transferred to the corresponding document line.
* **Contract Deferrals** <br/>
    * When posting the document line, the dimensions are transferred from the document line to the deferrals.
    * It is possible via the action **Update Dimensions in Deferrals** to update the dimensions in all Contract Deferrals for a contract that have not yet been released, e.g. if the dimensions of a contract line has been changed.
* **Archived Billing Lines** <br/>
    * There are no dimensions in the Archived Billing Lines.
