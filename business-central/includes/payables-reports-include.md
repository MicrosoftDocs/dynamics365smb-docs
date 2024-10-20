---
author: brentholtorf
ms.topic: include
ms.date: 07/15/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
---


The following table describes some key reports for accounts payable. The reports are designed to help different roles in the finance departments make informed decisions that optimize their operations.

| To... | Open in [!INCLUDE [prod_short](prod_short.md)] (CTRL+select) | Learn more | ID | 
|-------|------------| ------------|----|

| [!INCLUDE[report-301-scenario](../includes/report-301-scenario-include.md)] | [Vendor - List](https://businesscentral.dynamics.com?report=301) | [About *Vendor - List*](../reports/report-301.md) | 301 |
| [!INCLUDE[report-304-scenario](../includes/report-304-scenario-include.md)] | [Vendor - Detail Trial Balance](https://businesscentral.dynamics.com?report=304) | [About *Vendor - Detail Trial Balance*](../reports/report-304.md) | 304 |
| [!INCLUDE[report-307-scenario](../includes/report-307-scenario-include.md)] | [Vendor - Order Summary](https://businesscentral.dynamics.com?report=307) | [About *Vendor - Order Summary*](../reports/report-307.md) | 307 |
| [!INCLUDE[report-308-scenario](../includes/report-308-scenario-include.md)] | [Vendor - Order Detail](https://businesscentral.dynamics.com?report=308) | [About *Vendor - Order Detail*](../reports/report-308.md) | 308 |
| [!INCLUDE[report-311-scenario](../includes/report-311-scenario-include.md)] | [Vendor - Top 10 List](https://businesscentral.dynamics.com?report=311) | [About *Vendor - Top 10 List*](../reports/report-311.md) | 311 |
| [!INCLUDE[report-313-scenario](../includes/report-313-scenario-include.md)] | [Vendor/Item Purchases](https://businesscentral.dynamics.com?report=313) | [About *Vendor/Item Purchases*](../reports/report-313.md) | 313 |
| [!INCLUDE[report-319-scenario](../includes/report-319-scenario-include.md)] | [Payments on Hold](https://businesscentral.dynamics.com?report=319) | [About *Payments on Hold*](../reports/report-319.md) | 319 |
| [!INCLUDE[report-321-scenario](../includes/report-321-scenario-include.md)] | [Vendor - Balance to Date](https://businesscentral.dynamics.com?report=321) | [About *Vendor - Balance to Date*](../reports/report-321.md) | 321 |
| [!INCLUDE[report-322-scenario](../includes/report-322-scenario-include.md)] | [Aged Accounts Payable](https://businesscentral.dynamics.com?report=322) | [About *Aged Accounts Payable*](../reports/report-322.md) | 322 |
| [!INCLUDE[report-329-scenario](../includes/report-329-scenario-include.md)] | [Vendor - Trial Balance](https://businesscentral.dynamics.com?report=329) | [About *Vendor - Trial Balance*](../reports/report-329.md) | 329 |

<!-- 
|  | [Vendor - List](https://businesscentral.dynamics.com?report=301) | [About *Vendor - List*](../reports/report-301.md) | 301 |

|  | [Vendor - Summary Aging](https://businesscentral.dynamics.com?report=305) | [About *Vendor - Summary Aging*](../reports/report-305.md) | 305 |

|  | [Purchase Statistics](https://businesscentral.dynamics.com?report=312) | [About *Purchase Statistics*](../reports/report-312.md) | 312 |

|  | [Vendor Pre-Payment Journal](https://businesscentral.dynamics.com?report=317) | [About *Vendor Pre-Payment Journal*](../reports/report-317.md) | 317 |
|  | [Payments on Hold](https://businesscentral.dynamics.com?report=319) | [About *Payments on Hold*](../reports/report-319.md) | 319 |

|  | [Payment Practice](https://businesscentral.dynamics.com?page=687) | [About *Payment Practice*](../reports/report-687.md) | page 687 |

-->

## The old way
The following table describes some of the key reports for accounts payable.

| Report | Description | ID | 
|--|--|--|
| [Aged Accounts Payable](https://businesscentral.dynamics.com?report=322) |Shows overdue balances for vendors in time intervals. The overdue amounts can show by due date, posting date, or by document date. You can choose to show the amounts in local currency (LCY) and print details of the overdue documents. The time intervals can have headings with dates or with number of dates overdue, relative to the specified aging by type.<br>This report is the main report for reconciling vendor ledger to G/L. Assuming that you don't post directly to the payables account for the vendor posting group, this report is a specification of the amounts in the general ledger.| 322|
| [Vendor - Balance to Date](https://businesscentral.dynamics.com?report=321) | Shows the vendor balance by the ending date of the specified date range. You can choose to display the vendor balance in your local currency (LCY). Select the **Include Unapplied Entries** field to show entries that were closed by the ending date but were unapplied (opened) at a later date. Select the **Show Entries with Zero Balance** to show vendors with a balance of zero by the ending date of the date filter. The date filter applies to the detailed vendor ledger entries for the entries in the report. If a payment was made after the ending date, and the payment was applied to invoices within the date range, the report includes the invoice. The report includes the invoice because it wasn't closed before the ending date. | 321 |
| [Vendor - Trial Balance](https://businesscentral.dynamics.com?report=329) | Shows the net changes for vendors for the period specified in the date filter, and the net change year-to-date for the corresponding fiscal year. The report is grouped by vendor posting groups and gives a different view of the vendor ledger than the **Aged Accounts Payable** report. **Note**: If you don't set up accounting periods, [!INCLUDE [prod_short](prod_short.md)] doesn't know which fiscal year to use. It shows the year-to-date from the most recent fiscal year, or just the selected period. The date might not be from the beginning of a year.|329 |
| [Vendor - Detail Trial Balance](https://businesscentral.dynamics.com?report=304) | Shows all the vendor ledger entries within the specified date filter. The report shows the vendor's beginning balances relative to the date filter. | 304 |
| [Purchase Statistics](https://businesscentral.dynamics.com?report=312) |[!INCLUDE [reports-purchase-statistics](reports-purchase-statistics.md)]<br>This report can also be used in accounts payable as it's easier to do a quick look-up of posted payments, discounts, and other transactions for a given vendor.| 312 |
| [Vendor - Summary Aging](https://businesscentral.dynamics.com?report=305)| Legacy report for aged accounts payable. We recommend that you use **Aged Accounts Payables** report instead. You can choose a period length and a date to use for an *overdue per* date.|305|
| [Payments on Hold](https://businesscentral.dynamics.com?report=319)| Shows vendor ledger entries where the **On Hold** field isn't blank.| 319 |
| [Vendor Pre-Payment Journal](https://businesscentral.dynamics.com?report=317)|Shows the payment journal with payment discount and tolerance information. The report can be used to check payments before creating payment files and posting the journal. **Note**: The report shows payment discounts incorrectly when multiple credit memos were used in an application. In this case, the payment discounts for the extra credit memos are shown as unapplied amounts.| 317 |
| [Vendor - List](https://businesscentral.dynamics.com?report=301)|Shows basic information for vendors, such as the vendor posting group, discount and payment information, and priority level. The report also shows the vendor's default currency, and the vendor's current balance (in LCY). Use the report, for example, to maintain information about the vendor.|301|
|[Payment Practice](https://businesscentral.dynamics.com?page=687)| Shows how quickly you pay your vendors. You can base the report on a specific period, or by the size of the vendor company in terms of its number of employees. Some countries require this report. To learn more, go to [Payment practices report](../ui-payment-practices.md).| page 687 |