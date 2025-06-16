---
title: Track item cost adjustments
description: Learn how tracking adjustments to item costs can help you keep your item cost data accurate.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords:
ms.search.form:
ms.date: 04/08/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Track item cost adjustments

It's important to keep item costs accurate and shorten the time between when you post an entry and when the general ledger reflects its cost. You can track the performance of the cost adjustments for individual adjustment runs and items. If errors happen, you can identify the problematic items and make corrections. For example, you can exclude the items from calculations to ensure adjustments aren't interrupted for other items. You can adjust costs for individual items or create batches of items and adjust them all at the same time.

## Start tracking cost adjustments

It's easy to get started. On the **Inventory Setup** page, the **Cost Adjustment Logging** field offers a few options:

* **Disabled** means you don't log cost adjustment runs.
* **Errors Only** means you log only runs that failed.
* **All** means you log all runs.

> [!NOTE]
> To minimize the size of the log, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't log the adjustments that happen automatically when someone posts an item.

You must also set up the **Post Inventory Cost to G/L (1002)** job queue entry. This job queue entry automatically adjusts costs according to a schedule. To learn more about job queue entries, go to [Use job queues to schedule tasks](admin-job-queues-schedule-tasks.md).

## Manage cost adjustments

Use the **Inventory Cost Adjustment** page to manage and monitor the cost adjustment process. This page displays items along with their costing parameters and cost adjustment status. You can filter the list to focus on items that require adjustment or that are excluded from the cost adjustment process.

### About item batches

You can run cost adjustments for several items by grouping them into batches. Batches make it easy to adjust some items separately, for example, because they take longer to adjust. Batches can also help identify items that have issues.

To create a batch, on the **Inventory Cost Adjustment** page:

* Select the items in the list, choose **Run cost adjustment**, and then choose **Add Batch**.

To create a batch and run cost adjustment immediately:
* Select the items in the list, choose **Run cost adjustment**, and then choose **Add batch and run**.
* Choose **Run cost adjustment**, choose **Item Batches**, and then enter a filter in the **Item Filter** field.
  
> [!TIP]
> To quickly create another batch for all items that aren't already included in a batch, on the **Cost Adjustment - Item Batches** page, choose **Add Missing Items**.

When a run for a batch finishes, the batch has one of the following status on the **Item Batches** page:

* **Success**: The cost adjustment is successful.
* **Failed**: If the cost adjustment fails, [!INCLUDE [prod_short](includes/prod_short.md)] identifies the item that caused the error and then splits the current batch into two. One batch with the problematic item, and another with the remaining items. Cost adjustment reruns for the batch with the remaining items. If it fails again, the process repeats. You define the maximum number of splits in the **Max. Retry Attempts** field. The default value for retries is 10, but you can enter a new limit.
* **Timed out**: If the cost adjustment for a batch doesn't finish within the period specified in the **Timeout (Minutes)** field (ranging from 1 to 720 minutes), the session terminates and changes are rolled back. [!INCLUDE [prod_short](includes/prod_short.md)] then splits the current batch in half and reruns the cost adjustment process for each half. This process continues until the cost adjustment is successful or reaches the maximum retry attempts.

> [TIP!]
> Each batch runs in a separate session. To monitor progress, use the **Refresh** action.

### Run cost adjustment

Use the **Inventory Cost Adjustment** page to make adjustments.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Cost Adjustment**, and then choose the related link.
1. Depending on what you want to do, use one of the following options:

  * For one or more items immediately, select the items in the list and then choose **Run cost adjustment**.
  * For batches, use one of the following options:

    * To create a batch and adjust costs immediately, choose the items in the list, choose **Run cost adjustment**, and then **Add batch and run**.
    * To run it for all batches, choose **Run cost adjustment**, **Item Batches**, and then choose **Run**. To learn more about batches, go to [About item batches](#about-item-batches).
  * For all items on an item-by-item basis, which saves the results after each item is processed. For example, this option is useful for handling a large number of items, reducing lock times, and preventing full reruns if something goes wrong. To use this option, run the **Adjust Cost - Item Entries** report, and turn on the **Item-by-Item Adjustment** toggle.

### Explore item details

Use the **Item** menu to access information about cost adjustments for a selected item.

* **Item Ledger Entries**: List item entries for the item. The **Mark for Adjustment** action lets you force the rerun of cost adjustment for items directly or indirectly linked to the inbound entries you select. Forcing a rerun can be helpful if previous runs led to incorrect costs.
* **Value Entries**: List value entries for the item.
* **Cost Adjmt. Entry Points**: Open the **Avg. Cost Adjmt. Entry Point** page, which you primarily use to calculate average cost. The page displays combinations of items, locations, variants, and valuation dates for which cost adjustments are, or must be, run.
* **Cost Adjmt. Orders**: Open the **Inventory Adjmt. Entry (Order)** page, where you adjust production and assembly orders. It shows the orders are adjusted or require adjustment.
* **Item Application Entries**: Open the **Item Application Entries** page for details about quantity and cost applications. You can use the **Reset Outbound Entry is Updated** action in combination with the **Mark for Adjustment** setting on the **Item Ledger Entries** page to force a rerun of cost adjustment.

### View the outcome

Use the **Log per** menu to view the outcome of cost adjustments:

* **Run**: Show cost adjustment logs for each run. The log includes data about the item filter, status (Success/Failed/Timed out), start and end date/time, duration, and the cost differences produced by the run.
* **Item**: Show detailed information about the adjustment process for the selected item.

### Include or exclude items from adjustments

If one or more items fail, you can exclude the items from the adjustment run and then include them in later runs. On the **Functions** menu, choose one of the following:

* **Exclude item from adjustment** and **Include item in adjustment**: Temporarily disable and then re-enable cost adjustment for a selected item. Cost adjustment continues to keep costs accurate for other items while you investigate an issue with a specific item.

### Use iterative cost adjustments

To manage the processing scope of cost adjustments for items that have a high volume of transactions, you can do the adjustments on a period-by-period basis. You can do that in just a few steps. On the **Inventory Cost Adjustment** page, select the item to adjust, choose the **Cost Adjmt. Entry Points** action. Next, choose the **Valuation Date** until you want to complete the adjustment and then choose the **Adjust Cost Until Valuation Date** action.

These steps adjust entries for the selected item up to the chosen date and affects entries across all locations and variants. The item is marked as adjusted when all periods are fully adjusted.

You can also adjust costs for individual production and assembly orders. On the **Inventory Cost Adjustment** page, select one or more production or assembly orders, and then choose the **Adjust Cost for Selected Orders** action.

## Post adjusted costs to the general ledger

Typically, new value entries are posted to the general ledger according to the schedule for the **Post Inventory Cost to G/L (1002)** job queue entry. However, you can post adjustments to the general ledger immediately from the **Inventory Cost Adjustment** page. On the **Functions** menu, choose **Post Inventory Cost to G/L**.

## Troubleshoot cost adjustments

Use the following options on the **Diagnostics** menu to troubleshoot cost adjustment runs.

* **Export item data**: Export item-related data to a text file. You can use the file for further analysis in a sandbox environment or attach it to a support request when investigating costing calculation issues.
* **Import item data**: Import the previously exported text file back into the database. This action is only enabled in sandbox environments or evaluation companies.
* **Reset Cost Is Adjusted**: Reset the **Cost Is Adjusted** toggle on items, production orders, or assembly orders. This setting allows you to force the rerun of the cost adjustment for them.
* **Costing Issues Detection report**: Diagnose typical data issues cause calculation errors in costing. It checks whether the item ledger entries, value entries, item application entries, and capacity ledger entries are correct.
* **Delete item data**: Clear all item-related tables in the database. This action is only available in sandbox environments or evaluation companies.

### Self-diagnostics for potential issues and performance pitfalls

During posting and cost adjustment, [!INCLUDE [prod_short](includes/prod_short.md)] scans the current setup and data to identify inefficiencies that might affect the accuracy and performance of cost adjustment.

When you open the **Inventory Cost Adjustment** page, a notification might state that issues were found. You can view the issues on the **Action Messages** page by selecting **Action Messages** in the **Diagnostics** section.

[!INCLUDE [prod_short](includes/prod_short.md)] issues warnings in the following scenarios:

* Cost adjustment isn't set for automatic runs or run manually.
* Average cost adjustment settings aren't optimal for performance.
* Inventory periods aren't in use.
* Many periods require adjustment.
* Many production and assembly orders require adjustment.
* Cost adjustment for a single item takes more than five minutes to complete.
* One or more items are excluded from cost adjustment.
* Data discrepancies remain after cost adjustment completes.

Scanning happens automatically during normal system usage, but you can start it manually at any time by selecting the **Run Tests** action on the **Cost Adjmt. Action Messages** page. You can't turn off diagnostics completely but you can pause it for up to 30 days by choosing **Snooze for 30 days**.

## Use the Cost Adjustment Tracer feature

Cost adjustment can take time to complete. For example, due to a high volume of entries, data errors, or a setup that isn't optimal. Because the cause is often unclear, you can use the Cost Adjustment Tracer feature to gain visibility and get some help to diagnose data-related issues.

To use the Cost Adjustment Tracer feature, on the **Inventory Cost Adjustment** page, choose **Item Batches**. Create a batch for one or more items, fill in the **Timeout (minutes)** field, select the **Trace** checkbox, and then choose the **Run** action.

During the cost adjustment process, [!INCLUDE [prod_short](includes/prod_short.md)] records AL events, items, locations, variants, entries, and orders it processes. When the cost adjustment completes or reaches the specified time-out, it saves the results in the **Trace Log**. To access the recorded details, select **Trace Log**. Due to the potentially large volume of log entries, we recommend that you turn on the **Analysis View** mode to summarize the data.

## Related information

[Adjust item costs](inventory-how-adjust-item-costs.md)  
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)  
