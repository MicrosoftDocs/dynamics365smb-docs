---
title: Submit VAT Statements in the Italian Version [IT]
description: Learn how to review, print, submit VAT statements, and settle and post VAT transactions in the Italian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: deduct VAT, VAT deduction, submit VAT statements, review VAT statements, print VAT statements, settle VAT transactions, post VAT transactions, Italian version
ms.search.form: 12121, 12123
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Submit VAT statements in the Italian version

Companies must pay VAT for most purchased goods and services. VAT can be deducted if the goods and services that are purchased by a company are used in the production of its income.  

Use VAT statements to review VAT amounts for a period. VAT settlement transfers the amounts to the settlement account. These processes are separate from the threshold-based VAT Transactions Report.

## Review and print VAT statements  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Statements**, and then choose the related link.  
1. On the **VAT Statement** page, in the **Name** field, select the required VAT statement, and then choose the **Print** action.  
1. On the **Options** FastTab, enter a date interval to limit the period covered by the statement and define what type of VAT entries that you want to include.  
1. Choose the **Print** button to print the VAT statement.  

You can use the printed VAT statement to review the VAT entries to be submitted to the tax authorities.  

## Settle and post VAT transactions  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Calculate and Post VAT Settlement**, and then choose the related link.
1. On the **Options** FastTab, enter the date interval and select the correct VAT settlement account. Select the **Post** checkbox only when you're ready to post the VAT amounts to the settlement account.
1. Run the report. If **Post** is selected, confirm that you want to calculate and post the settlement.

After you calculate and post the VAT settlement, VAT amounts are transferred to the appropriate VAT settlement accounts. Clear **Post** when you only want to calculate the settlement without posting.

## Submit VAT statements

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Statements**, and then choose the related link.  
1. On the **VAT Statement** page, in the **Name** field, select the required VAT statement, choose the **Print** action, and then choose the **PDF** option.  

Submit the exported PDF if the tax authority accepts that format for your reporting obligation. Exporting the file doesn't submit it automatically.

For the Italian periodic VAT payment communication, use **Periodic VAT Payment Communication** to generate the XML file. This is a separate report from the printed VAT statement. For threshold-based transaction reporting, go to [Export VAT Transactions Reports](how-to-export-vat-transactions-reports.md).

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
