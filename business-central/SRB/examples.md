---
title: Examples for subscription billing 
description: The examples in this article describe some typical use cases that subscription billing features support.
author: bholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8067, 8084,
ms.date: 03/04/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Overcome subscription business model challenges

Subscription billing features address the key challenges of the subscription business model by automating billing, supporting flexible contract management, and ensuring compliance with revenue recognition standards. These features enable you to scale your subscription offerings with confidence.

> [!NOTE]
> *Tangible goods* are only supposed to work with subscription billing as items with a **Subscription Option** of **Sales with Subscription**. Nonphysical subscriptions are set up as noninventory items with a **Subscription Option** of **Subscription Item**.

## Example 1: Online newspaper subscription

**Scenario:**  

A publishing company offers monthly digital newspaper subscriptions. Customers can sign up, pause, or cancel their subscriptions at any time. The company faces challenges such as managing recurring billing cycles, handling mid-cycle cancellations, and ensuring accurate revenue recognition.

**Challenges:**

- Automating monthly invoicing for a large number of subscribers.
- Prorating charges for customers who start or cancel mid-month.
- Tracking and reporting deferred revenue for compliance.

**How subscription billing helps:**

Subscription billing in Business Central helps by automating recurring invoicing so invoices are generated and sent based on each customer’s billing cycle, reducing manual effort and errors. It also supports flexible proration, so when a customer subscribes or cancels mid-cycle, charges or credits are calculated fairly and accurately. In addition, deferred revenue is tracked and recognized according to accounting standards, with clear reporting for auditors and finance teams.

**Setup:**

- **Item:** Noninventory item with a **Subscription Option** of **Subscription Item**.
- **Subscription package:** Package marked as **Standard**, with a **Partner** set to **Customer**, invoicing via a **Subscription Contract**, a **Calculation Base % of **100**, a monthly **Billing Base Period**, and a **Billing Rhythm** of **(1M)**.

This example is part of the Contoso demo data as item "SB1100".

## Example 2: Gym membership

**Scenario:**  

A fitness center offers annual and monthly (base) memberships and add-ons. Members can upgrade, downgrade, or freeze their memberships. The gym needs to manage complex billing scenarios, including partial refunds and contract changes.

**Challenges:**

- Managing upgrades, downgrades, and freezes without manual intervention.
- Handling partial refunds or credits for unused membership periods.
- Ensuring accurate contract billing and compliance with revenue recognition rules.

**How subscription billing helps:**

Subscription billing provides contract flexibility by reflecting membership changes such as upgrades, downgrades, and freezes directly in the contract and automatically adjusting billing. It also supports partial credits and refunds through negative quantities and partial credits, so unused periods can be refunded seamlessly. In addition, all changes are logged, and revenue is recognized in line with accounting policies to support transparency and compliance.

**Setup:**

- **Items:** Noninventory items, as required, for membership and add-ons with a **Subscription Option** of **Subscription Item**.
- **Subscription packages:** Packages, as required, for monthly and annual memberships and for addons; each with Partner "Customer", Invoicing via "Subscription Contract", Calculation Base % "100" and respective Billing Base Period and Billing Rhythm (1M or 12M).

## Related information

[Subscription items](masterdata/items.md)  
[Subscription packages](masterdata/service-commitments.md)  
[Recurring billing](recurring-billing.md)  
