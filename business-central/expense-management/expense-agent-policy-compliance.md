---
title: Understand Policy Compliance in Expense Agent
description: Learn how Expense Agent applies real-time expense rules and uses AI to evaluate your organization's natural-language expense policies.
author: jswymer
ms.topic: overview
ms.date: 10/02/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot
---

# How expense policy and rules compliance work

[!INCLUDE [online_only](../includes/online_only.md)]

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Expense Agent helps your organization review expenses in two ways. [!INCLUDE [prod_short](../includes/prod_short.md)] checks deterministic expense rules, and Expense Agent can use AI to evaluate natural-language policies. These checks give submitters and approvers information to resolve or assess potential issues.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Understand the difference between rules and policies

**Expense Management Rules** define measurable conditions. Business Central checks these rules when users work with expenses and again when they submit a report. Rules can:

- Enforce maximum or recommended spending limits  
- Require justification for amounts exceeding defined thresholds  
- Restrict or disallow specific types of expenses  
- Enforce the use of specific merchants or providers

**Expense Policies** describe expected behavior in natural language. When policy evaluation is enabled, Expense Agent uses AI to assess applicable policies. Policies can describe:

- When employees might use business class travel
- What is appropriate for business meals  
- Acceptable hotel standards and conditions for exceptions


Rules and policies are independent. An expense can pass its deterministic rules and still be flagged by an AI policy evaluation.

## Review deterministic rule results

Business Central checks expenses against the rules that your organization configured. If an expense doesn't meet a rule condition, you can review the issue before submission. Business Central checks the report again when you submit it.

Rule results can include warnings or conditions that prevent submission:

- **Warnings** identify a rule issue but can still let you proceed. Add a justification when your organization's setup requires one.
- **Blocks** identify a condition that you must fix before you can submit the report.

> [!TIP]
> Add a clear explanation in the **Notes** field on the **Categorization** tab when an expense needs justification. This information helps the approver understand the expense.

## Understand AI-assisted policy evaluation

An administrator creates policies in Business Central and enables AI-assisted evaluation through **Configure Expense Agent** assisted setup. Expense Agent evaluates only policies that apply to each expense.

Policy evaluation uses additional AI credits. Expense Agent attempts background evaluation after submission only when:

- AI-assisted policy evaluation is enabled.
- One or more expenses need evaluation.
- The required services are available.
- AI capacity and credits are available.

Submission can continue if the background evaluation can't start or finish. Affected expenses remain **Policies pending**, and the approver can see that the results aren't current.

### Policy compliance outcomes

Expense Agent combines the rule and policy results into these user-visible outcomes:

- **Non-compliant**: A deterministic Business Central rule has an unresolved violation.
- **Flagged**: AI-assisted evaluation found a potential policy issue. Open the expense to review the explanation.
- **Policies pending**: Policy evaluation hasn't finished, or the available results aren't current.
- **Compliant**: The expense has no current rule or policy issues. Expenses with no applicable policies also appear as compliant.

### Keep evaluation results current

Policy results correspond to the expense information and policy that Expense Agent evaluated. Changing an expense or an applicable policy can make earlier results outdated. The expense then shows **Policies pending** until a current evaluation finishes.

If policies are pending when an approver tries to approve a report, Expense Agent warns that one or more evaluations aren't current. The approver can cancel and wait for current results or continue with approval.

## Find and act on compliance information

:::image type="content" source="../media/expense-agent-expense-illustration.svg" alt-text="Expense report with line-level policy badges and compliance status.":::

Submitters and approvers can find compliance information in these places:

- **Expense list**: Each expense can show **Non-compliant**, **Flagged**, **Policies pending**, or **Compliant**.
- **Expense details**: Open an expense and review the **Summary** section for its current status and policy explanations.
- **Report summary**: If one or more expenses need attention, select the compliance warning to open **These expenses need your review**. Approvers don't see a report-level compliance indicator when all expenses are compliant.

Submitters can run a check on a draft report when the action is available. They can then correct an expense or submit the report with the result for the approver to review. For instructions, go to [Optionally check policies before you submit](expense-agent-expense-reports.md#optionally-check-policies-before-you-submit).

Approvers review current results and decide whether to approve the report or send it back. For instructions, go to [Approve or send back expense reports](expense-agent-approve-reports.md).

## Configure policy evaluation

Use the **Configure Expense Agent** assisted setup to enable AI-assisted policy evaluation and record whether your organization allows submitters to run evaluations before submission. For instructions, see [Configure AI-assisted policy evaluation](expense-management-setup.md#configure-ai-assisted-policy-evaluation).

To create and maintain the policies that Expense Agent evaluates, see [Create and manage expense policies](expense-management-categories-rules.md#create-and-manage-expense-policies).

## Understand privacy for policy evaluation

Expense Agent sends the information needed to evaluate an expense against the applicable policies. It can include participant names, participant types, and organization names when they're relevant to a policy. The AI input omits participant email addresses and employee numbers.

## Related information

[Set up expense categories, rules, and policies](expense-management-categories-rules.md)  
[Set up expense management](expense-management-setup.md)  
[Expense Agent overview](expense-agent-overview.md)  
[Upload receipts and create expenses](expense-agent-upload-receipts.md)  
[Edit and manage expenses](expense-agent-edit-expenses.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
