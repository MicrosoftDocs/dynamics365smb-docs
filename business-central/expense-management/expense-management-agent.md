---
title: How the Expense Agent Processes Emails
description: Learn how Expense Agent monitors a mailbox, creates expenses from emails, and sends reminders about open expense reports.
author: jswymer
ms.topic: concept-article
ms.date: 11/04/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6996,
ai-usage: ai-assisted
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot

---

# How Expense Agent processes emails

[!INCLUDE [online_only](../includes/online_only.md)]

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Expense Agent in [!INCLUDE[prod_short](../includes/prod_short.md)] automates parts of the expense management process by monitoring an email mailbox. It can detect expense-related emails, create expenses automatically, and send reminders about open expense reports.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What the agent does

Expense Agent runs on a schedule and performs three tasks:

1. **Reads incoming emails** to retrieve new messages from the configured mailbox and find expense-related content such as receipt confirmations and credit card statements.
2. **Sends outgoing emails** for queued messages, such as confirmations and responses to expense users.
3. **Sends reminder notifications**. If open report notifications are enabled, the agent sends reminders to expense users who have open expense reports.

## How email processing works

When the agent finds a relevant email, it extracts key details like the date, amount, merchant, and category. It then creates an expense record for the corresponding expense user.

The agent also assigns expenses to a suitable draft expense report or creates a new report. Matching considers expense dates and, for travel-linked reports, the expected trip dates. If outgoing email is configured, the agent sends a confirmation email back to the user. The confirmation includes a summary of the created expenses, the total amount, and a link to review the expense report directly in the Expense Agent web app.

> [!NOTE]
> The agent suggests expense details based on the email content. Always review automatically created expenses to make sure the information is accurate before submitting the report.

## Prerequisites

Before the agent can process emails, an administrator must:

- Use **Configure Expense Agent** to activate the agent.
- Under **Access and submission**, turn on **Enable sending email with receipts** and configure the **Account** that the agent monitors. Incoming receipt processing is separate from outgoing email.
- Activate the **Expense Agent** capability on the **Copilot & Agent Capabilities** page.
- Accept the privacy notice.
- Add users to the **Agent Access Control** list to specify who the agent can work on behalf of.

## Reminder notifications

When enabled, the agent sends periodic reminders to expense users who have expense reports in **Open** status. The reminders help ensure that people submit reports on time.

Administrators configure reminders in **Communication** on the **Configure Expense Agent** page. Turn on outgoing email, select an **Account**, and enable **Notify users about unsubmitted reports**. Then configure the reminder frequency and schedule. The agent doesn't use the receipt mailbox as a fallback sender. Learn more in [Configure notification settings](expense-management-setup.md#configure-notification-settings).

## Security and access

The agent works within the permissions assigned to it. Administrators control which users the agent can act for, and which users can configure the agent. These settings are available on the **Agent Access Control** FastTab of the **Expense Management Setup** page.

The agent only sends emails to users who are registered as expense users.

## Related information

[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
