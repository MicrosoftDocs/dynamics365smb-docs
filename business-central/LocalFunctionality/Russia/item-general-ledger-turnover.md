---
title: Item general ledger turnover in Russia
description: Russian enhancements include creating turnover sheets for goods and materials.
author: DianaMalina


ms.topic: article
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Item General Ledger Turnover

The following pages and reports enable the creation of turnover sheet for goods and materials.

- Item General Ledger Turnover - Page 12449
- Item Turnover (Qty.) - Report 12469

## Item General Ledger Turnover Page (12449)

The **Item General Ledger Turnover** window shows the turnover for items in quantities and costs, the balance at the beginning of the month, positive and negative adjustment, and the balance at the end of the month.

The **Item General Ledger Turnover** window is usually created monthly, and can also be created for the date of inventory. The data in the **Item General Ledger Turnover** window is checked with the warehouse accounting data. The cost data is checked with the net changes and balances of:

- Account 41, Items
- Account 10, Materials

To access the **Item General Ledger Turnover** window

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item G/L Turnover**, and then choose the related link.
2. On the **Options** FastTab, you can specify the format options listed in the following table.

| Field                         | Description                                                  |
| ----------------------------- | ------------------------------------------------------------ |
| **Date Filter**               | Enter the period the data is analyzed for. You can use the buttons in the lower left of the window, or you can specify the period manually. |
| **Location Filter**           | Enter the location code that the information must be filtered for. You can enter a maximum of 10 characters, both numbers and letters. |
| **Global Dimension 1 Filter** | Enter the filter value for the analysis on the Global Dimension 1 filter. |
| **Global Dimension 2 Filter** | Enter the filter value for the analysis on the Global Dimension 2 filter. |

The window contains fields with the information listed in the following table. You cannot edit the fields.

| Field                      | Definition                                                   |
| ---------------------------| ------------------------------------------------------------ |
| **No.**                    | This field displays the item number.                        |
| **Description**            | This field displays the description of the item.             |
| **Base Unit of Measure**   | This field displays the base unit of measure of the item. The unit of measure is specified in the Item card as the Base. |
| **Starting Quantity**,  **Ending Quantity**,  **Debit Quantity**,  **Credit Quantity** | These fields provide information about the quantity of the item—item quantity at the beginning and at the end of the period, and positive and negative correction in quantities of the item. Quantities are specified in base units of measure. |
| **Starting Cost**,  **Ending Cost**,  **Debit Cost**,  **Credit Cost** | These fields provide information about the cost of the item, at the beginning and at the end of the period, and the item positive and negative adjustments in financial amounts. These field values are calculated on the basis of the cost amounts posted in the general ledger entry. |

To display the selected item card

- Choose the **Item** button and then **Card** (<kbd>Shift</kbd>+<kbd>F5</kbd> key).

To print the **Item Turnover (Qty.)** or **Item Turnover Checklist** reports.

- Choose the **Print** action, and then choose the **Turnover Sheet** or the **Turnover Checklist** action.

## Item Turnover (Qty.) Report (12469)

To analyze net changes and balances of items and materials, you can print the Item Turnover (Qty.) report and export it to Microsoft Office Excel. The report prints the following data from the Item General Ledger Turnover window:

- Item number and description
- Balance at the beginning of the specified period (quantity and cost)
- Positive adjustment (quantity and cost)
- Negative adjustment (quantity and cost)
- Balance at the end of the specified period (quantity and cost )
- Unit of measure

The following procedure shows how to access the turnover sheet.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item General Ledger Turnover**, and then choose the related link.
2. Choose the **Print** action, and then choose the **Turnover Sheet** action.

The turnover sheet is printed monthly and on the date of inventory, but it can be printed for any given period.

The **Item** FastTab of the request page contains fields with the information listed in the following table.

| Field               | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| **No.**             | Enter an item number or a range of item numbers to print an item general ledger turnover for one item or for a group of items. |
| **Location Filter** | Enter the location code that the information must be filtered for, to print the Item General Ledger Turnover window for one or several locations.   You can enter a maximum of 10 characters, both numbers and letters. The field value is entered automatically in the **Location Filter** field |
| **Date Filter**     | Enter the period that the report is printed for.             |

On the **Options** FastTab, you can specify the format options listed in the following table.

| Parameter                                  | Description       |
| ------------------------------------------ | ----------------- |
| **Rounding Precision**                     | Choose the required rounding precision:   0.001, 0.01, 1, or 1000. |
| **Replace zero values by blanks**          | Select this field if you want to replace zero values with blanks. |
| **Skip accounts without net changes**      | Select this field to exclude from the report the accounts with zero turnovers for the given period. |
| **Skip accounts with zero ending balance** | Select this field to exclude from the report the accounts with zero ending balance at the end of the period. |
| **Skip zero lines**                        | Select this field to exclude from the report the lines with zero values. |
| **Unit of Measure**                        | Choose a unit of measure for calculating report quantities:   -   **Base** – In base units of measure -   **Sale** – In units of measure for sales -   **Purchase** – In units of measure for purchases |
| **Print Quantity**                         | Select this field to print the quantity that is mentioned in the report. |
| **Print Cost**                             | Select this field to print the costs that are mentioned in the report. |
| **Export to Excel**                        | Select this field to export the report to Microsoft Office Excel. |

## Related information

[Item Obligatory Acts](Item-Obligatory-Acts.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
