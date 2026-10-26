---
title: Defining financial report extensions in Russia
description: Russian localization allows you to extend financial report lines for customized data filtering.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: financial report extension, define extension, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Define a financial report extension

[!INCLUDE[prod_short](../../includes/prod_short.md)] enables you to define an extension for a financial report line. Extensions are useful if you want to filter the data of your general ledger accounts.

## Steps to define a financial report extension

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. Select the financial report for which you want to define an extension.
1. Select **Edit Row Definition**.
1. In the **Row No.** field, select the number of the financial report row for which you want to define an extension.
1. In the **Totaling Type** field, select **Custom**, and then select the table you want to use from the **Extension Source Table** field.
1. In the **Totaling** field, select the extension that defines the filters and calculation for the selected source table.

Based on your selections, the financial report information is filtered from the entry tables, and then new amounts are calculated for the specified financial report line.

## Related information

- [Work with Financial Reports](How-to-Work-with-Account-Schedules.md)  
- [Financial Reports Overview](account-schedules-overview.md)  
- [Define a Financial Report Constant](how-to-define-an-account-schedule-constant.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
