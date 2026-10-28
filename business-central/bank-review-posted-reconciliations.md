---
title: Review and analyze posted bank reconciliations
description: Learn how to review posted bank reconciliations, compare statement history, and save a detailed report for period-end reviews and audit evidence.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 10/26/2026
ms.search.keywords: posted bank reconciliation, bank account statement, audit evidence, analysis mode
ms.search.form: 383, 389, 1407
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Review and analyze posted bank reconciliations

After you post a bank reconciliation, you can review the completed reconciliation to verify balances and investigate matched transactions. Use posted bank statements in [!INCLUDE[prod_short](includes/prod_short.md)] to support period-end reviews, compare reconciliation history, and provide evidence for an audit.

Choose the page or report that fits your task.

| Task | Page or report |
|------|----------------|
| Find completed reconciliations for a bank account or period. | **Bank Account Statement List** |
| Review the balances, statement lines, and applied entries for one reconciliation. | **Bank Account Statement** |
| Filter, group, and compare posted statement information. | Analysis mode on **Bank Account Statement List** |
| Print or save a detailed record of a completed reconciliation. | **Bank Account Statement** report (1407) |

> [!NOTE]
> This article describes statements posted from the **Bank Acc. Reconciliation** page. If you use the **Bank Rec. Worksheet** page in a North American version, follow the guidance in [View the posted bank account reconciliations](LocalFunctionality/UnitedStates/how-to-reconcile-bank-accounts.md#view-the-posted-bank-account-reconciliations).

## Review a completed reconciliation

Use the **Bank Account Statement List** page to find posted reconciliations and open their details.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Account Statement List**, and then select the related link.
2. Filter **Bank Account No.** and **Statement Date** to find the account and period that you want to review.
3. Open the statement that you want to review.
4. Compare **Balance Last Statement**, **Statement Ending Balance**, and **Statement Date** with the statement from your bank.
5. Review the statement lines, including **Transaction Date**, **Description**, **Statement Amount**, **Applied Amount**, and **Difference**.
6. Select an **Applied Amount** value to review the bank account or check ledger entries matched to that line.

The **Total Balance** field combines the balance from the last statement with the statement line amounts. The **Total Difference** field shows the sum of the differences between statement amounts and applied amounts.

## Analyze posted statement history

Use analysis mode on the **Bank Account Statement List** page to compare the available statement information without changing the posted data. For example, you can review ending balances over time for one bank account or group statements by bank account for a period-end review.

To use analysis mode, you need the **DATA ANALYSIS - EXEC** permission set or equivalent permissions. Learn more about access and analysis features in [Analyze list page and query data using the data analysis feature](analysis-mode.md).

1. Open the **Bank Account Statement List** page.
2. Filter the list to the bank account and statement date range that you want to analyze.
3. Select **Enter analysis mode** :::image type="content" source="media/analysis-mode-icon.png" alt-text="Screenshot of the Analysis Mode icon.":::.
4. In the **Columns** pane, include **Bank Account No.**, **Bank Account Name**, **Statement No.**, **Statement Date**, **Balance Last Statement**, and **Statement Ending Balance**.
5. Drag the **Bank Account No.** column heading to the **Row Groups** part, and sort **Statement Date** to review statements in date order.
6. Compare the individual statement balances to identify changes that you want to investigate.
7. Select **Leave analysis mode**, and open a statement to review its lines and applied entries.

Compare ending balances as individual statement values, not as a sum across periods. An ending balance isn't the amount of activity in a period. Keep bank accounts separate, especially when they use different currencies.

The list contains statement-level information. To investigate individual transactions or outstanding entries, open the statement or run the report.

## Print or save a completed reconciliation

Use the **Bank Account Statement** report to document a completed reconciliation. The standard report includes statement balances, general ledger balance information, and statement lines. You can also include details of outstanding bank transactions and checks.

1. On the **Bank Account Statement List** page, select the statement that you want to document.
2. Select **Print**.
3. Check the **Bank Account No.** and **Statement No.** filters on the report request page.
4. Turn on **Print Outstanding Transactions** if you want to include details of outstanding transactions and checks.
5. Select **Preview** to review the report.
6. Select **Print** to print the report, or select **Send to** to save it as a PDF file.

Your organization can configure a different report for the **Print** action, so the available options can differ.

Outstanding transactions can help explain the difference between the bank statement balance and the bank account balance. For example, a payment might be recorded in [!INCLUDE[prod_short](includes/prod_short.md)] before it appears on the statement from your bank. A statement can be reconciled even though some bank account ledger entries remain outstanding.

For historical reviews, consider how later reconciliations and backdated entries affect outstanding-entry details. Learn more about report behavior and limitations in [Find outstanding transactions in previous periods](bank-how-reconcile-bank-accounts-separately.md#find-outstanding-transactions-in-previous-periods).

Learn more about saving report output in [Run and print reports](ui-work-report.md).

## Correct an error in a posted reconciliation

If your review identifies an error, you can undo the posted reconciliation and correct it before posting again. The **Undo** action deletes the posted statement and creates a new bank reconciliation. Learn more about the process and its limitations in [Undo a bank account reconciliation](bank-how-reconcile-bank-accounts-separately.md#undo-a-bank-account-reconciliation).

## Related information

[Reconcile bank accounts](bank-how-reconcile-bank-accounts-separately.md)  
[Manage and reconcile your bank accounts](bank-manage-bank-accounts.md)  
[Ad-hoc analysis of finance data](ad-hoc-analysis-finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
