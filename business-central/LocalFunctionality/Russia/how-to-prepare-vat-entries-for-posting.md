---
title: Preparing VAT entries for posting in Russia
description: Russian localization allows you to periodically remit net VAT from sales and purchase transactions to the tax authorities.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: VAT entries, VAT settlement, VAT posting, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Prepare VAT entries for posting

Use the **VAT Settlement Worksheet** to prepare transactions with open VAT amounts for manual settlement and copy the entries to the appropriate **VAT Settlement Journal**. Configure **Manual VAT Settlement**, an unrealized VAT type, and the settlement journal template and batch in **VAT Posting Setup** before you begin.

## Steps to prepare VAT entries for posting

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Settlement Worksheet**, and then choose the related link.
1. Select the filters that define the VAT related transactions that you want to include in the VAT settlement.

   | Field | Description |
   |:-|:-|
   | **Type** | Select the type of transactions that you want to include in the VAT settlement. |
   | **View by** | Select the time period for the VAT settlement. |
   | **View as** | Select how you want to view the net VAT. The options include **Net Change** and **Balance at Date**. |

1. Choose **Suggest Documents**. Transactions with open VAT entries that match the filters that you selected are displayed.

1. Review the transactions that are included to ensure accuracy. If necessary, adjust your filter selection.

1. Choose **Copy Lines to Journal**.
1. Review the copied lines in the **VAT Settlement Journal**, and then choose **Post**.

Posting the journal creates the VAT settlement entries. This manual settlement workflow isn't the **Calc. and Post VAT Settlement** batch job used to close VAT entries for reporting.

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
