---
title: Customer Statement (report)
description: Send customers an overview of outstanding amounts, and also use as a payment reminder about overdue amounts.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_1316_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Customer Statement (report)

The **Customer Statement** report shows a customer statement for a specified period of time.

You can choose to show the overdue amounts in a separate section.

Similar to the **Aged Receivables** report, you can include an aging band. For the aging band, businesses often set **30D**. 30D means 30 day intervals such as 30, 60, and 90 days overdue. The intervals start from the ending date, or **1M+CM**. 1M+CM is the current month in a separate interval and then monthly intervals for the preceding months.

> [!NOTE]
> In the customer list, this report also has a **Scheduled Statements** action. This action doesn't filter to the selected customer. It's the same report, but you use it when you want to send statements to one or more customers. You can filter the report to only show open entries for the customer. To apply the filter when you're setting up the report, in the **Statement Style** field, choose **Open Items**

## Use cases

[!INCLUDE [report-1316-scenario](../includes/report-1316-scenario-include.md)]

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with accounts receivables / collection management.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Customer Statement

### What the report does
The *Customer Statement* report shows a customer statement for a specified time interval. 
You can choose to show the overdue amounts in a separate section. 
You can include an aging band similar to the one used in the **Aged Receivables** report. For the aging band, you typically set *30D*. 30D means 30 day intervals such as 30, 60, 90, and 90 days overdue. The intervals start from the ending date, or *1M+CM*. 1M+CM is the current month in a separate interval and then monthly intervals for the preceding months. 
**Note**: In the customer list, this report also has a **Scheduled Statements** action. This action doesn't filter to the selected customer. It's the same report but used when you want to send statement to all or more customers. You can filter the report so that it shows only entries that are still open for the customer. To apply the filter when you're setting up the report, in the **Statement Style** field, choose **Open Items**


### Use cases
Send customers an overview of outstanding amounts and also as a payment reminder about overdue amounts.

Please include your data sources and URLs

-->

Accounts receivable professionals use the report to:

* Generate customer statements for a specified time period to provide a clear view of all outstanding balances and transactions for the customer.
* Help reconcile customer accounts and ensure that all transactions are accurate and complete.
* Provide customer support by answering questions related to customer statements and resolving discrepancies or errors.

Collections specialists use the report to:

* Follow up with customers on overdue amounts and provide payment reminders based on the aging band used in the report.
* Analyze customer payment history and identify patterns or trends in late payments to proactively address potential issues.
* Prepare collection reports or dashboards for internal or external stakeholders.

Customer service representatives use the report to:

* Provide customers with an overview of their outstanding amounts and transaction history and help them understand the status of their account.
* Help answer customer inquiries related to their account, and provide support in resolving issues or discrepancies.
* Get data to prepare customer account summaries or sales reports for internal or external stakeholders.

## Try the report

Try the report here: [Customer Statement](https://businesscentral.dynamics.com?report=1316)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Accounts receivable report overview](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]