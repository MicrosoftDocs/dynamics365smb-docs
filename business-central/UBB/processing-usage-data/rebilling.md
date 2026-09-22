---
title: Rebilling usage data
description: Business Central automatically rebills usage data that arrives for an already-invoiced period.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8096
ms.date: 08/13/2026
ms.service: dynamics-365-business-central
---
# Rebill usage data

Usage-based billing normally expects new usage data to belong to a period that you didn't invoice yet. But some contracts bill further in advance than usage data reports. For example, an annual subscription often invoices for the entire year up front. If you increase the subscription quantity during the year and don't provide usage data before that point, you report the increase the next time you deliver usage data — for a period that [!INCLUDE [prod_short](../../includes/prod_short.md)] already invoiced.

Normally, a subscription line that you already invoiced for its current period isn't considered for invoicing again until its next billing date - which, for an annual subscription, could be almost a year away. Rebilling ensures this doesn't happen: it recognizes that the new usage data belongs to a period that you already invoiced, and makes the subscription line eligible for invoicing again, so the increase can be billed as a delta for the remainder of the period that you already paid for.

There's no setting to turn rebilling on or off. It's determined automatically: whenever new usage data covers the same billing period (the same charge end date) as a subscription line that you already invoiced, [!INCLUDE [prod_short](../../includes/prod_short.md)] treats it as a rebilling correction rather than as new, regular usage.

## What happens when data is rebilled

When usage data is identified as a rebilling correction, several things happen automatically:

* The corrected quantity is added on top of the subscription's existing quantity, instead of replacing it. This way, a correction adjusts the previously billed amount rather than overwriting it.
* The subscription line's next billing date temporarily moves back to the start of the corrected period, so the correction is picked up the next time you create invoices. Once the correction is invoiced, the next billing date automatically moves forward again to the correct date.
* The correction is calculated using only its own quantity, so it doesn't get blended with a later, regular billing period for the same subscription line.
* A rebilling correction always ends up on its own invoice or credit memo line. It's never combined with a regular charge for the same subscription line, even if both are due in the same billing run. If you cancel a rebilling correction before it's invoiced (for example, by deleting the usage data), the next billing date is automatically restored to where it was before.

## Review rebilling data

To check whether a usage data billing line is a rebilling correction, and whether it's already invoiced, use the **Usage Data Metadata** action. It's available from:

* The **Usage Data Billings** page
* The **Service Commitments** part of a subscription line
* The customer and vendor subscription contract lines

The action opens the **Usage Data Billing Metadata** page, which shows the **Rebilling** and **Invoiced** columns for the charge periods related to the subscription line.

## Related information

[Import data in usage-based billing](imports-processing.md)  
[Extend a contract](extend-contract.md)  
[Usage-based billing customers and subscriptions](../masterdata/customers-subscriptions.md)
