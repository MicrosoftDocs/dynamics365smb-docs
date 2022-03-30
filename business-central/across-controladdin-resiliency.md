---
title: "Control Add-In Resiliency in Business Central"
description: What to if control add-ins or custom controls are resulting in reduced functionality in Business Central.
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: conceptual

author: SusanneWindfeldPedersen
ms.author: solsen
ms.date: 04/01/2022
---

# Control Add-In Resiliency in Business Central

With [!INCLUDE[prod_short](includes/prod_short.md)] release wave 1, control add-ins that perform slowly are automatically detected and a dialog similar to the following is displayed.

![Busy control add-in.](media/controladdin-resiliency.png "Busy control add-in.")

A slow control add-in typically impacts the performance of the page that you are working on and may reduce your productivity. It has no impact on data and your changes are always saved. If you see a dialog as shown above, you can close it, but it might come back and if the problem persists, you should contact the administrator of the system.

## See Also

<!-- []() link to new topic in dev docs -->