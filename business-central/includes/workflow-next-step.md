---
author: brentholtorf
ms.topic: include
ms.date: 03/27/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

> [!IMPORTANT]
> When you change the when event for a workflow step, the then responses also changes. Sometimes, then responses of other when events refer to these then responses as the next step in the workflow. After you change a when event, verify that the next steps for its then events are correct.  
>
> For example, the **Vendor Approval Workflow** workflow template has a primary when event **Approval of a vendor is requested**. This when event has a **Send approval request for the record and create a notification** then response, which other then responses reference. If you change the primary **Approval of a vendor is requested** when event to, for example, **A vendor record is changed**, the then response is cleared along with the references.
>
> The then responses for the **An approval request is delegated** and **An approval request is approved** (with the **On Condition** of **Pending Approvals >0**) when events are examples of where changing a primary when event can cause problems. Their then responses have a next step that refers to the **Send approval request for the record and create a notification** then response of the **Approval of a vendor is requested** when event. Because the then response for the **Approval of a vendor is requested** when event is no longer available, the indented when events won't work as expected.
>
> You'll need to specify the next steps for the then responses for when events that referred to the changed when event.