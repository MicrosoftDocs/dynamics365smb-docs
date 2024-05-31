---
author: brentholtorf
ms.topic: include
ms.date: 05/30/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

When you set up users for approval workflows, it's important that the same user isn't both a requestor and an approver in a workflow user group. When a user is both a requestor and an approver, approvals work for them as follows:

* Their requests are always approved automatically.
* If there are multiple approvers, only the approvers with a higher sequence number in the workflow user group can change the status of a request to Approved. Approvers with a lower sequence number can approve requests, however, their approvals won't affect the status of a request.