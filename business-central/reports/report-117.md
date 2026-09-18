---
title: Reminder report
description: Print or email issued reminders that show overdue customer invoices, interest, fees, and VAT so customers can settle outstanding balances.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_117_Primary
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Reminder (report)

The **Reminder** report prints or emails an issued reminder to a customer. It lists the overdue documents, remaining amounts, interest, additional fees, and VAT that make up the total amount due. The report uses data from the **Issued Reminder Header** and **Issued Reminder Line** tables. It can render an RDLC layout for printing or a Word-based email body layout. The output includes company and customer addresses, bank details, and VAT specifications.

You can filter the report by reminder number using the **No.** filter on the **Issued Reminder Header**. You can show internal information, log the reminder as a customer interaction, show amounts that aren't yet due, and include multiple interest rate details in the output.

## Use cases

[!INCLUDE [report-117-scenario](../includes/report-117-scenario-include.md)]

Accounts receivable clerks can use the report to:

* Print or email a formal reminder to a customer for overdue invoices after the reminder has been issued.
* Include interest amounts and additional fees calculated on the overdue balance so that the customer can review the full amount due.
* Turn on **Log Interaction** to record the reminder as a customer interaction for follow-up tracking.
* Turn on **Show Not Due Amounts** to give the customer visibility into upcoming amounts alongside overdue amounts.

Controllers and finance teams can use the report to:

* Review the VAT amount specification to confirm that VAT bases, percentages, and amounts are correctly broken out by VAT identifier.
* Use **Show Internal Information** to check dimension values and multiple interest rate details before sending a reminder externally.
* Verify the local currency VAT specification and exchange rate details when reminders are issued in a foreign currency.

## Try the report

Try the report here: [Reminder](https://businesscentral.dynamics.com?report=117)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Accounts receivable analytics](../receivables-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
