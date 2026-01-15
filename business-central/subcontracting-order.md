---
title: Subcontract manufacturing
description: This article gives an extended overview of the extended functionality of subcontracting, including work center fields and routing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 06/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Order Subcontracting

You additionally have the option to order subcontracting via a released production order.

1. Call up the released production order.

1. Select the line in the production order.

1. Navigate via the ribbon to "Line", "Routing" to open it.

1. The lines list the operations for manufacturing. Mark the line(s) that contain your subcontracting to be ordered.

1. Then click on "Actions", "Functions", "Order Subcontracting" to place an order.

1. Confirm the subsequent dialog window with "Yes".

In the lines of the purchase order, the corresponding information and descriptions have been added according to the "Subcontracting Setup". The subcontractor prices are also transferred. You can send or print the purchase document to your vendor as usual.

## Display Subcontracting Orders

For an already existing subcontracting order, you can view the individual purchase lines starting from the routing and display the associated document.

1. Call up the released production order.

1. Select the corresponding line in the production order.

1. Navigate via the ribbon to "Line", "Routing" to open it.

1. The lines list the operations for manufacturing. Mark the line(s) that contain your subcontracting to be ordered.

1. Navigate via "Related", "Line" and select "Subcontracting Order Lines".

1. Navigate via the ribbon to "Show Document" to open it.

## Print Subcontracting Dispatch List

In addition to the purchase order document and the work papers of the production order, you can print a "Subcontracting Dispatch List" to accompany the unfinished product.
Open the purchase order and select "Actions", "Functions" and "Print Subcontracting Dispatch List" in the ribbon. Make your selection and output options on the request page to print or send the report.

