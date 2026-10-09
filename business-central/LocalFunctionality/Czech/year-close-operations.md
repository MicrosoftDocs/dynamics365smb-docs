---
title: Year closing operations in the Czech version
description: Learn how to run the Close Income Statement, Close Balance Sheet, and Open Balance Sheet reports to meet Czech year-end accounting requirements.
author: ACMartinKunes
ms.topic: how-to
ms.search.keywords: Czech, finance, CZ, closing operations
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Year closing operations in the Czech version

To comply with accounting legislation (Accounting Law 563/1991 §17), you must close and open certain account books at the end of the fiscal year:

- Close the profit and loss accounts with the **Close Income Statement CZ** report.
- Close the balance sheet accounts with the **Close Balance Sheet** report.
- Open the balance sheet accounts for the new fiscal year with the **Open Balance Sheet** report.

All three reports create lines in a general journal that you then post. They don't post entries directly.

## Close income statement accounts

The **Close Income Statement CZ** report creates journal lines that zero out your income statement accounts and transfer the balance to a retained earnings account.

1. Choose the **Tell Me** icon, enter **Close Income Statement CZ**, and then choose the related link.
1. In the **Fiscal Year Ending Date** field, enter the last date in the fiscal year that you're closing.
1. In the **Gen. Journal Template** and **Gen. Journal Batch** fields, select where the closing lines are created.
1. In the **Document No.** field, enter the document number to use on the closing lines.
1. In the **Retained Earnings Acc.** field, select the G/L account that collects the retained earnings.
1. In the **Post to Retained Earnings Acc.** field, select **Balance** to post retained earnings as one summarized line, or **Details** to post the retained earnings account as the balancing account on every line.
1. In the **Posting Description** field, enter the description to use on the closing lines.
1. In the **G/L Account Group** field, select the accounting circuit to close, if you use multi-circuit accounting.
1. Under **Close by**, select **Business Unit Code** and **Dimensions** to close per business unit or dimension combination, and select dimensions to use with the **Dimensions** field.
1. Choose **OK** to create the journal lines, and then post the batch.

## Close balance sheet accounts

The **Close Balance Sheet** report creates journal lines that transfer balance sheet account balances to a closing balance sheet account at year-end.

1. Choose the **Tell Me** icon, enter **Close Balance Sheet**, and then choose the related link.
1. In the **Fiscal Year Ending Date** field, enter the last date in the fiscal year that you're closing.
1. In the **Gen. Journal Template** and **Gen. Journal Batch** fields, select where the closing lines are created.
1. In the **Document No.** field, enter the document number to use on the closing lines.
1. In the **Closing Balance Sheet Account** field, select the G/L account that collects the closing balances.
1. In the **Post to Closing Balance Sheet Acc.** field, select **Balance** or **Details**, as described for the Close Income Statement CZ report.
1. In the **Posting Description** field, enter the description to use on the closing lines.
1. In the **G/L Account Group** field, select the accounting circuit to close, if you use multi-circuit accounting.
1. Under **Close by**, select **Business Unit Code** and **Dimensions** as needed.
1. Choose **OK** to create the journal lines, and then post the batch.

## Open balance sheet accounts

The **Open Balance Sheet** report creates journal lines that bring the closing balances back in as opening balances for the new fiscal year.

1. Choose the **Tell Me** icon, enter **Open Balance Sheet**, and then choose the related link.
1. In the **Fiscal Year Ending Date** field, enter the last date in the fiscal year that you closed.
1. In the **Gen. Journal Template** and **Gen. Journal Batch** fields, select where the opening lines are created.
1. In the **Document No.** field, enter the document number to use on the opening lines.
1. In the **Opening Balance Sheet Account** field, select the G/L account that holds the opening balances.
1. In the **Post to Opening Balance Sheet Acc.** field, select **Balance** or **Details**, as described for the Close Income Statement CZ report.
1. In the **Posting Description** field, enter the description to use on the opening lines.
1. In the **G/L Account Group** field, select the accounting circuit to open, if you use multi-circuit accounting.
1. Under **Open by**, select **Business Unit Code** and **Dimensions** as needed.
1. Choose **OK** to create the journal lines, and then post the batch.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
