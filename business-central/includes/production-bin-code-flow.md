---
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: include
ms.date: 05/14/2026
ms.service: dynamics-365-business-central
---

When you refresh a production order, the system determines the **Bin Code** for each component line using the following logic:

1. **Find the routing line.** If the component has a **Routing Link Code**, the system looks for a routing operation with that code. If no match is found, or the component doesn't have a routing link code, the system uses the first operation in the routing (the operation with no previous operation). If no routing lines exist, the system skips to step 3.

2. **Select the bin based on flushing method.** The routing line carries three bin codes from the work center or machine center. The system picks one based on the component's flushing method:

   | Flushing method | Bin code used |
   |---|---|
   | Manual, Forward, Backward | Open Shop Floor Bin Code |
   | Pick + Forward, Pick + Backward, Pick + Manual | To-Production Bin Code |

   The routing line only has these bin codes when the **Location Code** on the work center or machine center matches the production order line's location. If the locations don't match, the routing line bins are empty and the system uses the fallback.

3. **Fallback.** If the routing line doesn't provide a bin code, the system checks the **Location Card** for the corresponding bin code fields (the same flushing-method logic applies). If the location doesn't provide a bin code either, the system uses the default bin for the item at that location.

> [!NOTE]
> The **From-Production Bin Code** follows a different path. At the last routing operation, the From-Production bin flows to the production order line's **Bin Code** field, which represents where finished output is placed. To learn more about setting up these bins, go to [Set up work centers and machine centers](../production-how-to-set-up-work-and-machine-centers.md#to-set-up-a-work-center).
