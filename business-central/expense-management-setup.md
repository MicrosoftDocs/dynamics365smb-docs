---
title: Set Up Expense Management in Business Central
description: Learn how to configure expense management settings including the expense agent, mailbox, number series, posting groups, and approval workflows.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Set up expense management

Before employees can record expenses and submit reports, an administrator must configure the expense management module in [!INCLUDE[prod_short](includes/prod_short.md)]. This article walks you through the key setup tasks.

## To open expense agent setup

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Agent Setup**, and then choose the related link.

The **Expense Agent Setup** page contains all configuration settings organized into the following groups.

## To enable the expense agent

The expense agent monitors an email mailbox and can automatically create expenses from incoming emails, such as receipt confirmations and credit card statements.

1. On the **Expense Agent Setup** page, turn on the **Enable Agent** toggle.
2. In the **Mailbox Account** field, choose the email account that the agent should monitor. You need permission to the mailbox to activate the agent.
3. Set the **Exchange Rate for Expenses** field to specify how exchange rates are applied to expenses in foreign currencies.

> [!NOTE]
> Before you can enable the agent, you must accept the privacy notice and make sure the **Expense Agent** capability is active on the **Copilot & Agent Capabilities** page.

## To configure rules and controls

Use the **Rule & Controls** section to define expense policies.

1. Turn on **Use Rules** to enforce expense rules during submission.
2. Set **Do Not Allow Expenses Older Than** to restrict how far back expenses can be dated.
3. Choose what happens when an expense is older than allowed in the **If Exp. Is Older Than Allowed** field.
4. Turn on **Check Category/Subcategory Usage** to require that expenses use valid category and subcategory combinations.
5. Turn on **Enable Anti-Corruption Attestation** if your organization requires an attestation statement on expense reports.
6. Turn on **Enable Approval Workflow** to require manager approval before reports can be posted.

## To set up number series

In the **Number Series** section, assign number series for the following:

- **Expense User Nos.** — Automatic numbering for expense users.
- **Expense Reports Nos.** — Automatic numbering for expense reports.
- **Posted Expense Reports Nos.** — Automatic numbering for posted reports.
- **Expense Nos.** — Automatic numbering for individual expenses.

## To set up expense posting groups

Expense posting groups map expense transactions to general ledger accounts.

1. On the **Expense Agent Setup** page, choose the **Expense Posting Groups** action.
2. Create posting groups and assign the appropriate general ledger accounts for each group.

## To configure notification settings

When the agent is enabled, you can configure reminders about open expense reports.

1. In the **Communication** section, turn on **Enable Open Report Notification**.
2. Choose a notification frequency: **Weekly**, **Monthly**, or **Custom**.
3. For weekly notifications, choose the day of the week in the **Notification Day of Week** field.
4. For monthly notifications, specify the day in **Notification Day in a Month**.
5. For custom schedules, enter a date formula in the **Custom Notification Formula** field.

## To manage agent access control

The **Agent Access Control** section at the bottom of the setup page lets you specify which users can configure the agent and which users the agent can work on behalf of.

## To apply default settings

If you're setting up expense management for the first time, you can use default settings as a starting point.

1. On the **Expense Agent Setup** page, choose the **Apply default settings** action.

This action creates default categories, rules, and other master data. You can then adjust the defaults to match your organization's needs.

## Related information

[Set up expense categories and rules](expense-management-categories-rules.md)  
[Set up expense users and teams](expense-management-users-teams.md)  
[Set up per diem and mileage allowances](expense-management-per-diem-mileage.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
