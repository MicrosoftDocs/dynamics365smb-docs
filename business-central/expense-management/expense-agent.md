---
title: Expense Agent Overview
description: Learn how the Expense Agent automates expense processing, including receipt intake, data extraction, categorization, and expense report creation.
ms.date: 04/20/2026
ms.update-cycle: 180-days
ms.topic: overview
author: altotovi
ms.author: altotovi
ms.reviewer: altotovi
ms.collection:
  - bap-ai-copilot
ms.search.form: 4400, 4410
ai-usage: ai-assisted
---

# Expense Agent overview

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The **Expense Agent** is an AI-powered agent that automates expense processing in Business Central. It handles receipt intake, data extraction, categorization, itemization, and expense line creation, then groups expenses into expense reports for review and approval.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

Employees submit expenses through a dedicated web app at [https://app.expenses.dynamics.com/](https://app.expenses.dynamics.com/) or by forwarding receipts to a shared mailbox. Neither method requires a Business Central license. The agent processes the submitted receipts, extracts the relevant data, and creates expense records in Business Central. Users review the results and submit expense reports for approval through the web app.

All financial data, audit trails, and posting logic are processed within Business Central, so existing rules, permissions, and workflows continue to apply.

> [!NOTE]
> [!INCLUDE[copilot-language-support-en-only](../includes/copilot-language-support-en-only.md)]

## What the Expense Agent does

The Expense Agent manages the entire expense lifecycle, from capturing receipts to approving and posting expense reports. The following sections outline each step in the process.  

### Receipt intake

The agent accepts receipts from two channels:

- The **Expense Agent** web app at [https://app.expenses.dynamics.com/](https://app.expenses.dynamics.com/)
- A monitored **shared mailbox**

Supported file formats include JPEG, PNG, and PDF. The agent can process receipts in multiple languages, including unstructured documents such as itineraries and itemized receipts.

### Data extraction

From each receipt, the agent identifies and extracts:

- Merchant name
- Expense date
- Total amount
- Currency
- Payment method
- Line-item details (when available and itemization is required)

### Categorization and rule application

The agent automatically classifies each expense into the configured expense categories and subcategories based on the receipt content and descriptions for each of categories. It also handles special expense and allowance types:

- **Per diem** calculated from uploaded itinerary details
- **Mileage** calculated from travel map in the web app
<!-- - **Participant/guest** requirements -->

Company policies and rules configured in Business Central are enforced during this step.

### Expense report line creation 

The agent generates draft expense report lines from extracted data in both the web app and Business Central. The following fields are automatically populated: 

- Merchant  
- Description  
- Receipt number  
- Amount  
- Currency  
- Payment method  
- Expense date  
- Expense category  

#### Itemization  

If the selected category requires itemization, an additional tab is displayed in the web app. The agent extracts and assigns:   

- Subcategories with corresponding amounts for each itemized line  

#### Participants  

If the selected category requires participants, an additional tab is displayed in the web app where the user must provide:  

- Participants associated with the expense event  

> [!NOTE]  
> The user can automatically assign themselves as a participant and add additional guests, either internal (employees) or external. 

#### Per diem expenses 

If the selected category is configured as a per diem type, the agent extracts additional details: 

- Expense location  
- Start date and time  
- End date and time  

#### Mileage expenses 

For mileage-type expenses, a dedicated user interface is presented with the following fields:  

- Starting point  
- Ending point  
- Mileage  
- Round trip  

The user must provide the starting and ending points. The agent calculates available routes showing this on the displayed, including the fastest and alternative options. The user selects the preferred route and can enable the **Round trip** option if applicable. 

> [!NOTE]
> When the user selects a route and confirms the expense, a screenshot of the chosen route is captured and attached to the expense record. 

### User review

Expense users can review, edit, and submit expenses through the web app.

No Business Central license is required for this process if not processes inside Business central.

The user must review all expenses before submitting the report. As extraction and categorization are performed by the agent, the user is required to validate the accuracy of all data. After completing the review, the user can submit the expense report for approval.

### Automated workflow

The agent runs the following sequence automatically:

1. Receipt intake
2. Data extraction
3. Categorization and Itemization
4. Expense creation
5. Monthly expense report creation
6. Submission for approval
7. Approval policy validation
8. Posting of approved expense reports

## Setup and prerequisites

Before you can use the Expense Agent, an administrator must complete a few configuration steps in Business Central and the Microsoft 365 Admin Center. The following sections describe each requirement.

### AI subprocessor requirement

The Expense Agent uses Anthropic models. To use the agent, you must enable Anthropic as a subprocessor in the **Microsoft 365 Admin Center**. Learn more at [Anthropic as a subprocessor for Microsoft Online Services](/microsoft-365/copilot/connect-to-ai-subprocessor).

### Activation and configuration

Administrators enable the agent from Business Central using the dedicated **EA** hexagon icon, where they specify the required settings. Learn more at [Expense Agent Setup](expense-agent-configuration-page.md).

### Billing for use

The Expense Agent consumes Copilot Credits for AI processing. It costs 50 Copilot Credits for one receipt handling (one expense creation) regardless of complexity; it covers whole process from extraction, through categorization and itemization, groupping into expense reports and approving. Set up a billing model for your Business Central environment before using the agent. Learn more in [Manage consumption-based billing](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-consumption-billing).

### How the agent operates

Expense Agent runs in the background and uses AI to process receipts and create expenses. The agent notifies users when their review is needed, such as when extracted and categorized expenses are ready for verification.

The agent interacts with Business Central in a similar way as a user. It receives natural-language instructions that define how to handle expenses and uses page metadata (captions, tooltips, and other properties) along with its own instructions to determine each processing step.

### Reviewing agent activity

Administrators and users can review the agent's processing steps, imported receipts, and created expense details. The web app and Business Central both display the categorized data the agent entered alongside the original extracted data, so users can compare and correct values as needed.

## Processing flow in detail

### Receipt intake via web app

The Expense Agent web app is available at [https://app.expenses.dynamics.com/](https://app.expenses.dynamics.com/).

- Requires only a registered Expense User with a Microsoft Entra ID. No Business Central license needed.
- Uploading a receipt triggers extraction and AI processing
- Extracted data is stored as a JSON representation
- A new **Expense** record is created

### Receipt intake via shared mailbox

When you enable the shared mailbox, the Expense Agent uses an internal email processor in Business Central.

- Processes emails with attachments or inline content.
- Registers each email as an expense.
- Sends attachments and content to the AI model for analysis and extraction.

> [!NOTE]
> A dedicated mailbox is recommended.

### Categorization, validation, and issue detection

After extraction, the agent:

- Assigns **Expense Categories** and **Expense Subcategories** when itemization is required
- Populates all relevant fields
- Flags issues when:
  - A currency doesn't exist in Business Central
  - A problem occurred during extraction

Users must resolve issues before they submit the expense.

### Expense report creation

The agent creates monthly **Expense Reports** per employee, grouping all expenses for the period into a single report. The agent flags issues when:

- Participants are required but not specified
- An amount exceeds policy limits
- An expense is nonrefundable
- Required fields are missing
- A justification is missing (when required by policy)

Reports can be reviewed in the web app or in Business Central (for licensed users).

Controllers and approvers can review and adjust:

- Refundability
- Payment method
- Amount
- Dimensions
- Project and task numbers
- Billable/non-billable status

After approval, expense reports can be posted.

> [!NOTE]
> If you fill in the **Project No.** and **Project Task No.** fields on an expense report line, posting that expense also creates a **Project Ledger Entry**.

### Posting and reimbursement

Posting an expense report in Business Central creates:

- Expense Ledger Entries
- Employee Ledger Entries
- Detailed Employee Ledger Entries
- G/L Entries
- Project Ledger Entries (if applicable)

After posting, you can reimburse the employee through **Payment Journals** using **Employee** as the **Account Type**.

## Next steps

- [Set up Expense Agent](ExpenseAgentSetupGuide.md)

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Responsible AI FAQ for Expense Agent](faqs-expense-agent.md)
