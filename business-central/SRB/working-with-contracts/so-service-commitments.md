---
title: Subscription lines in subscriptions
description: You can use subscription lines with subscriptions in subscription billing.
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

# Subscription lines in subscriptions

Subscription lines describe the monetary content of agreements with customers and suppliers as well as termination dates. In order for a subscription line to be billed recurrently, it must be assigned to a contract.

A subscription line is valid if the **Invoicing via** field is set to **Contract** and the **Service End Date** field is either blank or the date in the **Next Billing Date** field hasn't reached the date in the **Service End Date**. Subscription lines with invoicing via sales are used to store information and aren't billed on a recurring basis.

If a subscription line is assigned to a contract, almost all changes can be made in the contract. The quantity of subscription lines cannot be changed in the contract.

> [!NOTE]
> * If the **Next Billing Date** reaches the **Service End Date**, it isn't available. These subscription lines are considered ended and can no longer be billed.
> * An example of a service that should not be billed recurringly but store information about the sale is a warranty extension. It is billed once through the sales order. The information about how long the extension is valid is stored in the subscription lines.

## Editing subscription lines

### Log changes to subscription lines

Subscription lines can be edited in subscriptions. To learn more, go to [Subscriptions](service-objects.md) and contracts.

If any of the following fields are edited, the subscription line is archived before the change is made:

* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Discount Amount
* Service Amount
* Billing Base Period
* Billing Rhythm

If the service amount changes due to quantity changes, the subscription line is also archived. In addition, changing the serial number will result in archiving, because the serial number is also present in the **Archived Subscription Lines**.

If archived subscription lines exist, the **Archived Subscription Lines** checkbox on the subscription is selected. Choose **Yes** to display the archived subscription lines, including the corresponding quantity of the subscription. The timestamp and user who made the change can be viewed via the Page Inspector.

> [!NOTE]
> If several changes are made in quick succession to the same subscription line, only the original version is archived.

### Delete subscription lines

You can delete subscription lines if they aren't invoiced and aren't assigned to a contract. If they're assigned to a contract, the contract line can be deleted to remove the assignment. If the subscription lines are already invoiced, they must first be ended by chosing a date in the **Service End Date** field.

> [!NOTE]
> Contract lines and subscription lines are always identical. If a contract line is edited, the change is automatically applied to the subscription lines.

## Related information

[Managing contracts, subscriptions, and subscription lines](contracts-services-mgmt.md)