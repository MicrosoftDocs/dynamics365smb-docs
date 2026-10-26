---
title: Import and Export Data in the Standard Import Export (SIE) Format
description: Set up SIE dimensions and account mappings, import transactions into general journals, and export Swedish general ledger data with Audit File Export.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import data, export data, SIE, standard import export, audit files export
ms.search.form: 5264, 5266, 5267, 5270, 5314, 5315
ms.date: 10/20/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import and export data in the standard import export (SIE) format

You can import and export general ledger data according to the standard import export (SIE) format. Choose SIE dimensions for imports and exports. For exports, choose a file type to control the level of detail. Learn more at the [Standard Import Export Group website](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d).

> [!NOTE]
> The Standard Import Export (SIE) extension provides SIE imports and adds the SIE export format to the Audit File Export app. In the current implementation, run the SIE setup guide to configure exports. You don't need the earlier **Feature update: Enable using SIE Audit Files Exports** switch. Learn more in [Export data for auditing](../../finance-how-to-export-audit-files.md).

## Audit files export

Use the **SIE Audit File Export Setup Guide** to set up the SIE format and map your chart of accounts.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SIE Audit File Export Setup Guide**, and then choose the related link.
1. Choose **Next**, and then select **Standard Account Type**.
1. Specify the accounting period or starting and ending dates for the mapping.
1. Open the G/L account mapping setup from the guide, and map your G/L accounts to the standard accounts.
1. Open the dimension setup from the guide if you want to include dimensions.
1. Complete the guide and choose **Finish**.

For manual setup and background processing options, see [Export data for auditing](../../finance-how-to-export-audit-files.md).

### Set up SIE dimensions

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Dimensions SIE**, and then select the related link.
1. In the **Dimension Code** field, select the Business Central dimension that you want to map.
1. In the **SIE Dimension** field, specify the number that you want to assign to the dimension.
1. In the **Selected** field, specify whether the dimension should be used when general ledger (G/L) data is imported or exported.

> [!NOTE]
> To add or change dimension mappings, open **Dimensions SIE** from search. When you open the page from the **Dimensions** field on **Import SIE**, you can change **Selected**, but you can't add or delete mappings or change their codes.

The current SIE file generator uses **Selected** on **Dimensions SIE**, not the document-specific **Dimensions** selection. Changing the document's **Dimensions** lookup doesn't update the shared **Selected** settings. Review the shared settings before each export, especially if you change them for an import.

### Audit file export document for SIE

Create an audit file export document after you complete the setup.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Audit File Export Documents**, and then choose the related link.
1. Choose **New**.
1. On the **General** FastTab, select **SIE** in **Audit File Export Format**, and select **G/L Account Mapping Code** for the reporting period.
1. Review **Starting Date** and **Ending Date**. The starting date must fall within an existing fiscal year.
1. Enter **Contact** and **Header Comment** if you want to include them in the file header.
1. On the **SIE** FastTab, select **File Type** using the descriptions below. Review **Fiscal Year**, which is initially set from **Starting Date** when the fiscal year is blank.
1. Review **Dimensions**. On **Dimensions SIE**, select **Selected** for the dimensions you want the SIE file generator to export.
1. Set **G/L Account Filter** if you want to limit the accounts in the account and balance sections of the file.
1. Choose **Start**.
1. When processing is complete, use **Download as File** on the **Lines** FastTab to download the generated file.

| File Type | Content |
|-----------|---------|
| **1. Year - End Balances** | Account information, opening and closing balance-sheet balances, and income statement balances. |
| **2. Periodic Balances** | Account balances and period net changes, with budget amounts when a budget filter is specified. |
| **3. Object Balances** | Account balances and period net changes, with additional balances filtered by selected global dimension values. |
| **4. Transactions** | Account information, balances, and individual general ledger entries for the selected date range. |

> [!IMPORTANT]
> For **4. Transactions**, **G/L Account Filter** limits the account and balance sections, but doesn't restrict the individual general ledger entries. The transaction section includes all G/L entries in the document's date range.

For **3. Object Balances**, use global dimensions 1 and 2 for dimension-filtered balances. The current calculations don't apply dimension value filters for other dimensions. **4. Transactions** can include other mapped dimensions on individual entries.

> [!NOTE]
> SIE exports don't use **Split By Month**, **Split By Date**, or **Create Multiple Zip Files**. These controls and the separate **Data check** action are hidden when the document uses SIE.

## Import data in SIE format

SIE imports create unposted general journal lines from transaction records in the file. Importing doesn't post the journal.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Import SIE**, and then choose the related link.
1. Fill in the fields as described in the following table.

    | Field | Description |
    |-------|-------------|
    | **Gen. Journal Template** | Select the general journal template to receive the imported transactions. |
    | **Gen. Journal Batch** | Select a batch in that template. Set up its number series if document numbers might be missing from the file. |
    | **Dimensions** | Select the mapped SIE dimensions to import. Configure the mappings on **Dimensions SIE** first. |
    | **Insert G/L Account** | Select to create missing accounts from account definitions in the SIE file. |
    | **Use Number Series for Doc. No.** | Select to combine the SIE voucher series and voucher number in the document number. If the resulting number is blank, the journal batch's number series supplies it. |

1. Choose **OK**, and then select the SIE file.
1. Open the journal batch and review the imported accounts, dates, amounts, document numbers, and dimensions before posting.

> [!NOTE]
> Balance-only SIE files don't contain the transaction records needed to create journal lines. For transaction data, use a file that contains SIE voucher and transaction records.

## Related information

- [Standard Import Export Group](https://go.microsoft.com/fwlink/?LinkID=164870&clcid=0x41d)  
- [Export data for auditing](../../finance-how-to-export-audit-files.md)
- [Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
