---
title: Controlling
description: You can use controlling in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 
ms.date: 07/16/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Controlling

## Dimension value for customer subscription contracts

On the [General setup](setup/general.md), **Autom. Insert Cust. Contr. Dimension Value** controls whether the customer subscription contract number is automatically created as a new dimension value for each new customer subscription contract. This value is then automatically assigned to the respective contract.

## Dimension value for customers

On the **Sales & Receivables Setup** page, the **Autom. Insert Cust. Dimension Value** controls whether the customer number is automatically created as a new dimension value for each new customer. This value is then automatically assigned to the respective customer.

## Other dimensions

* **Customer Subscription Contract**
    You can use the **Dimensions from Project No.** field to get the dimensions from the specified project into the respective customer subscription contract via a lookup.
* **Customer Subscription Contract Line**
    * Dimensions are stored on the subscription lines, but are accessible via the contract lines. When you assign subscription lines to a customer subscription contract, the dimensions of the customer subscription contract header pass to the subscription lines. More dimensions are added and dimension values of existing dimensions are overwritten. However, no dimensions are deleted.
    * Also, when you assign services to a customer subscription contract and update the dimensions at the subscription lines, the system looks for vendor subscription lines that refer to the same subscription package line template. If such a vendor subscription line is found, the dimensions of the customer subscription contract header are also passed to the vendor subscription lines.
    * When you delete a contract line, the dimensions of the customer subscription contract header are removed in the related subscription lines.
    * When you change a dimension in the customer subscription contract header (changing a dimension value, adding a dimension, removing a dimension), the change transfers to the subscription lines in the same way as for sales documents.
* **Vendor Subscription Contract Line**
    * When you assign subscription lines to a vendor contract, the dimensions of the vendor contract header are transferred to the subscription lines. More dimensions are added and dimension values of existing dimensions are overwritten. However, no dimensions are deleted.
    * When you delete a contract line, the dimensions of the vendor contract header are removed in the related subscription lines.
    * When you change a dimension in the Vendor Subscription Contract Header (changing a dimension value, adding a dimension, removing a dimension), this change passes to the subscription lines on demand.
* **Subscription**
    * The item to be used for billing (for example, the subscription line item itself or an invoicing item) is stored in the subscription line. The dimensions that this item brings transfer to the subscription line.
    * Because the subscription line is kept in sync with the contract line, changes to the subscription line are also made to the contract line.
* **Sales Subscription Lines**
    * The item to be used for billing, for example, the subscription line item itself or an invoicing item, is stored in the sales subscription lines. The dimensions that this item brings are transferred to the Sales subscription lines on shipment.
    * The remaining dimensions are copied from the sales line to the Subscription Lines on shipment. If there's a dimension conflict, the dimensions of the item in the subscription line have higher priority.
* **Recurring Billing**
    * There are no dimensions on the lines in **Recurring Billing**. However, the **Contract Line Dimensions** call can be used to access the dimensions of the related contract line.
    * When Posting Documents are created, the dimensions of the respective contract line are transferred to the corresponding document line.
* **Contract Deferrals**
    * When you post the document line, the dimensions transfer from the document line to the deferrals.
    * You can use the **Update Dimensions in Deferrals** action to update the dimensions in all contract deferrals for a contract that isn't released. For example, if the dimensions of a contract line changed.
* **Archived Billing Lines**
    * There are no dimensions in the archived billing lines.

## Related information

[Managing contracts, subscriptions, and subscription lines](working-with-contracts/contracts-services-mgmt.md)  
