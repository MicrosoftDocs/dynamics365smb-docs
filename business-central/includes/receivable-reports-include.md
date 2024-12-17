---
author: brentholtorf
ms.topic: include
ms.date: 06/12/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---


The following table describes some of the key reports in accounts receivable. The reports are designed to help different roles in finance and collections departments make informed decisions.

<!-- pending merge of finance report PR
| [!INCLUDE [report-33-scenario](../includes/report-33-scenario-include.md)] | [Reconcile Customer and Vendor Accounts](https://businesscentral.dynamics.com?report=33) | [About *Reconcile Customer and Vendor Accounts*](../reports/report-33.md) | 33 | 
-->

| To... | Open in [!INCLUDE [prod_short](prod_short.md)] (CTRL+select) | Learn more | ID | 
|-------|------------| ------------|----|
| [!INCLUDE [report-4402-scenario](../includes/report-4402-scenario-include.md)] | [Aged Accounts Receivable (Excel)](https://businesscentral.dynamics.com?report=4402) | [About *Aged Accounts Receivable (Excel)*](../reports/report-4402.md) | 4402 |
| [!INCLUDE [report-101-scenario](../includes/report-101-scenario-include.md)] | [Customer List](https://businesscentral.dynamics.com?report=101) | [About *Customer List*](../reports/report-101.md) | 101 |
| Check whether all entries for a specific customer are accounted for, or for other internal checks on customer ledgers. | [Customer - Detail Trial Balance](https://businesscentral.dynamics.com?report=104) | [About *Customer - Detail Trial Balance*](../reports/report-104.md) | 104 | 
| [!INCLUDE [report-107-scenario](../includes/report-107-scenario-include.md)] | [Customer - Order Summary](https://businesscentral.dynamics.com?report=107) | [About *Customer - Order Summary*](../reports/report-107.md) | 107 |
| [!INCLUDE [report-108-scenario](../includes/report-108-scenario-include.md)] | [Customer - Order Detail](https://businesscentral.dynamics.com?report=108) | [About *Customer - Order Detail*](../reports/report-108.md) | 108 |
| [!INCLUDE [report-111-scenario](../includes/report-111-scenario-include.md)] | [Customer - Top 10 List](https://businesscentral.dynamics.com?report=111) | [About *Customer - Top 10 List*](../reports/report-111.md) | 111 |
| [!INCLUDE [report-112-scenario](../includes/report-112-scenario-include.md)] | [Sales Statistics](https://businesscentral.dynamics.com?report=112) | [About *Sales Statistics*](../reports/report-112.md) | 112 |
| [!INCLUDE [report-113-scenario](../includes/report-113-scenario-include.md)] | [Customer/Item Sales](https://businesscentral.dynamics.com?report=113) | [About *Customer/Item Sales*](../reports/report-113.md) | 113 |
| [!INCLUDE [report-121-scenario](../includes/report-121-scenario-include.md)]  | [Customer - Balance to Date](https://businesscentral.dynamics.com?report=121) | [About *Customer - Balance to Date*](../reports/report-121.md) | 121 |
| [!INCLUDE [report-129-scenario](../includes/report-129-scenario-include.md)] | [Customer Trial Balance](https://businesscentral.dynamics.com?report=129) | [About *Customer Trial Balance*](../reports/report-129.md) | 129 |
| [!INCLUDE [report-211-scenario](../includes/report-211-scenario-include.md)] | [Customer - Payment Receipt](https://businesscentral.dynamics.com?report=211) | [About *Customer - Payment Receipt*](../reports/report-211.md) | 211 |
| [!INCLUDE [report-1316-scenario](../includes/report-1316-scenario-include.md)] | [Customer Statement](https://businesscentral.dynamics.com?report=1316) | [About *Customer Statement*](../reports/report-1316.md) | 1316 | 
| This is a legacy version of an accounts receivables aging report. We recommend you use the **Aged Accounts Receivables Excel** report instead. | [Customer - Summary Aging Simp.](https://businesscentral.dynamics.com?report=109) | [About *Customer - Summary Aging Simp.*](../reports/report-109.md) | 109 |
| This is a legacy version of an accounts receivables aging report. We recommend you use the **Aged Accounts Receivables Excel** report instead. | [Aged Accounts Receivables (Legacy)](https://businesscentral.dynamics.com?report=120) | [About *Aged Accounts Receivables (Legacy)*](../reports/report-120.md) | 120 |

<!-- Remove after 2025-01-01
## The old way

The following table describes some of the key reports in accounts receivable.

| Report | Description | ID |
|--|--|--|
| [Aged Accounts Receivables](https://businesscentral.dynamics.com?report=120) | Shows the amount outstanding with customers broken down into time intervals for the overdue time. The report also displays the part of the customers' balance that isn't due and can be shown with or without document details for each customer. This report is the main report for reconciling customer ledger to G/L. Assuming you don't allow direct posting to the accounts used in the customer posting groups' receivables account, this report is a specification of the amounts you find in the G/L. | 120 |
| [Customer Statement](https://businesscentral.dynamics.com?report=1316) | Generates a customer statement for a specified time interval. You can send the report to customers to give them an overview of outstanding amounts and also as a payment reminder about overdue amounts. You can choose to show the overdue amounts in a separate section. You can include an aging band similar to the one used in the **Aged Receivables** report. For the aging band, you typically set *30D*. 30D means 30 day intervals such as 30, 60, 90, and 90 days overdue. The intervals start from the ending date, or *1M+CM*. 1M+CM is the current month in a separate interval and then monthly intervals for the preceding months. **Note**: In the customer list, this report also has a **Scheduled Statements** action. This action doesn't filter to the selected customer. It's the same report but used when you want to send statement to all or more customers. You can filter the report so that it shows only entries that are still open for the customer. To apply the filter when you're setting up the report, in the **Statement Style** field, choose **Open Items**. | 1316 |
| [Customer - Balance to Date](https://businesscentral.dynamics.com?report=121) | Shows the open customer ledger entries until the ending date. This report shows similar content as the customer statement but with no indication if the entry is overdue. **Note**: The date filter is applied to the detailed customer ledger entries. You might have payments later than the ending date but are applied to invoices within the date range. Those invoices appear in the report because they weren't closed as per the ending date. | 121 | 
| [Customer - Trial Balance](https://businesscentral.dynamics.com?report=129) | Shows the net changes for customers for the period specified in the date filter. It also shows the net change year-to-date for the fiscal year for the selected period. The report is grouped by customer posting groups and gives a different view of the customer ledger than the **Aged Account Receivables** report. **Note**: If you don't set up accounting periods, [!INCLUDE [prod_short](prod_short.md)] doesn't know which fiscal year to use. It shows either year-to-date from the most recent fiscal year defined or just selects the period. The period might or might not be from the beginning of a year.| 129 |
| [Customer - Detail Trial Balance](https://businesscentral.dynamics.com?report=104) | Shows all the customer ledger entries within the specified date filter. This report is often used to check whether all entries for a specific customer are accounted for, or for other internal checks on customer ledgers. | 104 |
| [Customer - Payment Receipt](https://businesscentral.dynamics.com?report=211) | Creates a payment receipt for each customer ledger entry of type **Payment**. If the payment was applied to invoices, the invoices are specified; otherwise, it just states the payment amount as unapplied. You can send this report to customers who want documentation for receipt of payment.| 211 |
| [Reconcile Customer and Vendor Accounts](https://businesscentral.dynamics.com?report=33) | Shows the G/L entries resulting from posting customer and vendor entries split per G/L account and posting groups. Use this report to reconcile the balances on customer and vendor ledgers to general ledger balances. | 33 |
| [Customer - Summary Aging Simp.](https://businesscentral.dynamics.com?report=109)| This is a legacy version of an accounts receivables aging report. We recommend you use the **Aged Accounts Receivables** report instead. | 109 |
| [Sales Statistics](https://businesscentral.dynamics.com?report=112) | [!INCLUDE [reports-sales-statistics](reports-sales-statistics.md)]<br>This report can also be used in accounts receivable as it's easier to do a quick look-up of posted payments, discounts, and sales for a given customer.| 112 |
| [Customer List](https://businesscentral.dynamics.com?report=101) | Shows various kinds of basic information for customers. For example, the customer posting group, discount group, finance charge and payment information, and so on. Use this report, for example, to maintain information in the Customer table.| 101 |
 -->
