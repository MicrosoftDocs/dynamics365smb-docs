---
title: Notification Email report
description: Generate email content for Business Central notifications, including approval requests, overdue approvals, document details, and action links.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1320
ms.date: 09/18/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/18/2026
ai-usage: ai-assisted
---

# Notification Email (report)

The **Notification Email** report builds the email body that [!INCLUDE [prod_short](../includes/prod_short.md)] sends to a user who is registered for notifications. It uses the **Notification Entry** that triggered the email to determine the recipient and related record. The Word layout can include a greeting, an explanation, a link to the related document, labeled field values, details, and a link to notification settings.

The report has no visible request page fields. The notification engine runs it programmatically for one **Notification Entry** at a time. The entry type, recipient user ID, and related record determine the links, labels, and values in the email.

## Use cases

[!INCLUDE [report-1320-scenario](../includes/report-1320-scenario-include.md)]

Administrators and IT support staff can use the report to:

* Verify that the notification email layout shows the correct document type, number, and action link.
* Confirm that the settings link opens the recipient's notification setup.
* Check the sender and recipient information when troubleshooting notification content.

Approvers and business users can use the report to:

* Receive an email with a direct link to a sales, purchase, or journal document that needs attention.
* Review due dates and change details for approval or overdue notifications.
* Open notification settings from the email to change how future notifications are received.

## Try the report

Try the report here: [Notification Email](https://businesscentral.dynamics.com?report=1320)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Report overview](../reports-available-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
