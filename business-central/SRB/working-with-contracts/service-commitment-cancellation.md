---
title: Canceling service commitments
description: You can use cancel service commitments in subscription and recurring billing.
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

# Cancel contract components

All contract lines contain information about their validity and termination dates. Thus, they can be terminated before the expiry or end dates can be changed. If validity and notice periods aren't set, the contract lines are valid indefinitely or can be terminated at any time.

## Cancel a contract Line or service commitment

Use the **Service End Date** field to specify a date on which you stop billing a contract line. The service end date doesn't depend on the dates in the **Cancellation Possible Until** and **Term Until** fields.

If there isn't an agreement with the supplier or customer, the field is blank. If the **Service End Date** is one day prior to the **Next Billing Date**, the contract line is considered terminated. When you run the **Update Service Dates** action, the contract line is marked as closed. To learn more, go to [Customer contracts](customer-contracts.md#customer-contracts).

> [!NOTE]
> If a contract line was billed by mistake because the **Service End Date** was incorrect, you can't just terminate it retroactively. The contract line would be considered billed for a period after the **Service End Date**. Therefore, you must first issue a credit memo. The credit memo resets the **Next Billing Date**, and you can terminate the contract line. This ensures that the process of crediting and ending the contract line is followed.

## Termination dates and deadlines

The **Cancellation Possible Until** date specifies when a contract line can be cancelled in due time. The **Term Until** date specifies the minimum time until which a contract line is, or should be, charged, even if it's terminated.

The **Subsequent Term** specifies the duration of the automatic extension after the initial term. It also determines the rhythm of updating the **Cancellation possible until** and **Term Until** dates. If the field is blank, and either the **Initial Term** or the **Notice Period** are set at the same time, the **Service End Date** is set to the expiration date of the **Initial Term**.

For example, if there's a contract line with a **Next Billing Date** on **01.01.YYYY** that renews annually and has a notice period of three months, the termination dates are as follows:

* **Term Until** is **31.12.YYYY**. The contract line should be charged for the whole year even if it's terminated in due time.
* **Cancellation possible until** is **30.09.YYYY**. The contract line can be terminated in due time up to this date. If the cancellation is received later, the contract line will be billed for another year.

> [!NOTE]
> If a customer cancels a contract line, you can enter the date until which it will be invoiced directly in the contract line. If the cancellation is after the deadline, the regular end can be entered or, as a gesture of goodwill, the deadline can be ignored. This can be especially helpful if the customer wishes to upgrade, for example, and the old contract line should therefore no longer be billed.

If either the **Cancellation possible until** or **Term until** dates change, the other field is recalculated. The **Cancellation period** is always used for this calculation. The next time the dates are updated, the values are used for the calculation.

Use the **Update Service Dates** action to update the notice dates. The action can be called both in the contract and in the service object. For smooth operation, the action should always run in the job queue.

> [!NOTE]
> You can add the update of the end dates to the job queue by using **Update Serv. Comm. Term. Dates** (Codeunit 8058) to run automatically and autonomously. Typically, businesses run the codeunit once a day and outside business hours. The functionality corresponds to calling the action **Update Service Dates** in the contract card.

## Related information

[Service commitments](so-service-commitments.md)  
[Customer contracts](customer-contracts.md)  
