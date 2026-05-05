---
title: Set up Expense Agent
description: Learn how to set up Expense Agent to automate expense tracking, processing, and approval workflows in Business Central.
author: jswymer
ms.topic: how-to
ms.date: 01/30/2026
ms.author: jswymer
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up Expense Agent

Expense Agent helps automate expense tracking, processing, and approval workflows in Business Central. After you set it up, employees can submit expenses through email or the Expense Agent web app, and the agent creates expense reports and applies configured rules automatically.

## Choose your setup path

You can configure Expense Agent in two ways:

- **Assisted setup (recommended)**: Use **Configure Expense Agent** for guided onboarding, quick activation, and built-in validation checks as described in this article.
- **Manual setup (advanced)**: Use the **Expense Agent Setup** page to configure settings directly and manage detailed options after initial setup. Learn more in [Access expense management setup](expense-management-setup.md#access-expense-management-setup).

For most organizations, assisted setup is the best way to get started quickly.

## Prerequisites

Before you set up the Expense Agent, make sure the following prerequisites are met:

- The Anthropic model is enabled as a subprocessor in the Microsoft 365 admin center for Microsoft Online Services.  
  Learn more in [Anthropic as a subprocessor for Microsoft Online Services](/microsoft-365/copilot/connect-to-ai-subprocessor).

- Your Business Central account has the **Agent Admin** and **EXPENSE MGMT. ADMIN** permission sets or equivalent permissions.

- A shared mailbox is available for receiving expense submissions from employees.  
  
  The mailbox must be a Microsoft 365 **user mailbox** or **shared mailbox** in your organization. Learn more in [Set up email](../admin-how-setup-email.md).

  > [!IMPORTANT]  
  > You need **Read and manage (Full Access)** permission on the shared mailbox. Learn more in [Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation).

- Number series, payment methods, and posting groups for expenses are configured (optional).  

  You can choose to use default values during setup, and the wizard creates these entities for you. 

- Billing for agent capabilities is set up in Business Central admin center.

  Expense Agent uses Microsoft Copilot Studio messages when activated, which your company is charged for. Learn more in [Manage consumption-based billing](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-consumption-billing).

- The **Expense Agent** capability is enabled on the **Copilot & Agent Capabilities** page.  

  The capability is enabled if the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon appears in the upper-right corner of the role center.  
  Learn more in [Configure Copilot and agent capabilities](../enable-ai.md).

## Configure Expense Agent

Use the **Configure Expense Agent** page to configure and activate the agent.
The page guides you through agent setup. You configure submission channels, access controls, defaults, and policies, then activate the agent to handle registration.

1. In the upper-right corner of the role center, select the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon, and then select **Activate**.
1. Follow the instructions onscreen to configure how the agent behaves.
1. The configuration options are spread across multiple pages. Use the **Go to next card** and **Go to previous card** arrows to move between pages.
1. When you finish configuring the options, turn on the **Active** toggle to activate the agent.  
   If you don't want to activate the agent yet, leave the toggle off. You can return to the page to activate the agent later.
1. Select **Save**.

After configuration, the Expense Agent icon indicates the agent’s status:

- ![Shows the Expense Agent icon](../media/expense-agent-icon-small.png) indicates the agent is ready to process expense submissions.
- ![Shows the Expense Agent icon](../media/expense-agent-configured-icon-small.png) indicates the agent is configured but not currently active.

## What the configuration page does

The **Configure Expense Agent** assisted setup guides you through the choices required to prepare the Expense Agent for use in your Business Central environment.

The assisted setup configures the following areas:

- **Access and submission**: Configure receipt submission channels, mailbox account, and who can configure the agent or work on behalf of users.
- **Accounting defaults**: Apply number series, payment methods, posting groups, and expense categories. Some options become locked after defaults are applied.
- **Management defaults**: Apply default expense locations and management rules. Rule defaults depend on locations.
- **Rules and controls**: Configure policy enforcement such as required receipt number, required merchant name, and anti-corruption attestation visibility.
- **Communication**: Configure open-report reminder behavior and notification frequency.
- **Mileage and per diem**: Configure mileage rate/UOM and per diem calculation options, including partial-day settings.

When you activate the agent, Business Central verifies that all required conditions are met, such as enabled capabilities, correct permissions, and a valid mailbox for email-based expense submission. If any required conditions aren’t met, the assisted setup prompts you to address them before activation completes.

If you deactivate the agent later, Business Central stops processing incoming expenses and disables background processing. Your configuration settings are retained so that you can reactivate the agent without reconfiguring it.

For complete field-by-field reference and advanced options on the **Expense Agent Setup** page, go to [Set up expense management](expense-management-setup.md).

## After you finish setup

After the Expense Agent is active:

- The agent starts monitoring the configured mailbox for incoming expense submissions.
- Expenses submitted by email or through the Expense Agent web app are processed based on your configuration.
- Expense reports are created automatically and routed according to your rules.
- Reminder notifications are sent based on your notification settings, if enabled.
- Managers and approvers can review and approve expense reports in Business Central and the Expense Agent web app.

You can return to the **Configure Expense Agent** page at any time to update settings, apply other defaults, or deactivate and reactivate the agent.

## Troubleshooting

For setup, processing, and user issues, go to [Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md).

## Next steps

- [Upload receipts and create expenses in Expense Agent](expense-agent-upload-receipts.md)  
- [Expense Agent overview](expense-agent-overview.md)  

## Related information

[Set up email](../admin-how-setup-email.md)  
[Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation)  
[Configure Copilot and agent capabilities](../enable-ai.md)  
[Assign permissions to users and groups](../ui-define-granular-permissions.md)  