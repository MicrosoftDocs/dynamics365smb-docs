---
title: Manage known senders for Payables Agent
description: Manage per-sender email review policies for the Payables Agent to automatically approve or reject emails from trusted or unwanted vendors.
ms.date: 07/28/2026
ms.update-cycle: 180-days
ms.topic: how-to
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
ms.search.form: 3313_Primary,3304
ai-usage: ai-assisted
---
# Manage known senders for Payables Agent

The known senders feature helps you manage how Payables Agent handles emails from specific senders to improve invoice processing efficiency. To use sender-specific policies, configure Payables Agent to use the **Manage per sender (recommended)** email review option. You can then automatically approve emails from trusted vendors, require review for other senders, or reject emails from unwanted senders.

## Overview of known senders

Payables Agent automatically builds the known senders list as it processes vendor invoices. When the agent creates a purchase invoice draft from a new sender, it adds the sender's email address to the list before finalizing the invoice. Each sender has a policy that determines how the agent handles future emails from that sender.

You can also add senders manually before the agent processes their invoices. This option is useful when you want to assign a policy to a vendor in advance.

## Understanding sender review policies

Assign one of the following policies to a sender to control how the agent processes emails:

- **Ask:** The agent requests human review before processing emails from this sender.
- **Approve:** The agent automatically processes emails from this sender without requesting review.
- **Reject:** The agent skips emails from this sender and doesn't create a task.

How these policies work and how the agent assigns them depends on your email review setting as described in the following section.

### When are sender policies used?

The known senders list is always maintained regardless of your email review setting. Sender review policies are applied only when both of the following conditions are met:

- The email review setting is **Manage per sender**
- No monitored subfolder is configured

If the email review setting is **Always** or **Never**, sender policies aren't used because the email review setting determines how all emails are processed.

If a monitored subfolder is configured, Payables Agent processes only emails in that folder. Sender policies and the email review setting aren't used for those emails because they're processed automatically.

If you later switch back to **Manage per sender** and remove the monitored subfolder, any configured sender policies are available immediately.

A message appears when a configuration change affects whether sender policies are used, allowing you to confirm the change or adjust your settings.

## Decide how known senders are reviewed

The known senders list and per-sender review policies work differently depending on the agent's email review setting. The email review setting determines whether sender review policies are used and which policy is assigned to new senders.

- **Manage per sender (recommended):** The first time an email is received from an unknown sender, the agent requires review of the incoming email task. When you approve the task, the agent assigns an **Approve** policy to the sender. Future emails from that sender are processed automatically without requiring review. Emails skip review when the sender is set to **Approve**. Emails from senders set to **Reject** are skipped entirely without creating a task.
- **Never:** The agent ignores sender review policies. All emails are processed without review. New senders are still added to the known senders list and assigned the **Ask** review policy, but policies aren't used while this setting is active.
- **Always:** The agent ignores sender review policies. All emails require review regardless of sender review policy. New senders are assigned the **Ask** policy.

## Access the known senders list

1. In the navigation bar at the upper right of the role center, select ![Shows the Payables Agent icon after configured](media/payables-agent-activated-icon.png) **Payables Agent** > ![Shows the configuration icon for Payables Agent](media/soa-configure-icon.png) **Configure Payables Agent**.
1. On the **Configure Payables Agent** page, go to the **Email review** section.
1. Select **Manage known senders**.

The **Payables Agent Known Senders** page opens, showing all known senders and their assigned policies.

## Add a sender manually

You can add a sender to the list before the agent processes an invoice from them. This step allows you to preconfigure their review policy:

1. On the **Payables Agent Known Senders** page, select **New**.
1. In the **Email** field, enter the email address of the sender you want to add.
1. In the **Policy** column, select one of the three available policies: **Ask**, **Approve**, or **Reject**. See "Understanding sender review policies" earlier in this article for details.
1. Select **Close** when done.

## Set per-sender review policies

On the **Payables Agent Known Senders** page, you can manage review policies for each sender:

1. Find the sender you want to manage in the list.
1. In the **Policy** column, select one of the three available policies: **Ask**, **Approve**, or **Reject**. See "Understanding sender review policies" earlier in this article for details.
1. Select **Update** to apply the changes.

## Delete a sender

Remove a sender from the known senders list if you no longer want to maintain a specific policy for them or if the sender becomes irrelevant.

1. On the **Payables Agent Known Senders** page, find the sender you want to remove.
1. Select the sender.
1. Select **Delete** to remove them from the list.

After you delete a sender, if the agent later processes an invoice from that email address again, it treats the sender as a new sender and adds them back to the list with the default policy for your current email review setting.

## Best practices for managing senders

- **Approve trusted vendors:** Set policy to **Approve** for regular vendors whose invoices are consistently accurate.
- **Monitor the "Ask" policy:** Regularly review how many emails require manual review. If a trusted vendor consistently requires review, consider changing their policy to **Approve**.
- **Reject known unwanted senders:** Set policy to **Reject** for senders you don't want to receive invoices (such as spam or test email accounts) from.

## Related information

[Set up Payables Agent](payables-agent-setup.md)  
[Payables Agent overview](payables-agent.md)  
