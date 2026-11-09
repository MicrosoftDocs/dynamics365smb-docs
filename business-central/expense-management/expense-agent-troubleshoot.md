---
title: Troubleshoot Expense Agent Issues
description: Find solutions for common issues in Expense Agent, including sign-in problems, receipt upload failures, and policy violations.
author: jswymer
ms.topic: concept-article
ms.date: 11/04/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot
---

# Troubleshoot common issues in Expense Agent

[!INCLUDE [online_only](../includes/online_only.md)]

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

If you run into problems while using [!INCLUDE[prod_short](../includes/prod_short.md)] Expense Agent, the following sections can help you find a solution.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## You can't sign in or access Expense Agent

If you get an "access denied" or "not authorized" error, select your profile picture in the upper right corner, select **Sign out**, and then sign in using your proper credentials (name and password). If the problem continues, contact your administrator to make sure you have the right permissions.

## Receipt upload fails

Make sure your file meets these requirements:

- **Format**: JPEG, PNG, GIF, WebP, HEIC, HEIF, or PDF
- **Size**: 10 MB or smaller

If your file meets the requirements but the upload still fails, check your internet connection and try again.

## AI doesn't detect receipt details correctly

The AI suggests details such as the amount, date, and merchant based on what it detects in the receipt image. These suggestions might not always be accurate. Review the prepopulated fields and manually edit anything that needs correction before you confirm.

## An expense shows a policy violation

If an expense is flagged for a policy violation, open the expense and review the flagged fields. Fix any values that don't meet your organization's policy. For soft warnings, you can add a justification if your company allows it.

## You get a network error

Network errors usually mean the connection to the server was interrupted. Check your internet connection and try the action again. If the error persists, wait a few minutes before retrying.

## An expense or report is missing

If you can't find an expense or report, it might have been deleted by you or another user. Check your filters and search criteria to make sure you're looking in the right place. If you still can't find it, contact your administrator.

## Malware detected in upload

If a file you try to upload is flagged for malware, the upload is blocked for security. Use a different file or rescan the original file with your antivirus software before trying again.

## Travel requests aren't available or actions are disabled

**Create travel request** appears only when the connected Business Central environment supports travel requests. If the action is missing, ask your administrator whether the environment supports this capability.

If travel actions are disabled, check your internet connection and company access. Travel requests can't be created, edited, submitted, approved, or deleted offline. A request awaiting approval is read-only. You can revise it after the approver sends it back.

## A travel request can't be saved or submitted

1. Check that the request has a purpose and valid expected start and end dates. The end date can't be before the start date.
1. Add at least one estimated cost. For each estimate, enter a description, amount, and currency. Select a category when the cost type is **Category**.
1. If you entered any details on **Per diem allowance**, complete the location and both times. The return must be after departure. If you don't want to include per diem, clear all three fields.
1. Review any highlighted fields and correct them.
1. Ask your administrator to check your expense user and approver setup if submission still fails.

Saving and submitting are separate operations. If the request was saved but submission failed, reopen the saved draft and try submitting again. You don't need to create another request.

## An approved travel request has no expense report

Approval normally creates linked reports in Business Central. You see only your own linked report in Expense Agent.

If you created the request and your linked report was deleted, find the approved request on **Approved** in the web app or **Submitted** in the mobile app. Open the request for review and select **Create expense report** when the action is available. If you're an additional traveler whose report is missing, contact the requester or your administrator.

If the trip is no longer needed and **Delete** is available, you can try deleting the request. Business Central blocks deletion while any expense report or report line still references the request, including another traveler's report or a posted report. Deleting only your own report doesn't remove those other links.

## A trip receipt is assigned to the wrong report

For a report linked to a travel request, matching uses the expected trip dates, with up to three days before and after the trip also considered. Other draft reports can be candidates too. Matching doesn't guarantee that a receipt goes to the trip report.

Review the receipt date and report assignment. If necessary, [move the expense to the correct draft report](expense-agent-expense-reports.md#move-an-expense-to-a-different-report).

## AI quota exceeded

If you get a message that the AI quota is exceeded, the system reached its processing limit. Try again later. If the issue continues, contact your administrator.

## Agent doesn't process incoming emails

If Expense Agent isn't processing incoming emails, check these setup and runtime conditions:

1. Verify that the agent is active.
2. Confirm that the mailbox account is configured correctly.
3. Make sure Email Connector v4 is installed and configured.
4. Check scheduler task entries for errors.
5. Review entries in the **EA Scheduler Task** table.
6. Verify that the user has **Can Create Task** permission.

## You can't turn off the agent

If turning off **Active** shows this message, try again after a short wait and then check service connectivity:

Failed to unregister environment from Expense Agent service. Please try again or contact support.

If the issue persists, contact support.

## Expenses fail validation or show policy violations

If you can't save or submit an expense, or it shows a policy violation, review these settings:

1. Check the age of the expense against **Do Not Allow Expenses Older Than**.
2. Verify that category and subcategory values are valid and active.
3. Confirm that the payment method has a **Reimbursement Type** assigned (**Company Paid**, **Employee Paid**, or **Credit Card**).
4. Check that a posting group is assigned to the category.
5. Verify that the employee is configured as an expense employee.

## Per diem doesn't calculate

If per diem amounts don't populate, verify these configurations:

1. **Full Per-Diem Calculation** isn't set to **None**.
2. Per diem rates are configured for the location and category.
3. Travel dates meet minimum-hour requirements.
4. Partial-day rule settings are configured correctly.
5. **Per Diem Rounding Precision** is set.

## Expense report posting fails

If expense reports can't be posted, review posting setup:

1. Verify that the posting group has all required G/L accounts configured.
2. Check that G/L accounts allow direct posting.
3. Confirm that the number series for posted expense reports is set.
4. Verify the approval status if approval workflow is enabled.
5. Check that source code **EXPENSE** exists in Source Code Setup.

## Policy evaluation troubleshooting

If an expense shows **Policies pending**, the evaluation might still be running, might not have started, or might be outdated because the expense or an applicable policy changed.

1. Wait for the background evaluation to finish, and then refresh the report.
1. If the submitter can't find **Check policies with AI**, confirm that the report is a draft and needs evaluation.
1. Ask an administrator to open **Configure Expense Agent** assisted setup and verify that **Evaluate compliance with AI** is turned on.
1. If you receive a quota message, follow the guidance in [AI quota exceeded](#ai-quota-exceeded).
1. If the report is still pending, try **Check policies with AI** again when the action is available. Otherwise, submit the report so the approver can review the pending status. Contact your administrator if the issue continues.

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Upload receipts in Expense Agent](expense-agent-upload-receipts.md)  

[Plan and submit travel requests](expense-agent-travel-requests.md)

[Expense policy compliance in Expense Agent](expense-agent-policy-compliance.md)  
[Set up the Expense Agent](expense-agent-configuration-page.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
