---
author: edupont04

ms.service: dynamics365-business-central
ms.topic: include
ms.date: 01/20/2021
ms.author: edupont
---
If the **Summarize Gen. Jnl. Lines** check box on the **Electronic Banking Setup** page is selected, [!INCLUDE[prod_short](../../../includes/prod_short.md)] summarizes all payment journal lines for a specific vendor into one general journal line. The general description "Payment %1," where %1 is the vendor number, is used for the summarized journal line description. A separate payment line and a separate general journal line are created to handle:  

- Payment journal lines that contain partial payments, with both the **Partial Payment** and the **Separate Line** fields selected.  

- Payment journal lines that contain a standard format message (passes the MOD97 test), which sets **Standard Format Message** to True in the electronic banking journal.
