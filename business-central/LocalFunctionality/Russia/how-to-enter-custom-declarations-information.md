---
title: Set Up Customs Declaration Tracking in Russia
description: Set up customs declaration tracking in the Russian version of Business Central to track imported goods and print declaration details on factura-invoices.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: custom declarations, item tracking, item tracking codes, Russia
ms.date: 10/23/2026
ms.reviewer: v-soumramani
ms.author: bholtorf
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Track customs declarations in Russia

Use customs declaration tracking to record declaration numbers and countries/regions of origin for imported goods. The **Customs Declaration Tracking for Russia** extension uses package numbers to track goods from purchase to sale and include declaration details on factura-invoice reports.

This extension is for on-premises deployments.

## Set up customs declaration tracking

Set up number formats and item tracking codes before you assign declaration numbers to transactions.

### Check the format of customs declarations

To check customs declaration numbers against the formats you specify, turn on **Check CD Number Format** on the **Inventory Setup** page.

Add the accepted formats on the **CD Number Formats** page. A number must have the same length as a format and match each position. If you specify multiple formats, matching any one of them is enough. The following table describes the symbols you can use.

|Symbol  |Use for|
|---------|---------|
|#|A digit from 0 through 9.|
|@|A character from the format check's predefined character set, which includes A-Z.|
|?|Any character.|

All other characters must match exactly. For example, a slash in a format must also appear at that position in the declaration number.

### Set up item tracking codes

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **Item Tracking Codes**, and then choose the related link.
1. Create an item tracking code for items that require customs declaration tracking.
1. Turn on **Package Specific Tracking** for the item tracking code.
1. Choose **CD Location Setup**, and add a line for each location where you need customs declaration rules. Fill in the fields described in the following table.

   | Field | Description |
   |:-|:-|
   | **Location Code** | Specifies the location where the rules apply to this item tracking code. |
   | **CD Info. Must Exist** | Requires customs declaration information for tracked items at the location. |
   | **CD Sales Check on Release** | Checks that item tracking quantities match the quantities to handle when you release sales orders or sales return orders. |
   | **CD Purchase Check on Release** | Checks that item tracking quantities match the quantities to handle when you release purchase orders or purchase return orders. |
   | **Allow Temporary CD Number** | Allows temporary customs declaration numbers at the location. Turn off this setting where permanent declaration numbers are required. |

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **Items**, and then choose the related link.
1. Assign the item tracking code to all items that require customs declaration tracking.

> [!NOTE]
> Turn on **Package Specific Tracking** before you add location setup. You can't delete a location setup line if an item with that tracking code has item ledger entries at the location.

For more information about tracking codes, see [Set up item tracking with serial, lot, and package numbers](../../inventory-how-setup-item-tracking.md).

## Create a customs declaration

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **Customs Declarations**, and then choose the related link.
1. Create a new customs declaration, and fill in the following fields.

   | Field | Description |
   |:-|:-|
   | **No.** | Specifies the customs declaration header number. |
   | **Description** | Specifies a description of the customs declaration. |
   | **Source Type** | Specifies the type of source associated with the declaration. Leave the field blank, or select **Customer**, **Vendor**, or **Item**. |
   | **Source No.** | Specifies the customer, vendor, or item number, depending on **Source Type**. |
   | **Country/Region of Origin Code** | Specifies where the items were produced or processed. Selecting a customer or vendor in **Source No.** fills this field with that customer's or vendor's country/region code. Check that the value is the actual country/region of origin. If you change the header value after adding lines, you can confirm that you want to update the country/region on the existing lines. |
   | **Declaration Date** | Enter the date of the customs declaration. |

1. Add lines for the items on the declaration you received from the customs authority. Enter the item number, variant if applicable, declaration tracking number, and country/region for each line.
1. Close the page.

### Use temporary declaration numbers

Use temporary numbers when goods arrive before you receive the permanent customs declaration number. Turn on **Allow Temporary CD Number** for the relevant item tracking code and location, and select **Temporary CD Number** on the declaration lines.

If **Check CD Number Format** is turned on, Business Central updates **Temporary CD Number** when you enter or change a package number on a declaration line. A number that matches a configured format is marked as permanent. A number that doesn't match any configured format is marked as temporary.

Assign a permanent number before you handle the goods at a location that doesn't allow temporary numbers. For more information about changing tracking numbers, see [Reclassify serial or lot numbers](../../inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers).

## Assign declaration numbers to transactions

Assign customs declaration numbers through package tracking on the **Item Tracking Lines** page. The process is similar to assigning lot and serial numbers. For more information, see [Assign serial or lot numbers during an inbound transaction](../../inventory-how-work-item-tracking.md#to-assign-serial-or-lot-numbers-during-an-inbound-transaction).

## Print declaration details on factura-invoices

Factura-invoice reports use the assigned tracking numbers and declaration information to print declaration numbers and countries/regions of origin.

Before you generate either report, specify **Factura Template Code** on the **Sales & Receivables Setup** page. Also check that the relevant report is included on the **Report Selection - Sales** page:

| Usage | Report |
|:-|:-|
| **Invoice** | **Posted Factura-Invoice (A)**, report 12418. |
| **UnPosted Invoice** | **Order Factura-Invoice (A)**, report 12411. |

These reports generate Excel workbooks from the configured template. Open the downloaded workbook in Excel to review or print it.

For item lines that require package tracking, assign tracking numbers for the full quantity to ship before printing an unposted factura-invoice. The report checks that the tracked quantity matches **Qty. to Ship**.

### Print the posted factura-invoice

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **Posted Sales Invoices**, and then choose the related link.
1. Open the invoice.
1. Choose **Print**. If the **Report Selection - Print** page opens, select **Print Report** for **Posted Factura-Invoice (A)**. Clear the checkbox for any other reports you don't need, and choose **OK**.
1. Fill in the report options. If you only want to review the invoice without marking it as printed, select the **Preview** checkbox.
1. Choose **OK** to generate and download the workbook.
1. Open the workbook in Excel to review or print it.

### Print the factura-invoice before posting

1. [!INCLUDE[open-search](../../includes/open-search.md)], enter **Sales Invoices**, and then choose the related link.
1. Open the invoice.
1. Complete the invoice and its item tracking assignments, and choose **Release**.
1. Choose **Print**. If the **Report Selection - Print** page opens, select **Print Report** for **Order Factura-Invoice (A)**. Clear the checkbox for any other reports you don't need, and choose **OK**.
1. Fill in the report options. If you only want to review the invoice without marking it as printed, select the **Preview** checkbox.
1. Choose **OK** to generate and download the workbook.
1. Open the workbook in Excel to review or print it.

## Related information

- [Russia local functionality](russia-local-functionality.md)
- [Set up item tracking with serial, lot, and package numbers](../../inventory-how-setup-item-tracking.md)
- [Customize Business Central using extensions](../../ui-extensions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
