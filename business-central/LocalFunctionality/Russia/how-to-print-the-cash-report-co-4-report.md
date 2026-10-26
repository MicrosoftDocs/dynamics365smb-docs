---
title: Printing the cash report CO-4 report in Russia
description: Russian enhancements include support for the Cash Report CO-4, a standardized daily cash account report.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: cash report CO-4, cash report, CO-4, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Print the Cash Report CO-4 report

The **Cash Report CO-4** report shows cash transactions for one operational day of a cash account.

This report shows the opening balance of all the posted ingoing and outgoing cash orders, and the closing balance of an operational day for one cash account.  

## Steps to print the cash report CO-4

Before you run the report, set **Cash Order KO4 Template Code** in **General Ledger Setup**.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Report CO-4**, and then choose the related link.

1. In the **Cash Report CO-4** window, fill in the fields.

   | Field | Description |
   |:-|:-|
   | **Cash Account No.** | Select a cash account number. |
   | **Report Type** | Select the type of report to run. Reports include **Cash Report CO-4** and **Cash Additional Sheet**. |
   | **Date** | Enter the operational date of the cash account transactions to be reported. |
   | **Cashier** | Select the employee who is the contact for this cash account. This employee must sign the end of the report. |
   | **Print Title Sheet** | Select to print a title sheet. |
   | **Print Last Sheet** | Select to print a last sheet. |
   | **Preview Without Page Numbering** | Select to generate the report without updating cash report page numbering. |

1. Choose **OK** to export the report to Excel. Print the exported workbook from Excel.

## Related information

[Petty cash management](petty-cash-management.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
