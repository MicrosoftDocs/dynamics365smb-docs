---
title: Inventory act of receivables and payables INV-17 in Russia
description: Provides guidance on using the INV-17 and Supplement to INV-17 reports as part of Russian localization in Business Central.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: inventory acts, inventory act card, inventory act processing, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Inventory act of receivables and payables INV-17

The inventory act of receivables and payables feature enables you to prepare an inventory of debts and liabilities, and print reports in the following formats:

- INV-17
- Supplement to INV-17

## Set up a number series for inventory acts

The following procedure shows how to set up a number series for inventory acts. 

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
1. In the **General Ledger Setup** window, fill in the **Contractor Invent. Act Nos.** field.

## Inventory act processing

You can create and process inventory acts of contractors' accounts. You can print inventory acts.

### Create an inventory act card

The following procedure shows how to create an inventory act card. 

1. Search for **Contractors Inventory Acts**, open the related list, and create a new act.

1. In the **Invent. Act Card** page, enter information in the following fields:

   | Field | Description |
   |:-|:-|
   | **No.** | This field displays the number of the act, and is filled in automatically from the number series. |
   | **Act Date** | This field displays the act date, and is filled in with the work date. |
   | **Inventory Date** | This field displays the date of inventory, and is filled with the work date. Debts and liabilities are calculated on this date. |
   | **Reason Document Type** | Select the type of reason document from the following:   -   **Order** -   **Resolution** -   **Regulation** |

1. Choose **Suggest Lines**.

   > [!NOTE]
   > Leave the customer and vendor filters blank to include all contractors. Set filters if you want to calculate lines for specific customers or vendors.

   Debts and liabilities for vendors and customers are calculated, and lines are created. For each customer and vendor, the total debt and the total liability amount (taking posting groups into account) on the inventory date are calculated, and shown in a separate line. The line fields are listed in the following table.

   | Field | Description |
   |--|--|
   | **Contractor Type** | This field displays the contractor type (Customer, Vendor). |
   | **Contractor No.** | This field displays the number corresponding to the contractor. |
   | **Contractor Name** | This field displays the name of the contractor. |
   | **Posting Group, G/L Account No.** | This field displays the posting group and the receivables or payables account for which the debt or liability amount is calculated. |
   | **Category** | This field displays the amount category (Debts, Liabilities). |
   | **Total Amount** | This field displays the total amount of debts or liabilities. |
   | **Confirmed Amount** | This field displays the total amount of debts or liabilities by default. |

### Change separate lines in an inventory act

The following procedure shows how to change individual lines in an inventory act on the **Invent. Act Card** page.

1. Specify whether the amount (or part of the amount) is one of the following:

    - Confirmed by contractor
    - Not confirmed
    - Overdue

1. If the amount isn't confirmed, enter the amount that isn't confirmed in the **Not Confirmed Amount** field.

1. If the amount is overdue, enter the overdue amount in the **Overdue Amount** field.

1. To recalculate amounts after you post or apply missing documents, choose **Suggest Lines**.

1. Select the vendor or customer code, and then choose the **OK** button. 

The debts and liabilities amount for the selected vendor or customer is recalculated and the lines are inserted in the document.

## Print the INV-17 form and the supplement to INV-17 form

Configure **INV-17 Template Code** and **INV-17 Appendix Template Code** in **Inventory Setup** before you generate the reports. These reports export to Excel.

The following procedure shows how to print the INV-17 form and the Supplement to INV-17 form.

1. On the **Invent. Act Card** page, choose **Release**.
1. Choose **Act** > **Employee Signatures**.
1. Select the following fields:

    - **Chairman**
    - **Member1**
    - **Member2**
    - **Member3**
    - **Accountant**

    > [!NOTE]
    > All selected signatures are reflected in the appropriate fields.

1. Choose the **Print** action, and then choose the **Invent. Act INV-17** action to print the inventory act.
1. Choose **Print** > **Supplement to INV-17** to generate the supplement to the inventory act.

For each report, choose **OK** to generate the workbook, and then print it from Excel.

## Related information

- [Russian Payables Reports](russian-payables-reports.md)  
- [Russian Receivables Reports](russian-receivables-reports.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
