---
title: Planned subscription lines in subscriptions
description: You can use planned subscription lines with subscriptions in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8014, 8004_Primary
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Planned subscription lines in subscriptions

On the **Planned Subscription Lines** page, subscription lines describe the monetary content of agreements with customers and suppliers as well as termination dates. In order for a subscription line to be billed recurrently, it must be assigned to a contract.

A subscription line is valid if the **Invoicing via** field is set to **Contract** and the **Subscription Line End Date** field is either blank or the date in the **Next Billing Date** field hasn't reached the date in the **Subscription Line End Date**. Subscription lines with invoicing via Sales are used to store information and aren't billed on a recurring basis.

If a subscription line is assigned to a contract, almost all changes can be made in the contract. For example, an exception is that you can't change the quantity on subscription lines.

> [!NOTE]
>
> * If the **Next Billing Date** reaches the **Subscription Line End Date**, it isn't available. These subscription lines are considered ended and can no longer be billed.
> * An example of a subscription line that should not be billed recurrently but store information about the sale is a warranty extension that's billed one time through the sales order. The information about how long the extension is valid is stored in the subscription lines.

## Log changes to subscription lines

You can edit subscription lines in subscriptions. To learn more, go to [Subscriptions](service-objects.md).

If any of the following fields are edited, the subscription line is archived before the change is made:

* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Discount Amount
* Amount
* Billing Base Period
* Billing Rhythm

If the amount changes due to quantity changes, the subscription line is also archived. In addition, changing the serial number will also result in archiving the subscription line; the serial number is also available in the archived subscription lines.

If archived subscription lines exist, the **Archived Subscription Lines** checkbox on the subscription is selected. Choose **Yes** to display the archived subscription lines, including the corresponding quantity of the subscription. The timestamp and user who made the change can be viewed via the Page Inspector.

> [!NOTE]
> If you make several changes in quick succession to the same subscription line, only the original version is archived.

## Delete subscription lines

You can delete subscription lines if they aren't invoiced and aren't assigned to a contract. If they're assigned to a contract, the contract line can be deleted to remove the assignment. If the subscription lines are already invoiced, they must first be ended by choosing a date in the **Subscription Line End Date** field.

> [!NOTE]
> Contract lines and subscription lines are always identical. If you edit a contract line, the change automatically applies to the subscription lines.

## Related information

[Managing contracts, subscriptions, and subscription lines](contracts-services-mgmt.md)
