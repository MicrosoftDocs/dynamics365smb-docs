---
title: Track item cost adjustments
description: Learn how tracking adjustments to item costs can help you keep your item cost data accurate.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.search.keywords:
ms.search.form:
ms.date: 03/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Track item cost adjustments

It's important to keep costs accurate and shorten the time between when you post an entry and when the general ledger reflects its cost. You can track the performance of the cost adjustment batch job for each run and individual item. If the batch job has errors, you can identify the problematic items and take corrective actions. For example, you can exclude the items from calculations to ensure uninterrupted adjustments for other items.

## Start tracking cost adjustments

It's easy to get started. On the **Inventory Setup** page, the **Cost Adjustment Logging** field offers a few options:

* **Disabled** means you don't log cost adjustment runs.
* **Errors Only** means to log only runs that failed.
* **All** means to log all runs.

> [!NOTE]
> To minimize the size of the log, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't log the adjustments that happen automatically when someone posts an item.

## Use the Inventory Cost Adjustments page

The **Inventory Cost Adjustment** page provides tools to manage and monitor the cost adjustment process. This page displays items along with their costing parameters and cost adjustment status. You can filter the list to focus on items that require adjustment or that are excluded from the cost adjustment process.

The following sections provide an overview of features available on the page.

### Run

* **Run cost adjustment**: Run cost adjustments immediately for all or selected items.
* **Add Batch and Run**: Create a new batch of selected items and runs cost adjustments for the batch.
* **Add Batch**: Create a new batch of selected items.
* **Item Batches**: Show a list of existing item batches. For more information about batches, go to [Item batches](#item-batches).

### Item Details

* **Item Ledger Entries**: List item entries and provides a **Mark for Adjustment** action that lets you force the rerun of cost adjustment for items directly or indirectly linked to the inbound entries you select. Forcing a rerun can be helpful if previous runs led to incorrect costs.
* **Value Entries**: List value entries for the item.
* **Cost Adjmt. Entry Points**: Open the **Avg. Cost Adjmt. Entry Point** page, which you primarily use to calculate average cost. The page displays combinations of items, locations, variants, and valuation dates for which cost adjustments are, or must be, run.
* **Cost Adjmt. Orders**: Open the **Inventory Adjmt. Entry (Order)** page, where you adjust production and assembly orders. It shows the orders are adjusted, or require adjustment.

### Log per

* **Run**: Show cost adjustment logs for each run. The log includes data about the item filter, status (Success/Failed/Timed out), start and end date/time, duration, and the cost differences produced by the run.
* **Item**: Show detailed information about the adjustment process for the selected item.

### Functions

* **Exclude Item from Adjustment** and **Include Item in Adjustment**: Temporarily disable and then re-enable cost adjustment for a selected item. Cost adjustment continues to keep costs accurate for other items while you investigate an issue with a specific item.
* **Post Inventory Cost to G/L**: Post new value entries to the general ledger.

### Diagnostics

* **Export Item Data**: Export item-related data to a text file. You can use the file for further analysis in a sandbox environment or attach it to a support request when investigating costing calculation issues.
* **Import Item Data**: Import the previously exported text file back into the database. This action is only enabled in sandbox environments or evaluation companies.
* **Reset Cost Is Adjusted**: Reset the **Cost Is Adjusted** toggle on items, production orders, or assembly orders. This setting allows you to force the rerun of the cost adjustment for them.
* **Costing Issues Detection Report**: Diagnose typical data issues cause calculation errors in costing. It checks whether the item ledger entries, value entries, item application entries, and capacity ledger entries are correct.
* **Delete Item Data**: Clear all item-related tables in the database. This action is only available in sandbox environments or evaluation companies.

### Item batches

Use the **Cost Adjustment - Item Batches** feature to divide a set of items into multiple batches and run the cost adjustment separately for each batch. This feature also helps identify items that have issues.

Batch runs can finish with one of the following outcomes:

* **Success**: If the cost adjustment is successful.
* **Failed**: If the cost adjustment fails, [!INCLUDE [prod_short](includes/prod_short.md)] identifies the item that caused the error, and then splits the current batch into two. One batch with the problematic item, and another with the remaining items. Cost adjustment reruns for the batch with the remaining items. If it fails again, the process repeats. You define the maximum number of splits in the **Max. Retry Attempts** field.
* **Timed out**: If the cost adjustment for a batch doesn't finish within the specified timeout period (ranging from 1 to 720 minutes), the session terminates and changes are rolled back. [!INCLUDE [prod_short](includes/prod_short.md)] then splits the current batch in half and reruns the cost adjustment process for each half. This process continues until the cost adjustment completes successfully or reaches the maximum retry attempts.

> [TIP!]
> Each batch runs in a separate session. To monitor progress, use the **Refresh** action.

## See also

