---
title: Inventory act of receivables and payables INV-17 in Russia
description: Russian enhancements include support for the INV-17 report and INV-17 supplement report.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Inventory Act of Receivables And Payables INV-17

The inventory act of receivables and payables feature enables you to prepare an inventory of debts and liabilities, and print reports in the following formats: 

- INV-17
- Supplement to INV-17

## Setting Up a Number Series for Inventory Acts

The following procedure shows how to set up a number series for inventory acts. 

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. In the **General Ledger Setup** window, fill in the **Contractor Invent. Act Nos.** field.

## Inventory Act Processing

You can create and process inventory acts of contractors' accounts. You can print inventory acts.

### Creating an Inventory Act Card

The following procedure shows how to create an inventory act card. 

1. Choose the **General Ledger** action, choose the **Analysis & Reporting** action, and then choose the **Contractor Invent. Act.** action.

2. In the **Inventory Account Card** window, enter information in the following fields:

   | Field                    | Description                                                  |
   | :----------------------- | :----------------------------------------------------------- |
   | **No.**                  | This field displays the number of the act, and is filled in automatically from the number series. |
   | **Act Date**             | This field displays the act date, and is filled in with the work date. |
   | **Inventory Date**       | This field displays the date of inventory, and is filled with the work date. Debts and liabilities will be calculated on this date. |
   | **Reason Document Type** | Select the type of reason document from the following:   -   **Order** -   **Resolution** -   **Regulation** |

3. Choose the **Add Lines** action.

   > [!NOTE]
   > You must not set filters.

   Debts and liabilities for vendors and customers are calculated, and lines are created. For each customer and vendor, the total debt and the total liability amount (taking posting groups into account) on the inventory date are calculated, and shown in a separate line. The line fields are listed in the following table.

| Field                              | Description          |
| ---------------------------------- | -------------------- |
| **Contractor Type**                | This field displays the contractor type (Customer, Vendor).  |
| **Contractor No.**                 | This field displays the number corresponding to the contractor. |
| **Contractor Name**                | This field displays the name of the contractor.    |
| **Posting Group, G/L Account No.** | This field displays the posting group and the receivables or payables account for which the debt or liability amount is calculated. |
| **Category**                       | This field displays the amount category (Debts, Liabilities). |
| **Total Amount**                   | This field displays the total amount of debts or liabilities. |
| **Confirmed Amount**               | This field displays the total amount of debts or liabilities by default. |

### Changing Separate Lines in an Inventory Act

The following procedure shows how to change individual lines in an inventory act in the **Inventory Account Card** window. 

1. Specify whether the amount (or part of the amount) is one of the following:

    - Confirmed by contractor
    - Not confirmed
    - Overdue

2. If the amount is not confirmed, enter the amount that is not confirmed in the **Not Confirmed Amount** field.

3. If the amount is overdue, enter the overdue amount in the **Overdue Amount** field.

4. To correct a line that has an incorrect amount (for instance, if some documents are not posted, or not applied), choose the **Add Lines** action.

5. Select the vendor or customer code, and then choose the **OK** button. 

The debts and liabilities amount for the selected vendor or customer is recalculated and the lines are inserted in the document.

## Printing the INV-17 form and the Supplement to INV-17 form

The following procedure shows how to print the INV-17 form and the Supplement to INV-17 form.

1. In the **Inventory Account Card** window, choose the **Release** action.
2. Choose the **Act** action, and then choose the **Signatures** action.
3. Select the following fields:

    - **Chairman**
    - **Member1**
    - **Member2**
    - **Member3**
    - **Accountant**

    > [!NOTE]
    > All selected signatures will be reflected in the appropriate fields.

4. Choose the **Print** action, and then choose the **Invent. Act INV-17** action to print the inventory act.
5. Choose the **Print** action, and then choose the **Supplement to Invent. Act INV-17** action to print the supplement to the inventory act.

## Related information

[Russian Payables Reports](Russian-Payables-Reports.md)  
[Russian Receivables Reports](Russian-Receivables-Reports.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
