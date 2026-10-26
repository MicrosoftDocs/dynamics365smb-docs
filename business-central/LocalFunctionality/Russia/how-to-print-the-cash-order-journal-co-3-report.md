---
title: Printing the cash order journal CO-3 report in Russia
description: Russian localization provides functionality for generating and printing the Cash Order Journal CO-3 report.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: cash order journal, CO-3 report, cash orders, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Print Cash Order Journal CO-3 report

The **Cash Order Journal CO-3** report shows the unified standard printing form (typically on a monthly basis).  

This report shows the register of posted ingoing and outgoing cash orders during a specified reporting period.  

## Steps to print the cash order journal CO-3 report

Before you run the report, set **Cash Order KO3 Template Code** in **General Ledger Setup**.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Order Journal CO-3**, and then choose the related link.
1. In the **Cash Order Journal CO-3** window, fill in the fields.

   | Field | Description |
   |:-|:-|
   | **Cash Account No.** | Select the cash account number for which the journal is to be printed. |
   | **Starting Date** | Enter the start date of cash orders to be included in the register. |
   | **Ending Date** | Enter the end date of cash orders to be included in the register. This date is set automatically to the last day of the month. |
   | **Employee No.** | Select the employee who is responsible for the report. The employee’s name – last, first, and middle – are printed on the title page of the report. |

1. Choose **OK** to export the report to Excel. Print the exported workbook from Excel.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
