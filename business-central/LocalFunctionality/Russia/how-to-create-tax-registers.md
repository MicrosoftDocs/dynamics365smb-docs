---
title: Creating tax registers in Russia
description: Step-by-step guide to creating tax registers in Russia for tax accounting purposes.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: tax registers, create tax registers, Russia
ms.date: 07/14/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Create tax registers

The following procedure shows how to create tax registers.

1. Choose **Financial Management**, choose **Tax Accounting**, choose **Setup**, choose **Tax Register**s, and then choose **Sections**.

1. In the **Tax Register Sections** window, choose the **Functions** button.

1. Select one of the following fields:

   - **Copy Section** -Copies data from one tax register to another.
   - **Clear Registers** -Clears data already created in the tax registers and is used for debugging conditions to recount tax registers.
   - **Create Registers** -Creates data in the tax registers**.**

1. To create data, choose **Create Register**. The **Tax Register Create** window opens.

1. On the **General** tab, enter the fields described in the following table.

   | Field | Description |
   |:-|:-|
   | **Periodicity** | Enter a period to create data in tax accounting registers. The allowed values are:   -   **Month** -   **Quarter** -   **Year**. **Note:** If you select a month, the data in the selected registers is created especially for that month. If you select a quarter, the data is created for each of the three months of that quarter. If you select a year, the data is created for each of the 12 months of that year. |
   | **Accounting Period** | The value entered in this field depends on the value selected in the Periodicity field. Select the accounting period  (**Month**, **Quarter**, or **Year**). |
   | **From, To** | These fields are filled in automatically and show start and end dates of the chosen period. |
   | **G/L Entries, Vend's/Cust's, Items, Fixed Asset, Fut. Exp., Payroll, Templates** | Select the fields to calculate registers of the appropriate type. |
   | **Status** | This field displays information about the version of the tax register. |
   | **Starting Date, Ending Date** | This field displays the dates given when setting the tax register version. |

1. Choose **OK** to create the tax register.

   > [!NOTE]
   > If the creation of registers for an already counted period is selected, a warning is displayed. At this stage of the tax register creation, it's possible either to continue counting and delete all existing data, or stop.

1. To view the calculated information in the **Tax Register Accumulation** window, choose **Financial Management**, choose **Tax Accounting**, choose **Reporting,** and then choose **Profit Tax**.

1. Using the register list, you can view the contents of any register or using the arrows at the top of the window, you can view the information going from one register to another.

1. With the arrows and buttons in the lower-left corner of the window, you can view the contents of the registers for previously counted periods.

1. Choose the **Drill-down** button in the **Amount** field to view the sources based on which this was counted. A source can be a tax register or a list of transactions forming this amount, depending on the settings. If the source forming the sum is a tax register, choose the **Drill-down** button to open the window where the source tax register information is displayed. Then choose the **Drill-down** button in the **Amount** field on this form to get a list of transactions forming the amount.

1. Select a document and choose **Find Entries** to get all the transactions of the selected document.

1. Choose **Show Related Entries** to view all the transactions of any entry ledger that is created.

## Related information

- [Tax Accounting](Tax-Accounting.md)  
- [Tax Registers](Tax-Registers.md)  
- [Set Up Tax Register Sections](How-to-Set-Up-Tax-Register-Sections.md)  
- [Collecting Profit Tax Information for Tax Declaration](Collecting-Profit-Tax-Information-for-Tax-Declaration.md)  
- [Find Entries](../../ui-find-entries.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
