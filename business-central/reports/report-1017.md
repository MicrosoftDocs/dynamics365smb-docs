---
title: Job Task Quote report
description: Generate a printable quote for a project task that lists planning lines, quantities, prices, and discounts along with the total project value.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1017
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Job Task Quote (report)

The **Job Task Quote** report produces a quote for a single project task. It shows the company and bill-to addresses, project number and description, and a breakdown of the project planning lines associated with the task. The report excludes budget lines and totals only lines that represent billable quantities. It shows the calculated total project value at the end of the document.

You can filter the report by **Job No.** and **Job Task No.** to select the project and task that the quote covers. You can also filter the project planning lines by **Job Task No.** to narrow down the lines included in the quote.

## Use cases

[!INCLUDE [report-1017-scenario](../includes/report-1017-scenario-include.md)]

Project managers can use the report to:

* Produce a formal quote for a specific project task before committing resources to it.
* Review planned quantities, unit prices, and line discounts for a task in a single printable document.
* Confirm the total project value calculated from billable planning lines before sharing it with a customer.

Sales representatives can use the report to:

* Send customers a quote that shows bill-to details and task-level pricing.
* Filter the report to a single project and task to generate a targeted quote for a customer inquiry.
* Use the printed quote as a basis for negotiating pricing or discounts with the customer before work starts.

## Try the report

Try the report here: [Job Task Quote](https://businesscentral.dynamics.com?report=1017)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Project reports](../project-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
