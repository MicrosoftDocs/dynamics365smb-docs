---
title: Account for the cost to dispose fixed asset in Russia
description: Russian functionality lets you record and report expenses related to the disposal of fixed assets.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: fixed asset disposal, write-off, maintenance code, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Account for the cost to dispose a fixed asset

The maintenance on disposal feature enables you to account for the amount spent to dispose a fixed asset (FA) as an expense. You can post operations related to spending for the disposal of a fixed asset, so that they're reflected in the FA Write-Off Act forms.

The expenses of a fixed asset disposal can be posted from general ledger journals, fixed asset journals, and purchase documents. The following procedure shows how to post the expenses for a fixed asset disposal by using the Fixed Asset General Ledger Journal.

The expenses on a fixed asset disposal can be printed in the FA Write-off Act FA-4 report and the FA Write-off Act FA-4a report.

## Set up a maintenance code

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Setup**, and then choose the related link.
1. In the **Fixed Asset Setup** window, on the **General** FastTab, enter a maintenance code in the **On Disposal Maintenance Code** field.
1. Close **Fixed Asset Setup**.

## Post expenses on a fixed asset disposal

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.
1. In the **Fixed Asset G/L Journal** window, fill in the fields as described in the following table.

   | Field | Description |
   |:-|:-|
   | **Account Type** | Select **Fixed Asset** as the account type. |
   | **Account No.** | Specifies the number of the fixed asset for disposal for which the expenses are made. |
   | **FA Posting Type** | Select **Maintenance** as the fixed asset posting type. |
   | **Maintenance Code** | Specifies the maintenance code that is entered in the **On Disposal Maintenance Code** field of the **Fixed Asset Setup** window. |

1. Fill in the posting date, document number, expense amount, and balancing account as required for the journal, and then choose **Post**.

## Print a report with expenses on a fixed asset disposal

1. Open the **FA Writeoff Act** for the fixed asset whose disposal expenses you posted.
1. Generate **FA Write-off Act FA-4** or **FA Writeoff Act FA-4a**, as appropriate for the asset.
1. Choose **OK** to export the report to Excel. Print the exported workbook from Excel.

   > [!NOTE]
   > If the expenses on the disposal of the fixed asset are made in advance, they're displayed on the second page of the report.

Configure **FA-4 Template Code** or **FA-4a Template Code** in **Fixed Asset Setup** before you generate the corresponding report. Printing doesn't post the write-off act. Use **Post** on the act to record the write-off.

## Related information

[Fixed Assets](../../fa-manage.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
