---
title: Track item cost adjustments
description: Learn how tracking adjustments to item costs can help you keep your item cost data accurate.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords:
ms.search.form:
ms.date: 03/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Track item cost adjustments

It's important to keep item costs accurate and shorten the time between when you post an entry and when the general ledger reflects its cost. You can track the performance of the cost adjustments for individual adjustment runs and items. If errors happen, you can identify the problematic items and make corrections. For example, you can exclude the items from calculations to ensure adjustments aren't interrupted for other items. You can adjust costs for individual items, or create batches of items and adjust them all at the same time.

## Start tracking cost adjustments

It's easy to get started. On the **Inventory Setup** page, the **Cost Adjustment Logging** field offers a few options:

* **Disabled** means you don't log cost adjustment runs.
* **Errors Only** means to log only runs that failed.
* **All** means to log all runs.

> [!NOTE]
> To minimize the size of the log, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't log the adjustments that happen automatically when someone posts an item.

You must also set up the **Post Inventory Cost to G/L (1002)** job queue entry. This job queue entry automatically adjusts costs according to a schedule. To learn more about job queue entries, go to [Use job queues to schedule tasks](admin-job-queues-schedule-tasks.md).

## Manage cost adjustments

Use the **Inventory Cost Adjustment** page to manage and monitor the cost adjustment process. This page displays items along with their costing parameters and cost adjustment status. You can filter the list to focus on items that require adjustment or that are excluded from the cost adjustment process.

### About item batches

You can run cost adjustment for several items by grouping them in batches. Batches make it easy to adjust some items separately, for example, because they take longer to adjust. Batches can also help identify items that have issues.

To create a batch, on the **Inventory Cost Adjustment** page, do one of the following:

* Select the items in the list, choose **Run cost adjustment**, and then choose **Add Batch**.
* To create a batch and run cost adjustment immediately, select the items in the list, choose **Run cost adjustment**, and then choose **Add batch and run**.
* Choose **Run cost adjustment**, choose **Item Batches**, and then enter a filter in the **Item Filter** field.
  
> [!TIP]
> To quickly create another batch for all items that are not already included in a batch, on the **Cost Adjustment - Item Batches** page, choose **Add Missing Items**.

When a run for a batch finishes, the batch has one of the following status on the **Item Batches** page:

* **Success**: The cost adjustment is successful.
* **Failed**: If the cost adjustment fails, [!INCLUDE [prod_short](includes/prod_short.md)] identifies the item that caused the error, and then splits the current batch into two. One batch with the problematic item, and another with the remaining items. Cost adjustment reruns for the batch with the remaining items. If it fails again, the process repeats. You define the maximum number of splits in the **Max. Retry Attempts** field. The default value for retries is 10, but you can enter a new limit.
* **Timed out**: If the cost adjustment for a batch doesn't finish within the period specified in the **Timeout (Minutes)** field (ranging from 1 to 720 minutes), the session terminates and changes are rolled back. [!INCLUDE [prod_short](includes/prod_short.md)] then splits the current batch in half and reruns the cost adjustment process for each half. This process continues until the cost adjustment is successful or reaches the maximum retry attempts.

> [TIP!]
> Each batch runs in a separate session. To monitor progress, use the **Refresh** action.

### Run cost adjustment

Use the **Inventory Cost Adjustment** page to make adjustments.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Cost Adjustment**, and then choose the related link.
1. Depending on what you want to do, use one of the following options:

  * For one or more items immediately, select the items in the list and then choose **Run cost adjustment**.
  * For batches, use one of the following options:

    * To create a batch and adjust costs immediately, choose the items in the list, choose **Run cost adjustment**, and then **Add batch and run**.
    * To run it for all batches, choose **Run cost adjustment**, **Item Batches**, and then choose **Run**.
    
    To learn more about batches, go to [About item batches](#about-item-batches).

### Explore item details

Use the **Item** menu to access information about cost adjustments for a selected item.

* **Item Ledger Entries**: List item entries for the item. The **Mark for Adjustment** action lets you force the rerun of cost adjustment for items directly or indirectly linked to the inbound entries you select. Forcing a rerun can be helpful if previous runs led to incorrect costs.
* **Value Entries**: List value entries for the item.
* **Cost Adjmt. Entry Points**: Open the **Avg. Cost Adjmt. Entry Point** page, which you primarily use to calculate average cost. The page displays combinations of items, locations, variants, and valuation dates for which cost adjustments are, or must be, run.
* **Cost Adjmt. Orders**: Open the **Inventory Adjmt. Entry (Order)** page, where you adjust production and assembly orders. It shows the orders are adjusted, or require adjustment.

### View the outcome

Use the **Log per** menu to view the outcome of cost adjustments:

* **Run**: Show cost adjustment logs for each run. The log includes data about the item filter, status (Success/Failed/Timed out), start and end date/time, duration, and the cost differences produced by the run.
* **Item**: Show detailed information about the adjustment process for the selected item.

### Include or exclude items from adjustments

If one or more items fail, you can exclude the items from the adjustment run, and then include them in later runs. On the **Functions** menu, choose one of the following:

* **Exclude Item from Adjustment** and **Include Item in Adjustment**: Temporarily disable and then re-enable cost adjustment for a selected item. Cost adjustment continues to keep costs accurate for other items while you investigate an issue with a specific item.

## Post adjusted costs to the general ledger

Typically, new value entries are posted to the general ledger according to the schedule for the **Post Inventory Cost to G/L (1002)** job queue entry. However, you can post adjustments to the general ledger immediately from the **Inventory Cost Adjustment** page. On the **Functions** menu, choose **Post Inventory Cost to G/L**.

## Troubleshoot cost adjustments

Use the following options on the **Diagnostics** menu to troubleshoot cost adjustment runs.

* **Export Item Data**: Export item-related data to a text file. You can use the file for further analysis in a sandbox environment or attach it to a support request when investigating costing calculation issues.
* **Import Item Data**: Import the previously exported text file back into the database. This action is only enabled in sandbox environments or evaluation companies.
* **Reset Cost Is Adjusted**: Reset the **Cost Is Adjusted** toggle on items, production orders, or assembly orders. This setting allows you to force the rerun of the cost adjustment for them.
* **Costing Issues Detection Report**: Diagnose typical data issues cause calculation errors in costing. It checks whether the item ledger entries, value entries, item application entries, and capacity ledger entries are correct.
* **Delete Item Data**: Clear all item-related tables in the database. This action is only available in sandbox environments or evaluation companies.

## See also

[Adjust item costs](inventory-how-adjust-item-costs.md)  
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)  
