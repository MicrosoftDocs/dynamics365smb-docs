---
title: How the Expense Agent Processes Emails
description: Learn how the expense agent in Business Central monitors a mailbox, creates expenses from emails, and sends reminders about open expense reports.
author: brentholtorf
ms.topic: conceptual
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6996
---

# How the expense agent processes emails

The expense agent in [!INCLUDE[prod_short](includes/prod_short.md)] automates parts of the expense management process by monitoring an email mailbox. It can detect expense-related emails, create expenses automatically, and send reminders about open expense reports.

## What the agent does

The expense agent runs on a schedule and performs three tasks:

1. **Reads incoming emails** — The agent retrieves new messages from the configured mailbox and looks for expense-related content such as receipt confirmations and credit card statements.
2. **Sends outgoing emails** — The agent processes queued messages, such as confirmations and responses to expense users.
3. **Sends reminder notifications** — If open report notifications are enabled, the agent sends reminders to expense users who have open expense reports.

## How email processing works

When the agent finds a relevant email, it extracts key details like the date, amount, merchant, and category. It then creates an expense record for the corresponding expense user.

The agent also groups expenses into expense reports automatically based on the configured reporting period. After processing, the agent sends a confirmation email back to the user. The confirmation includes a summary of the created expenses, the total amount, and a link to review the expense report directly in the Expense Agent web app.

> [!NOTE]
> The agent suggests expense details based on the email content. Always review automatically created expenses to make sure the information is accurate before submitting the report.

## Prerequisites

Before the agent can process emails, an administrator must:

- Enable the agent on the **Expense Agent Setup** page.
- Configure a mailbox account that the agent monitors.
- Activate the **Expense Agent** capability on the **Copilot & Agent Capabilities** page.
- Accept the privacy notice.
- Add users to the **Agent Access Control** list to specify who the agent can work on behalf of.

## Reminder notifications

When enabled, the agent sends periodic reminders to expense users who have expense reports in **Open** status. This helps ensure that reports are submitted on time.

Administrators configure the reminder frequency (weekly, monthly, or custom) and schedule on the **Expense Agent Setup** page. For more information, see [Set up expense management](expense-management-setup.md).

## Security and access

The agent works within the permissions assigned to it. Administrators control:

- **Which users the agent can act for** — Defined in the **Agent Access Control** section of the setup page.
- **Which users can configure the agent** — Also defined in the access control list.

The agent only sends emails to users who are registered as expense users.

## Related information

[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
