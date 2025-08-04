---
title: Controlling
description: You can use controlling in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Controlling

## Dimension value for customer contracts

In the [General setup](setup/general.md), **Autom. Insert Cust. Contr. Dimension Value** controls whether the Customer Contract No. is automatically created as a new dimension value for each new Customer Contract. This is then automatically assigned to the respective contract.


## Dimension Value for Customers

In the **Sales & Receivables Setup** it is controlled via **Autom. Insert Cust. Dimension Value** whether the customer number is automatically created as a new dimension value for each new customer. This is then automatically assigned to the respective customer.


## Other dimensions
* **Customer Contract** <br/>
    The **Dimensions from Project No.** field can be used to fetch the dimensions from the specified Project into the respective Customer Contract via lookup.
* **Customer Contract Line** <br/>
    * Dimensions are basically stored at the Service Commitments, but are accessible via the contract lines. When assigning Services Commitments to a Customer Contract, the dimensions of the Customer Contract header are passed to the Service Commitments. Additional dimensions are added and Dimension Values of existing dimensions are overwritten. However, no dimensions are deleted.
    * In addition, when assigning services to a Customer Contract and updating the dimensions at the Service Commitments a check is performed whether there are any vendor Service Commitments that refer to the same Service Commitment Template. If such a vendor Service Commitment is found, the dimensions of the Customer Contract Header are also passed to the vendor Service Commitment(s).
    * When deleting a contract line, the dimensions of the Customer Contract Header are removed in the related Service Commitments.
    * When changing a dimension in the Customer Contract Header (changing a Dimension Value, adding a Dimension, removing a Dimension), this change will be transferred to the Service Commitments on request. Here the system behaves in the same way as for sales documents.
* **Vendor Contract Line** <br/>
    * When assigning Services Commitments to a Vendor Contract, the dimensions of the Vendor Contract header are transferred to the Service Commitments. Additional dimensions are added and Dimension Values of existing dimensions are overwritten. However, no dimensions are deleted.
    * When deleting a contract line, the dimensions of the Vendor Contract Header are removed in the related Service Commitments.
    * When changing a dimension in the Vendor Contract Header (changing a Dimension Value, adding a Dimension, removing a Dimension), this change will be passed to the Service Commitments on demand.
* **Service Object** <br/>
    * The item to be used for billing (i.e. the Service Commitment Item itself or an Invoicing Item) is stored in the Service Commitment. The dimensions that this item brings are transferred to the Service Commitment.
    * Since the Service Commitment is kept in sync with the contract line, changes to the Service Commitment are also made to the contract line.
* **Sales Service Commitments** <br/>
    * The item to be used for billing (i.e. the Service Commitment Item itself or an Invoicing Item) is stored in the Sales Service Commitment. The dimensions that this item brings are transferred to the Sales Service Commitment on shipment.
    * The remaining dimensions are copied from the Sales Line to the Service Commitments on shipment. If there is a dimension conflict, the dimensions of the item in the Service Commitment have higher priority.
* **Recurring Billing** <br/>
    * There are no dimensions on the lines in **Recurring Billing**. However, the **Contract Line Dimensions** call can be used to access the dimensions of the related contract line.
    * When Posting Documents are created, the dimensions of the respective contract line are transferred to the corresponding document line.
* **Contract Deferrals** <br/>
    * When posting the document line, the dimensions are transferred from the document line to the deferrals.
    * It is possible via the action **Update Dimensions in Deferrals** to update the dimensions in all Contract Deferrals for a contract that have not yet been released, e.g. if the dimensions of a contract line has been changed.
* **Archived Billing Lines** <br/>
    * There are no dimensions in the Archived Billing Lines.
