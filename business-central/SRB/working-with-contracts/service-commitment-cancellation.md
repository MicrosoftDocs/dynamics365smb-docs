---
title: Canceling service commitments
description: You can use cancel service commitments in subscription and recurring billing.
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

# Termination of contract components

All contract lines contain information about their validity and termination dates. Thus, they can be terminated before the expiry or termination dates can be changed. If validity and notice periods are not set, the contract lines are valid indefinitely or can be terminated at any time.


## Cancellation of a Contract Line / or Service Commitment
In the field **Service End Date** a date can be maintained, from which the contract line should no longer be charged. After this date, the contract line will automatically no longer be considered for billing. The Service End Date can be independent of **Cancellation Possible Until** and **Term Until**.

If there is no agreement with the supplier or customer, the field will be left blank. If the **Service End Date** is one day prior to the **Next Billing Date**, the contract line is considered terminated. When the action **Update Service Dates** is executed, the contract line is marked as [closed](/docs/srb/working-with-contracts/customer-contracts.md).

:::info
If a **contract line** has been billed by mistake because the **Service End Date** was not maintained, it cannot simply be terminated retroactively. Otherwise, the contract line would be considered billed for a period after the **Service End Date**.
Therefore, a credit memo must first be issued. The credit memo resets the **Next Billing Date**. The contract line can then be terminated. This ensures that the process of crediting and ending the contract line is followed.
:::


## Termination dates and deadlines
The **Cancellation Possible Until** date provides information on when a contract line can be cancelled in due time. The **Term Until** date provides information about the minimum time until which a contract line will be charged or should be charged, even if it has been terminated.

The **Subsequent Term** specifies the duration of the automatic extension after the Initial Term. In addition, it determines the rhythm of updating **Cancellation possible until** and **Term until**. If the field is blank and either the **Initial Term** or the **Notice Period** is set at the same time, the **Service End Date** is automatically set to the expiration date of the **Initial Term**.

For example, if there is a contract line with **Next Billing Date** 01.01.YYYY that renews annually and has a notice period of 3 months, the termination dates will be as follows:
* **Term until** is 31.12.YYYY. The contract line should be charged for the whole year even if it is terminated in due time.
* **Cancellation possible until** is 30.09.YYYY. The contract line can be terminated in due time up to this date. If the cancellation is received later, the contract line will be billed for another year.

:::tip Tip
If a contract line is cancelled by the customer, the date until which it will be invoiced can be entered directly in the contract line. If the cancellation takes place after the deadline, the regular end can be entered or as a gesture of goodwill the deadline can be ignored. This can be especially helpful if the customer wishes to upgrade, for example, and the old contract line should therefore no longer be billed.
:::

If **Cancellation possible until** or **Term until** is changed, the other field will be recalculated. The **Cancellation period** is always used for this calculation. The next time the dates are updated, the entered values will be used for the calculation. 

The **Update Service Dates** action can be used to update the notice dates. The function can be called both in the contract and in the Service Object. For smooth operation, the function should always run in the Job Queue.

:::info Update of termination dates
The update of the termination dates can be added to the Job Queue via **DYCEUpdateServCommTermDates** (Codeunit 70920758) to run automatically and autonomously. It is sufficient to run the codeunit once a day outside business hours. The functionality corresponds to calling the action **Update Service Dates** in the contract card.
:::