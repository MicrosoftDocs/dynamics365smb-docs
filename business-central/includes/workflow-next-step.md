---
author: brentholtorf
ms.topic: include
ms.date: 03/27/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

> [!IMPORTANT]
> When you change the when event for a workflow step, the next step for the then responses also change. The next steps for then responses sometimes refer to other then responses for when events. After you change a when event, verify that the next steps for its then events are correct.  
>
> For example, the **Vendor Approval Workflow** workflow template has a **Approval of a vendor is requested** primary workflow when event that has a **Send approval request for the record and create a notification** then response. If you change the primary **Approval of a vendor is requested** when event to **A vendor record is changed**, the then response is cleared.
> There are several other indented when events that also have then responses with next steps. The **An approval request is delegated** and **An approval request is approved** (with the **On Condition** of **Pending Approvals >0**) when events have a then response with a next step that refers to the **Send approval request for the record and create a notification** then response of the **Approval of a vendor is requested** when event. Because that then response is no longer available, the when events won't work as expected.
>
> You'll need to specify the next steps for the then responses for when events that referred to the changed when event.