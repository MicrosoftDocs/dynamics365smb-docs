---
title: Defining financial report extensions in Russia
description: Russian enhancements include extending financial report lines.
author: DianaMalina
ms.topic: how-to
ms.search.keywords:
ms.date: 11/13/2023
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Define a financial report extension

[!INCLUDE[prod_short](../../includes/prod_short.md)] enables you to define an extension for a financial report line. Extensions are useful if you want to filter the data of your general ledger accounts.

## To define a financial report extension

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Report**, then choose the related link.
2. Select the financial report for which you want to define an extension.
3. Select **Edit Financial Report**.
4. In the **Row No.** field, select the number of the financial report row for which you want to define an extension.
5. In the **Totaling Type** field, select **Custom**, and then select the table you want to use from the **Extension Source Table** field.

Based on your selections, the financial report information is filtered from the entry tables, and then new amounts are calculated for the specified financial report line.

## Related information

[Work with Financial Reports](How-to-Work-with-Account-Schedules.md)  
[Financial Reports Overview](account-schedules-overview.md)  
[Define a Financial Report Constant](How-to-Define-an-Account-Schedule-Constant.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
