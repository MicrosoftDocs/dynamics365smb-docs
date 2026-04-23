---
title: Troubleshoot Expense Agent Issues
description: Find solutions for common issues in Expense Agent, including sign-in problems, receipt upload failures, and policy violations.
author: brentholtorf
ms.topic: conceptual
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Troubleshoot common issues in Expense Agent

If you run into problems while using [!INCLUDE[prod_short](includes/prod_short.md)] Expense Agent, the following sections can help you find a solution.

## You can't sign in or access Expense Agent

If you get an "access denied" or "not authorized" error, try signing in again. If the problem continues, contact your administrator to make sure you have the right permissions.

## Receipt upload fails

Make sure your file meets these requirements:

- **Format**: JPEG, PNG, or PDF
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

If a file you try to upload is flagged for malware, the upload is blocked for security. Use a different file or re-scan the original file with your antivirus software before trying again.

## AI quota exceeded

If you get a message that the AI quota is exceeded, the system has reached its processing limit. Try again later. If the issue continues, contact your administrator.

## Related information

- [Expense Agent overview](expense-agent-overview.md)
- [Upload receipts in Expense Agent](expense-agent-upload-receipts.md)
- [Expense policy compliance in Expense Agent](expense-agent-policy-compliance.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
