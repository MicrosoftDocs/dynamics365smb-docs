---
title: Expense Agent Overview
description: Expense Agent automates expenses processing in Business Central. Speed up expense posting, approvals reimbursement, and reduce bottlenecks.
ms.date: 04/20/2026
ms.update-cycle: 180-days
ms.topic: overview
author: altotovi
ms.author: altotovi
ms.reviewer: altotovi
ms.collection:
  - bap-ai-copilot
ms.search.form: 4400, 4410
---
# Expense Agent overview

Expense Agent extends expense management by letting users submit receipts outside Business Central while financial processing remains in Business Central.

Many people who submit expenses work mainly in email or mobile workflows and might not have a Business Central license. Expense Agent supports these users through a web app and shared mailbox intake, so they can submit receipts without using Business Central directly.

Expense Agent uses AI to automate receipt intake, data extraction, categorization, and draft expense creation. Users and approvers still review and correct data before submission, approval, and posting.

This approach reduces manual entry while preserving existing Business Central controls for permissions, policy validation, audit trails, and posting.

> [!NOTE]
> [!INCLUDE[copilot-language-support-en-only](../includes/copilot-language-support-en-only.md)]

## Expense Agent Core Functionality

The Expense Agent orchestrates the full expense lifecycle, from receipt capture and interpretation to expense report generation and submission. Key capabilities include: 

### Receipt Understanding

- Intake of receipts from:

  - The **dedicated Expense Agent Dashboard** - [Web App](https://app.expenses.dynamics.com/) 
  - A monitored **shared mailbox**
- Support for multiple file formats (JPEG, PNG, PDF) and languages
- Parsing of unstructured documents, including itineraries and complex receipts

### Data Extraction

- Automatic identification and extraction of:

  - Merchant name
  - Expense date
  - Total amount
  - Currency
  - Line‑item details (if available and required for itemization)

### Categorization & Rule Application

- Automatic classification into **Expense Categories** or **Subcategories**
- Handling of special expense types:
  - **Per diem** (based on itinerary details)
  - **Mileage** (based on travel maps)
  - **Participants**/guests requirements
- Enforcement of internal company policies and rules

### Expense Report Line Creation

- Transforms extracted data into draft expense report lines
- Populates fields such as:
  - **Merchant**
  - **Description**
  - **Receipt number**
  - **Amount**
  - **Currency**
  - **Expense date**
  - **Expense Category**
  - **Expense Subcategory**

### User Review & Web Experience

- Users review and submit all expenses via the web app or via forwarding emails to the shared mailbox
- No Business Central license required to use the web app or email forwarding
- Users can edit, correct, or supplement information before submission in the web app
- After reviewing, user can submit expense report for approval

### Workflow Orchestration

- Fully automated sequence:
  - Receipt intake
  - Extraction
  - Categorization
  - Expense creation
  - Monthly expense report creation (option to create expense report per trip is planned for public preview in July)
  - Submitting for approval
  - Approval policy validation (planned for public preview in July)
  - Approving and posting expense reports

## Setup and Prerequisites

### AI Subprocessor Requirement

The **Expense Agent** uses Anthropic models, which must be enabled as a subprocessor in the **Microsoft 365 Admin Center**:

Copilot → Settings → Data Access

> [NOTE!]
> Read more details about [Anthropic as a subprocessor for Microsoft Online Services](https://learn.microsoft.com/en-us/microsoft-365/copilot/connect-to-ai-subprocessor) before enabling it.

### Activation and configuration

The agent is available in Business Central and is ready for you to use. Administrators can enable the agent from Business Central via a dedicated “EA” hexagon icon where they will specify all required actions. More details about how to activate and configure Expense Agent can be found in [Expense Agent Setup](ExpenseAgentSetupGuide.md).

### Billing for use

The Expense Agent uses Copilot Credits for AI interactions, which can incur charges based on interaction complexity. Before you use the agent, set up a billing model for your Business Central environment. Learn more in [Manage consumption-based billing](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-consumption-billing).

### General agent operations

The Expense Agent runs autonomously in the background, using AI to do its tasks while keeping users informed about key steps and involving them when needed. Involvement might be needed in specific scenarios, like when users review extracted and categorized expense created by the agent, based on set preferences.

Conceptually, the agent interacts with Business Central features like a Business Central user. The agent gets general instructions in natural language that outline how to handle expenses. It uses UI metadata, like captions, tooltips, and other properties, along with data on Business Central pages and its own instructions, to decide each step needed to finish the task. 

### Customer and user involvement

Administrators and users can check the agent's steps, imported receipts, and the created expenses details. They can easily see categorized data the agent enters compared to data from Business Central's business logic and imported extracted data, and change the expense or expense report as desired.

## End-to-End Processing Flow

### Receipt Intake

Agents at this moment can handle various types of receipts and invoices with different languages, but also with the itineraries to extract data for per-diem calculation.

#### Receipt Intake via Expense Agent Dashboard (Web App)

The Expense Agent Dashboard (web app) is available at https://app.expenses.dynamics.com/ 

- **Does not require a BC license**; only registered Expense User with the Entra ID.
- Receipt upload triggers extraction + LLM processing
- Extracted data is stored as a JSON representation
- Registers new **Expense**

#### Receipt Intake via Shared Mailbox

If you enable the shared mailbox, the Expense Agent uses an internal email processor in Business Central (similar to Payable Agent or Sales Order Agent).

- Emails with attachments or body content are processed automatically
- Registered as **Expenses**
- Forwarded to LLM for analysis and extraction

> [!NOTE]
> A dedicated mailbox is recommended.

#### Categorization, Validation & Issue Detection

Once the document has been analyzed by LLM, and just after extraction, the agent:

- Assigns **Expense categories** and **Expense subcategories** if **Itemization** is required
- Populates all relevant fields
- Flags issues when:
  - Currency doesn’t exist in Business Central
  - There is a problem during extraction process

Users must resolve issues before submission.

### Expense Report Creation

The agent autonomously creates monthly **Expense Reports** per employee:

- All expenses for the period are grouped into the report
- Flags issues when:
  - Participants are required
  - Amount exceeds policy limits
  - Expense is non-refundable
  - Required fields are missing
  - Justification is missing (if required)
- Reports can be reviewed by users in:
  - The web app
  - Business Central (for licensed Business Central users)

Controllers/approvers can review and adjust:

- Refundability
- Payment method
- Amount
- Dimensions
- Project and task numbers
- Billable/non-billable status

After approval, expense reports can be posted.

> [!NOTE]
> If you add the **Project No.** and **Project Task No.** to the Expense Report Line, this particular expense will also create **Project Ledger Entry** after posting.

### Posting & Reimbursement

Posting (performed in Business Central) creates:

- Expense Ledger Entries
- Employee Ledger Entries
- Detailed Employee Ledger Entries
- G/L Entries
- Project Ledger Entries (if applicable)

Once the expense report is posted, it can be reimbursed. Reimbursement is processed through **Payment Journals** using **Employee** as the** Account Type**.



## Next steps

- [Set up Expense Agent](ExpenseAgentSetupGuide.md)

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Responsible AI FAQ for Expense Agent](faqs-expense-agent.md)  
