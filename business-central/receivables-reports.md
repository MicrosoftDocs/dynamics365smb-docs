---
title: Accounts Receivable Reports and Analytics
description: See which reports and analytics are available in the standard version of Business Central so that you can keep track of your accounts receivable.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 07/13/2021
ms.author: edupont

---
# Accounts Receivable Reports and Analytics in Business Central

To help you manage your accounts receivable in [!INCLUDE [prod_short](includes/prod_short.md)], standard reports and analytics are built in. It moves beyond traditional reporting constraints to help you efficiently design various types of reports.  

## Reports

The following table describes some of the key reports in accounts receivable reporting.

| Report | Object ID | Description |
|--|--|--|
| **Aged Accounts Receivables** | 120 | Shows the amount outstanding with customers broken down into time intervals for the overdue time. The report also displays the part of the customers' balance that is not due and can be shown with or without document details for each customer. This report is the main report for reconciling customer ledger to G/L. Assuming you have not allowed direct posting to the accounts used in the customer posting groups' receivables account, this report is a specification of the amounts you find in G/L. |
| **Customer Statement** | 1316 | Generates a customer statement for a specified time interval. It's usually sent to the customers to give them an overview of outstanding amounts and also as a reminder to pay any overdue amounts. You can choose to show the overdue amounts in a separate section. You can include an aging band similar to the one used in the **Aged Receivables** report. For the aging band, you typically set *30D*, which means 30 days intervals such as30, 60, 90, and 90+ days overdue, from the ending date, or *1M+CM*, which will be the current month in a separate interval and then monthly intervals for the preceding months. **Note**: In the customer list, this report also has a separate action, **Scheduled Statements**. This option does not filter to the customer you have selected. It's the same report but used when you want to send statement to all/more customers. |
| **Customer - Balance to Date** | 121 | Shows the open customer ledger entries until the ending date. This report shows similar content as the customer statement but with no indication if the entry is overdue. **Note**: The date filter will be applied to the detailed customer ledger entries. This means that if you have payments later than the ending date that have been applied to invoices in within the date range, the invoices will appear in the report as they have not been closed as per the ending date. |
| **Customer – Trial Balance** | 129 | Shows the net changes for customers for the period specified in the date filter as well as the net change year-to-date for the fiscal year corresponding to the period selected. The report is grouped by customer posting groups and will give a different view of the customer ledger than the **Aged Account Receivables** report. **Note**: If you haven't set up any accounting period, the system will not know what fiscal year to use and will either show year-to-date from the most recent fiscal year defined or just select the period, which may or may not be from beginning of a year.|
| **Customer – Detail Trial Balance** | 104 | Shows all the customer ledger entries within the specified date filter. This report is generally used to check that all entries for a specific customer are accounted for, or other internal checks on customer ledgers. |
| **Customer - Payment Receipt** | 211 | Creates a payment receipt for each customer ledger entry of type **Payment**. If the payment has been applied to invoices, the invoices will be specified; otherwise, it will just state the payment amount as unapplied. This report is used to send to customers that want documentation for receipt of payment.|
| **Reconcile Customer and Vendor Accounts** | 33 |Shows the G/L entries resulting from posting customer and vendor entries split per G/L account and posting groups. This report is used for reconciling the balances on customer and vendor ledgers to general ledger balances. |
| **Customer – Summary Aging Simp.**| 109 |This is a legacy version of an accounts receivables aging report. We recommend you use the **Aged Accounts Receivables** report instead. |
| **Sales Statistics** |112  |[!INCLUDE [reports-sales-statistics](includes/reports-sales-statistics.md)]<br>This report can also be used in accounts receivable as it's easier to do a quick look-up of posted payments, discounts, and sales for a given customer.|
|**Customer List**|101| Shows various kinds of basic information for customers, such as customer posting group, discount group, finance charge and payment information, salesperson, the customer's default currency and credit limit in your local currency (LCY), and the customer's current balance (in LCY). The report can be used, for example, to maintain the information in the Customer table.|

## See also

[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Working with Dimensions](finance-dimensions.md)  
[Managing Fixed Assets](fa-manage.md)  
[Local Functionality Overview](about-localization.md)  
[Accountant Experiences in [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
