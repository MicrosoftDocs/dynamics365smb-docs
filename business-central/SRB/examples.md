---
title: Examples for subscription billing 
description: Examples provide an overview of use cases available for subscription billing.
author: TobiSIT
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8067, 8084,
ms.date: 05/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Overcoming Subscription Business Model Challenges with Business Central

The Subscription Billing module in Business Central addresses key pain points of the subscription business model by automating billing, supporting flexible contract management, and ensuring compliance with revenue recognition standards. This enables organizations to scale their subscription offerings with confidence.

> [!NOTE]
> Please be aware that *tangible goods* are only supposed to work in conjunction with subscription billing as items with Subscription Option "Sales with Subscription". Non-physical subscriptions are set up as non-inventory items with Subscription Option "Subscription Item".

## Example 1: Digital Newspaper Subscription

**Scenario:**  
A publishing company offers monthly digital newspaper subscriptions. Customers can sign up, pause, or cancel at any time. The company faces challenges such as managing recurring billing cycles, handling mid-cycle cancellations, and ensuring accurate revenue recognition.

**Challenges:**
- Automating monthly invoicing for a large number of subscribers.
- Prorating charges for customers who start or cancel mid-month.
- Tracking and reporting deferred revenue for compliance.

**How Subscription Billing in Business Central Helps:**
- **Automated Recurring Invoicing:** The module automatically generates and sends invoices based on each customer’s billing cycle, reducing manual effort and errors.
- **Flexible Proration:** When a customer subscribes or cancels mid-cycle, Business Central calculates prorated charges or credits, ensuring fair and accurate billing.
- **Revenue Recognition:** Deferred revenue is tracked and recognized according to accounting standards, with clear reporting for auditors and finance teams.

**Setup:**
- **Item:** Non-inventory item with Subscription Option "Subscription Item"
- **Subscription package:** Package marked as "Standard", with Partner "Customer", Invoicing via "Subscription Contract", Calculation Base % "100" and monthly Billing Base Period and Billing Rhythm (1M).
This example is part of the Contoso demo data as item "SB1100".

## Example 2: Gym Membership

**Scenario:**  
A fitness center offers annual and monthly (base) memberships and addons. Members may upgrade, downgrade, or freeze their memberships. The gym needs to manage complex billing scenarios, including partial refunds and contract changes.

**Challenges:**
- Managing upgrades, downgrades, and freezes without manual intervention.
- Handling partial refunds or credits for unused membership periods.
- Ensuring accurate contract billing and compliance with revenue recognition rules.

**How Subscription Billing in Business Central Helps:**
- **Contract Flexibility:** Membership changes (upgrades, downgrades, freezes) are reflected in the contract, and billing is automatically adjusted.
- **Partial Credits and Refunds:** The system supports negative quantities and partial credits, so refunds for unused periods are processed seamlessly.
- **Compliance and Reporting:** All changes are logged, and revenue is recognized in line with accounting policies, supporting transparency and compliance.

**Setup:**
- **Items:** Non-inventory items, as required, for membership and addons with Subscription Option "Subscription Item"
- **Subscription packages:** Packages, as required, for monthly and annual memberships and for addons; each with Partner "Customer", Invoicing via "Subscription Contract", Calculation Base % "100" and respective Billing Base Period and Billing Rhythm (1M or 12M).

## Related information

[Subscription items](masterdata/items.md)
[Subscription packages](masterdata/service-commitments.md)
[Recurring billing](recurring-billing.md)  
