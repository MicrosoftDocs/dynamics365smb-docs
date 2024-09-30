---
title: Service commitments in service objects
description: You can use service commitments in subscription and recurring billing.
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

# Service commitments

Service Commitments describe the monetary content of agreements with customers and suppliers as well as termination dates. In order for a Service Commitments to be billed recurrently, it must be assigned to a contract.

A Service Commitment is valid if **Invoicing via** is set to *Contract* and the **Service End Date** is either blank or the **Next Billing Date** has not reached the Service End Date. Service Commitments with Invoicing via *Sales* are used to store information and are not billed on a recurring basis.
If a Service Commitments is assigned to a contract, almost all changes can be made in the contract. The quantity of Service Commitments cannot be changed in the contract.

> [!NOTE]
> * If the **Next Billing Date** reaches the **Service End Date**, it isn't available. These service commitments are considered ended and can no longer be billed.
> * An example of a service that should not be billed recurringly but store information about the sale is a warranty extension. It is billed once through the sales order. The information about how long the extension is valid is stored in the service commitments.

## Editing service commitments

### Log changes to service commitments

Service commitments can be edited as lines in the **[Service Objects](/docs/srb/working-with-contracts/service-objects.md)** and contracts. If any of the following fields are edited, the service commitment is archived before the change is made:

* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Discount Amount
* Service Amount
* Billing Base Period
* Billing Rhythm

If the service amount changes due to quantity changes, the service commitment is also archived. In addition, changing the serial number will result in archiving, because the serial number is also present in the **Archived Service Commitments**.

If archived service commitments exist, the **Archived Service Commitments** checkbox on the service object is selected. Click *Yes* to display the archived service commitments, including the corresponding quantity of the service object. The timestamp and user who made the change can be viewed via the Page Inspector.

> [!NOTE]
> If several changes are made in quick succession to the same service commitment, only the original version is archived.

### Delete service commitments

You can delete service commitments if they aren't invoiced and aren't assigned to a contract. If they're assigned to a contract, the contract line can be deleted to remove the assignment. If the service commitments are already invoiced, they must first be ended by setting a **Service End Date**.

> [!NOTE]
> Contract lines and service commitments are always identical. If a contract line is edited, the change is automatically applied to the service commitments.

## See also

[Managing contracts, service objects, and services commitments](contracts-services-mgmt.md)  