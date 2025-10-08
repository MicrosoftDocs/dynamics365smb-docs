---
title: Set up the Subscription Billing Power BI app
description: Learn how to set up the Subscription Billing Power BI app
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: how-to
ms.search.keywords:
ms.search.form:
ms.date: 10/08/2025
ms.service: dynamics-365-business-central
---

# Set up the Subscription Billing Power BI app

In a subscription business, managers typically want to know KPIs such as Monthly Recurring Revenue (MRR) or Total Contract Value (TCV), because these metrics provide insight into predictable revenue streams, long-term customer commitments, and the overall health of the business model.

To calculate these KPIs in Business Central, more is needed than just the current state of your subscription contracts and subscription contract lines. Subscriptions can change over time — quantities may increase, terms may be shortened, or subscriptions may end. If you only evaluate the live subscription contract data, you will only see the recurring revenue for the current month, without any historical perspective.

Relying on posted invoices or general ledger entries does not solve this challenge either. While they provide historical figures, they do not include **future-dated subscriptions** that have not yet been invoiced but still need to be reflected in recurring revenue and contract value calculations.

The **Subscription Contract Analysis Entries** table was introduced to create a **monthly snapshot** of all active and planned subscriptions. This ensures you can:

- Track KPIs historically, even when contracts have changed.
- Include future contracts in your revenue calculations.
- Maintain a consistent, comparable basis for both current and historic subscription analysis.

Setting up the analysis entries is therefore a required step to make full use of the subscription billing Power BI app.

The Subscription Contract Analysis Entries table can also be used within Business Central, to easily create an ad-hoc analysis based on your subscription data.

## Create subscription contract analysis entries

You can create subscription contract analysis entries manually:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Create Subscription Contract Analysis**, then choose the related link.
1. The task runs immediately and generates entries for all contract lines that meet the required conditions.
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Subscription Contract Analysis Entries**, then choose the related link. You will see the newly created entries with the current date as Analysis Date.

The task creates one entry per **Subscription Line** for the current month. It only considers subscription lines that meet the following conditions:

- The line is linked with a customer or vendor subscription contract.
- The subscription line is active (meaning the Subscription Line End Date is empty or in the future).

> [!NOTE]  
> Business Central compares the current month with the month in field Analysis Date for each subscription line.  If a subscription contract analysis entry for the same subscription line and the same month already exists, no new entry is created. The existing entry is not updated.

For each entry, Business Central calculates the Monthly Recurring Revenue LCY (MRR) and Monthly Recurring Cost LCY (MRC).

It calculates the MRR for a customer-facing subscription by normalizing the Amount (LCY) to a monthly value based on the date formula in **Billing Base Period**.

**Example calculation of MRR:**

- A subscription line has an amount of 1.200 USD with a billing base period of 1Y (or 12M). This means the amount represents a **yearly** subscription price.
- Business Central calculates the MRR by dividing 1.200 USD by 12 months, resulting in 100 USD per month.

The value for MRC is calculated in a similar way based on the Unit Cost (LCY) and Billing Base Period of the subscription.

MRR and MRC for vendor-facing subscription lines are calculated in the following way:

- MRR is always zero.
- MRC is calculated by normalizing the Amount (LCY) to a monthly value based on the date formula in Billing Base Period.

## Set up job queue for subscription contract analysis entries

Instead of running the task manually each month, you can schedule it in the **Job Queue**. This ensures that your subscription contract analysis entries are always created on time and remain up to date.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Job Queue Entries**, then choose the related link.
1. Choose the **New** action.
1. In the **Object Type to Run** field, choose *Report*.
1. the **Object ID** to Run field, choose *8005*, **Create Subscription Contract Analysis**.
1. In the Earlies Start Date/Time field, enter the first date of the next month.
1. In the **Next Run Date Formula** field, enter *1M*.
1. In the **Starting Time** field, enter *2 AM*.
1. Choose the **Set Status to Ready** action.

Now, the subscription contract analysis entries will be created once per month at the beginning of each month. You can run the job queue entry more than once in the same month. In this case, it will only create entries for **newly added subscription lines** since the last run.

By automating this process, you reduce manual effort and ensure that the Power BI Subscription Billing app always reflects the most accurate and complete set of subscription data.

## Set up job queue for subscription contract termination dates

To calculate KPIs such as **Total Contract Value (TCV)** or **Revenue Forecast**, the Power BI Subscription Billing app relies on the **Term Until** field to determine the remaining subscription period. This date is calculated in Business Central based on the **Subscription Start Date**, **Initial Term**, **Notice Period**, and **Extension Period** defined on the subscription line.

To ensure the **Term Until** field is always accurate, you can schedule the update as a recurring **Job Queue Entry**:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Job Queue Entries**, then choose the related link.
1. Choose the **New** action.
1. In the **Object Type to Run** field, choose *Codeunit*.
1. the **Object ID** to Run field, choose *8058*, **Update Sub. Lines Term. Dates**.
1. In the Earlies Start Date/Time field, enter the first date of the next month.
1. In the **Next Run Date Formula** field, enter *1D*.
1. In the **Starting Time** field, enter *1 AM*.
1. Choose the **Set Status to Ready** action.

Now, the notice dates are updated automatically once a day and outside of business hours.

## Related information

[Cancel planned subscription lines](../working-with-contracts/service-commitment-cancellation.md)  
[Subscription lines](../working-with-contracts/so-service-commitments.md)
[Use Job Queues to Schedule Tasks](../../admin-job-queues-schedule-tasks.md)
