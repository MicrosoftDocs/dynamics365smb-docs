---
title: "Control add-in resiliency in Business Central"
description: What to if control add-ins or custom controls are resulting in reduced functionality in Business Central.
ms.topic: article
author: brentholtorf
ms.author: bholtorf
ms.date: 12/12/2023
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Control add-in resiliency in Business Central

From update 20.0 of [!INCLUDE[prod_short](includes/prod_short.md)], control add-ins that perform slowly are automatically detected and a dialog similar to the following is displayed.

![Busy control add-in.](media/controladdin-resiliency.png "Busy control add-in.")

An unhealthy control add-in might affect your Business Central experience and cause the page you're working on to start slowly. It has no impact on data and your changes are always saved. If you see the warning as shown above, you can hide it, but it might come back and if the problem persists, you should contact your administrator.

## Related information
[Control add-in performance best practices](/dynamics365/business-central/dev-itpro/developer/devenv-control-addin-bestpractices)  
