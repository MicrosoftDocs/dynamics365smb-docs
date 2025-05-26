---
title: Service commitments in service objects
description: You can use service commitments with service objects in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Service commitments in service objects

Service commitments describe the monetary content of agreements with customers and suppliers as well as termination dates. In order for a service commitment to be billed recurrently, it must be assigned to a contract.

A service commitment is valid if the **Invoicing via** field is set to **Contract** and the **Service End Date** field is either blank or the date in the **Next Billing Date** field hasn't reached the date in the **Service End Date**. Service commitments with invoicing via sales are used to store information and aren't billed on a recurring basis.

If a service commitments is assigned to a contract, almost all changes can be made in the contract. The quantity of service commitments cannot be changed in the contract.

> [!NOTE]
> * If the **Next Billing Date** reaches the **Service End Date**, it isn't available. These service commitments are considered ended and can no longer be billed.
> * An example of a service that should not be billed recurringly but store information about the sale is a warranty extension. It is billed once through the sales order. The information about how long the extension is valid is stored in the service commitments.

## Editing service commitments

### Log changes to service commitments

Service commitments can be edited as lines in the service objects. To learn more, go to [Service objects](service-objects.md) and contracts.

If any of the following fields are edited, the service commitment is archived before the change is made:

* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Discount Amount
* Service Amount
* Billing Base Period
* Billing Rhythm

If the service amount changes due to quantity changes, the service commitment is also archived. In addition, changing the serial number will result in archiving, because the serial number is also present in the **Archived Service Commitments**.

If archived service commitments exist, the **Archived Service Commitments** checkbox on the service object is selected. Choose **Yes** to display the archived service commitments, including the corresponding quantity of the service object. The timestamp and user who made the change can be viewed via the Page Inspector.

> [!NOTE]
> If several changes are made in quick succession to the same service commitment, only the original version is archived.

### Delete service commitments

You can delete service commitments if they aren't invoiced and aren't assigned to a contract. If they're assigned to a contract, the contract line can be deleted to remove the assignment. If the service commitments are already invoiced, they must first be ended by chosing a date in the **Service End Date** field.

> [!NOTE]
> Contract lines and service commitments are always identical. If a contract line is edited, the change is automatically applied to the service commitments.

## Related information

[Managing contracts, service objects, and services commitments](contracts-services-mgmt.md)  
